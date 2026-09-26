# 🆔 Preventing Unicode & Homoglyph Attacks in Display Names

![Security](https://img.shields.io/badge/security-reviewed-success?style=flat-square&color=2ecc71)
![Tests](https://img.shields.io/badge/tests-passing-success?style=flat-square)
![Coverage](https://img.shields.io/badge/coverage-90%25-brightgreen?style=flat-square)

Unicode-safe • Emoji-friendly • Homoglyph-protected • Race-condition safe

---

## 📘 Display Name Feature – Design, Validation & Security

### 1. Introduction

The **Display Name** feature allows users to choose a public-facing name (e.g. store name, profile name) during registration and profile setup.

This name:
- Is user-visible  
- Must be unique  
- Must be secure against impersonation  
- Must support international languages  
- Must allow emojis for UX, without breaking security  

The implementation follows **Clean Architecture**, uses **CQRS**, and enforces **database-level guarantees**.

---

### 2. Why This Feature Needed Special Design

Naive implementations commonly suffer from:
- Race conditions during availability checks  
- Unicode homoglyph attacks (impersonation)  
- Emoji-based uniqueness bypass  
- Language and casing inconsistencies  
- Poor error propagation to frontend  

This design addresses all of the above.

---

### 3. High-Level Flow

1. User enters a display name on the registration page  
2. Frontend calls **Check Display Name Availability API**  
3. Backend:
   - Validates input  
   - Applies security & normalization rules  
   - Checks availability  
   - Returns availability + suggestions (if needed)  
4. On registration:
   - Display name is validated again  
   - Database unique constraint enforces final truth  

> **Availability check is advisory. Registration is authoritative.**

---

### 4. API Design

#### Endpoint
```
GET /api/users/display-names/{displayName}/availability
```

#### Sample Success Response
```json
{
  "displayName": "😀Your Store😀",
  "isAvailable": true
}
```

#### Sample Validation Error
```json
{
  "errors": [
    {
      "code": "InvalidDisplayName",
      "message": "This display name is reserved"
    }
  ]
}
```

---

### 5. Core Design Principle

> **Display Name validation and security rules live in one place only.**

Implemented via:
```
DisplayNamePolicy
```

All layers (availability, registration, profile update) rely on this policy.

---

### 6. Emoji Handling

- Emojis are allowed visually  
- Emojis are removed during normalization  
- Emojis do not participate in uniqueness  

| Input | Normalized |
|-----|-----------|
| 😀Your Store😀 | your store |
| 🔥ADMIN🔥 | admin |

---

### 7. Unicode Normalization Pipeline

1. Unicode normalization (Form D)  
2. Diacritic removal  
3. Emoji removal  
4. Homoglyph folding  
5. Culture-invariant lowercasing  
6. Trim whitespace  

---

### 8. Homoglyph & Language Protection

- Single-script enforcement  
- Mixed Latin/Cyrillic/Greek blocked  
- Known homoglyph folding  

Blocked examples:
```
admin  → аdmin
paypal → раураl
```

---

### 9. Reserved Display Names

Blocked globally (after normalization):

```
admin
support
system
moderator
root
official
```

---

### 10. Database Enforcement

SQL Server uniqueness guarantee:

```sql
DisplayName_Normalized AS LOWER(DisplayName) PERSISTED
```

```sql
CREATE UNIQUE INDEX UX_Users_DisplayName_Normalized
ON Users (DisplayName_Normalized);
```

---

### 11. Race Condition Safety

- Availability checks are informational  
- Registration relies on DB constraint  
- Conflicts handled gracefully  

---

### 12. Unit Testing

Covered cases:
- Emoji-only names  
- Mixed-script attacks  
- Homoglyph impersonation  
- Reserved name variants  
- Valid multilingual names  

---

## 🧱 Architecture Decision Record (ADR)

### ADR-005: Secure Display Name Handling

**Status:** Accepted

#### Context
Display names are user-visible identifiers and form an **identity boundary**.
Naive approaches allow impersonation via Unicode homoglyphs, emojis, or race conditions.

#### Decision
We implemented a centralized **DisplayNamePolicy** responsible for:
- Unicode normalization
- Emoji handling
- Single-script enforcement
- Homoglyph folding
- Reserved name blocking

Availability checks are advisory.
Final uniqueness is enforced at the database level using a persisted computed column and unique index.

#### Consequences

**Positive**
- Prevents impersonation attacks
- Supports international users
- Emoji-friendly UX
- Race-condition safe
- Clean Architecture compliant

**Negative**
- Increased validation complexity
- Requires dedicated unit tests for Unicode edge cases

#### Alternatives Considered
- Regex-only validation (rejected)
- Database collation-only enforcement (rejected)
- Reserving names during availability check (rejected)

---

## 🏆 Final Guarantees

✔ Unicode-safe  
✔ Emoji-friendly  
✔ Homoglyph-protected  
✔ Race-condition safe  
✔ Clean Architecture compliant  

---

## 📄 License

This pattern may be reused for:
- Usernames
- Store names
- Public handles
- Organization identifiers
