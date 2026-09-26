# US Recruitment Firm – Setup & Operations Plan

**Location:** Vadodara, Gujarat, India  
**Primary Business Function:** US Recruitment & Staffing  
**Initial Recruitment Team:** 8 Recruiters  
**Recruitment Platform:** CEIPAL  
**Document Type:** Setup, Implementation & Operations Plan  
**Status:** Preliminary Planning / Client Reference  

---

## 1. Executive Summary

This document defines the proposed plan for establishing a US-focused recruitment firm operating from Vadodara, Gujarat.

The initial operation will be designed for **8 recruiters**, with the technology and operating foundation structured so that the business can subsequently expand without redesigning its core systems.

The setup covers:

- Office IT infrastructure
- Laptops and recruiter equipment
- Internet connectivity and network redundancy
- US calling infrastructure
- CEIPAL ATS/recruitment platform
- Job boards and candidate sourcing
- Corporate email and collaboration
- Company website
- Information security
- Recruitment workflows and SOPs
- Recruiter hiring and training
- Management reporting and KPIs
- Compliance considerations
- Initial CAPEX and recurring OPEX
- 60-day implementation and go-live plan

> **Important:** All costs in this document are preliminary planning estimates. Final costs must be validated through vendor quotations before procurement or contractual commitment.

---

# 2. Business Objective

The objective is to establish a professional recruitment operation in Vadodara capable of servicing US clients, staffing companies, MSP/VMS requirements, and direct hiring requirements.

The operation should be capable of supporting, depending on client contracts and applicable requirements:

- US IT Recruitment
- Professional / Non-IT Recruitment
- Contract Staffing
- Contract-to-Hire
- Direct Hire / Permanent Placement
- W2 requirements
- C2C requirements
- Client/MSP/VMS-driven recruitment

The company should be built around four principles:

1. **Standardized recruitment processes**
2. **Centralized candidate and requirement management through CEIPAL**
3. **Secure and reliable infrastructure**
4. **Measurable recruiter performance and recruitment funnel analytics**

---

# 3. Initial Organization Structure

A lean structure is recommended during the initial stage.

```text
                         Director / Owner
                                │
                                ▼
                     Recruitment Manager
                                │
                    ┌───────────┴───────────┐
                    │                       │
             Sr. Recruiter / Lead      Operations / HR
                    │
          ┌─────────┼─────────┐
          │         │         │
     Recruiters Recruiters Recruiters
          │
          ▼
     US Candidates
          │
          ▼
   Client / MSP / VMS
```

For an initial team of eight recruiters, unnecessary management layers should be avoided.

One experienced recruiter may initially perform the role of **Senior Recruiter / Team Lead**, reporting to the Recruitment Manager or business owner.

---

# 4. Initial Staffing Plan

| Role | Initial Headcount | Purpose |
|---|---:|---|
| Recruitment Manager / Operations Head | 1 | Recruitment delivery and operations management |
| Senior Recruiter / Team Lead | 1 | Team support, quality review and escalation |
| Recruiters | 7 | Candidate sourcing, screening and submissions |
| HR / Admin | Shared / Optional initially | Attendance, hiring and administration |
| IT Support | Outsourced / Shared | Infrastructure and user support |

> The final structure can be adjusted depending on whether one of the eight recruiters is designated as the team lead.

---

# 5. Office Infrastructure Requirements

The initial office should support at least 8 recruiter workstations and ideally provide expansion capacity for approximately 15–20 users.

The office should include:

- Recruiter work area
- Manager workstation
- Conference / interview room
- Reliable power backup
- Dual internet connectivity
- Structured LAN cabling
- Secure Wi-Fi
- Printer area
- CCTV/access control if required
- Storage for IT equipment
- Appropriate late-shift access and security

Because US recruitment will involve evening/night operations in India, employee access, transport policy, office security and power availability should be considered during office selection.

---

# 6. Recruiter Laptop Specification

Each recruiter should receive a business-class laptop.

### Recommended minimum specification

| Component | Recommended Specification |
|---|---|
| Processor | Intel Core i5 / AMD Ryzen 5 or better |
| Memory | 16 GB RAM |
| Storage | 512 GB NVMe SSD |
| Operating System | Windows 11 Pro |
| Display | 15.6-inch Full HD preferred |
| Network | Gigabit Ethernet / compatible adapter |
| Wireless | Wi-Fi 6 preferred |
| Security | TPM 2.0, BitLocker support |
| Warranty | 3-year business warranty preferred |

8 GB RAM should be avoided for new purchases because recruiters commonly operate CEIPAL, Outlook, Teams, LinkedIn, job boards, spreadsheets, VoIP and numerous browser tabs simultaneously.

---

# 7. IT Equipment Requirement & Preliminary Budget

| Equipment | Qty | Planning Unit Cost | Estimated Total |
|---|---:|---:|---:|
| Business laptops | 8 | ₹60,000 | ₹4,80,000 |
| Logitech USB headsets | 8 | ₹2,500 | ₹20,000 |
| Keyboard + Mouse Combo | 8 | — | ₹9,600 |
| 5 GHz AC1200 / Gigabit Routers / APs | 2 | ₹3,000 | ₹6,000 |
| Business Firewall / Dual-WAN Router | 1 | ₹20,000 | ₹20,000 |
| Gigabit Managed Network Switch | 1 | ₹10,000 | ₹10,000 |
| CAT6 LAN Cabling / 8 LAN Points | 8 | ₹1,500 | ₹12,000 |
| Patch Panel / Rack / Network Accessories | 1 Lot | ₹15,000 | ₹15,000 |
| Multifunction Laser Printer | 1 | ₹25,000 | ₹25,000 |
| 4K-supported Projector | 1 | ₹50,000 | ₹50,000 |
| Conference Room Camera | 1 | ₹30,000 | ₹30,000 |
| UPS / Power Backup | 1 Lot | ₹60,000 | ₹60,000 |
| NAS / Backup Storage | 1 | ₹35,000 | ₹35,000 |
| Surge Protection / Power Accessories | 1 Lot | ₹10,000 | ₹10,000 |

### Preliminary IT hardware budget

**Approximately ₹7.8–8.0 lakh**

A procurement contingency should be maintained for price variations, adapters, installation and additional accessories.

---

# 8. Internet & Network Architecture

Internet availability is business-critical for US recruitment.

Two independent business internet connections are strongly recommended.

### Recommended configuration

**Primary Internet**

- 300–500 Mbps business connection
- Static IP #1

**Secondary Internet**

- 200–300 Mbps business connection
- Static IP #2
- Preferably a different ISP

### Proposed architecture

```text
              PRIMARY ISP
           300–500 Mbps
            Static IP #1
                 │
                 │
                 ▼
        ┌──────────────────┐
        │ Dual-WAN Firewall│
        │     / Router     │
        └────────┬─────────┘
                 │
          ┌──────┴──────┐
          │             │
          ▼             ▼
   Managed Switch     Wi-Fi AP
          │
    ┌─────┼──────────────────────┐
    │     │       │       │      │
   PC1   PC2     PC3     ...    PC8

                 ▲
                 │
        SECONDARY / BACKUP ISP
             200–300 Mbps
              Static IP #2
```

### Network recommendations

- CAT6 LAN connection for every recruiter
- Gigabit managed switch
- Dual-WAN automatic failover
- Separate corporate and guest Wi-Fi networks
- Firewall rules for corporate devices
- Wi-Fi should not be the primary connection for recruiter desktops/laptops during production hours
- Network equipment should be connected to UPS power

The two static IPs should preferably be associated with two independent ISP connections to provide genuine redundancy.

---

# 9. Recruitment Platform – CEIPAL

**CEIPAL will be used as the primary recruitment software for the initial operation.**

CEIPAL should become the central system of record for recruitment activity.

The implementation should be configured around the firm's actual workflow rather than allowing each recruiter to develop an independent process.

## Core CEIPAL usage

The platform should manage:

- Clients
- Contacts
- Job requirements
- Recruiter assignment
- Candidate database
- Resume parsing
- Candidate search
- Candidate ownership
- Duplicate candidate management
- Screening notes
- Candidate status
- Right-to-Represent tracking
- Submissions
- Interviews
- Offers
- Placements
- Activities and communication history
- Recruiter performance
- Management reports

### Target workflow

```text
Client / VMS Requirement
          │
          ▼
   Requirement Created
        in CEIPAL
          │
          ▼
    Recruiter Assigned
          │
          ▼
 Candidate Sourcing
          │
          ▼
 Candidate Screening
          │
          ▼
 Right-to-Represent
          │
          ▼
 Candidate Submission
          │
          ▼
   Client Interview
          │
          ▼
        Offer
          │
          ▼
      Placement
          │
          ▼
 Reporting / Analytics
```

### CEIPAL implementation activities

Before go-live:

1. Configure organization structure.
2. Create users and permissions.
3. Define candidate statuses.
4. Define job/requisition workflow.
5. Define submission workflow.
6. Configure email integration.
7. Configure job-board integrations where available.
8. Configure calling integrations where appropriate.
9. Create standard candidate notes and submission templates.
10. Define mandatory fields.
11. Configure recruiter dashboards.
12. Configure management reports.
13. Define duplicate candidate handling.
14. Configure placement workflow.
15. Train all users.

**CEIPAL licensing and implementation costs should be confirmed directly with CEIPAL based on the required modules, integrations and number of users.**

---

# 10. US Calling & Communication Platform

Recruiters should not depend on Indian mobile numbers for normal US candidate communication.

A cloud-based business telephony/VoIP solution should be implemented.

### Required capabilities

- US telephone numbers
- Individual recruiter extensions
- Inbound calls
- Outbound calls
- Voicemail
- Call history
- Call analytics
- Call disposition
- SMS where supported and compliant
- Click-to-call where possible
- CEIPAL integration where supported
- Call recording only where lawful and appropriately disclosed
- Manager monitoring/reporting

Potential vendors should be evaluated based on CEIPAL compatibility, India-based agent support, US number availability, calling rates, SMS registration requirements, reliability and reporting.

### Preliminary budget

**₹20,000–₹40,000 per month**

Final cost will depend on provider, usage, phone-number requirements and international operating model.

---

# 11. Corporate Email & Collaboration

A business collaboration suite such as Microsoft 365 is recommended.

### Initial accounts

Approximately 10–12 accounts should be planned initially for:

- 8 recruiters
- Recruitment Manager
- Director / Owner
- HR / Operations
- Shared/service accounts where required

Example addresses:

```text
firstname.lastname@company.com
recruitment@company.com
hr@company.com
accounts@company.com
support@company.com
```

### Required configuration

- Corporate domain
- Microsoft 365
- Outlook
- Microsoft Teams
- OneDrive / SharePoint
- Multi-factor authentication
- Email signatures
- Shared mailboxes
- Distribution groups
- Anti-spam / anti-phishing configuration
- Device policies

A planning allowance of approximately **₹10,000–₹15,000 per month plus applicable taxes** can be maintained depending on the selected plans and number of accounts.

---

# 12. Candidate Sourcing & Job Boards

The candidate sourcing strategy should not depend on a single platform.

The sourcing ecosystem may include:

- CEIPAL candidate database
- LinkedIn Recruiter
- Dice
- Indeed
- Monster
- CareerBuilder or other relevant US databases
- Referrals
- Internal candidate database
- Previous applicants
- Recruiter networks

## Recommended initial approach

Avoid purchasing premium licenses for all eight recruiters immediately.

Start with a controlled number of premium sourcing seats and measure utilization.

Example:

- 2–3 premium LinkedIn sourcing seats
- Dice access based on technology recruitment requirements
- CEIPAL integrated job-board access where commercially appropriate
- Shared sourcing strategy managed by the team lead

### Preliminary sourcing budget

**₹1.0–2.0 lakh per month**

This is one of the largest variables in the operating budget and should be finalized only after vendor quotations and the client's target recruitment vertical are confirmed.

---

# 13. Company Website

A professional recruitment website should be established to support both business development and candidate acquisition.

The website should not be limited to a simple corporate brochure.

## Proposed sitemap

```text
Home
│
├── About Us
│
├── Services
│   ├── IT Staffing
│   ├── Professional Staffing
│   ├── Contract Staffing
│   ├── Contract-to-Hire
│   ├── Direct Hire
│   └── Recruitment Process Outsourcing
│
├── Industries
│
├── For Employers
│   ├── Submit Requirement
│   └── Request Consultation
│
├── For Candidates
│   ├── Search Jobs
│   ├── Submit Resume
│   └── Career Opportunities
│
├── Jobs
│
├── Why Us
│
├── Contact Us
│
├── Privacy Policy
├── Candidate Privacy Notice
├── Terms & Conditions
└── Cookie Policy
```

## Candidate workflow

```text
Candidate
    │
    ▼
Search Jobs
    │
    ▼
View Job
    │
    ▼
Apply
    │
    ▼
Upload Resume
    │
    ▼
Consent / Privacy Notice
    │
    ▼
CEIPAL / Recruitment Workflow
```

Where practical, job and application functionality should integrate with CEIPAL rather than creating a second independent candidate database.

### Website requirements

- Responsive/mobile-friendly design
- SEO-friendly structure
- SSL/HTTPS
- Candidate application
- Resume upload
- Employer enquiry
- Contact form
- Analytics
- Privacy controls
- Spam protection
- CEIPAL integration where supported
- Fast hosting/CDN
- Automated backups

### Preliminary website budget

**₹1.0–2.0 lakh** depending on design, functionality and integration depth.

---

# 14. Information Security

The company will process candidate resumes, contact information, employment information and potentially other personal information.

Security must therefore be implemented from the beginning.

## Minimum controls

### Device security

- Windows 11 Pro
- BitLocker disk encryption
- Endpoint security / EDR
- Automatic Windows updates
- Screen-lock policy
- Restricted local administrator access
- Corporate device inventory

### Identity security

- MFA for all corporate accounts
- Unique user accounts
- Strong password policy
- Password manager
- No credential sharing
- Immediate access revocation during offboarding

### Data security

- CEIPAL as primary candidate system
- Avoid candidate data on personal drives
- Controlled corporate cloud storage
- Automated backup
- Access based on job role
- Defined retention procedures

### Network security

- Business firewall
- Separate guest Wi-Fi
- Corporate Wi-Fi protection
- Dual internet failover
- Static IP management
- Router/firewall firmware updates

### Employee security policies

- Acceptable Use Policy
- Information Security Policy
- Password Policy
- Candidate Data Handling Policy
- Remote Work Policy if applicable
- Employee Offboarding Checklist
- Incident Reporting Procedure

---

# 15. Recruitment Compliance Framework

Appropriate professional legal/compliance advice should be obtained for the company's specific Indian and US operating model.

Operational controls should address areas such as:

- Candidate consent and privacy
- Candidate data retention
- Right-to-Represent
- Job advertising practices
- Email outreach
- SMS outreach
- Calling practices
- Call recording requirements
- Client confidentiality
- Candidate information access
- Candidate deletion/correction requests where applicable
- Cross-border processing of candidate information
- Anti-discrimination / EEO considerations applicable to the engagement
- Work authorization information handling

If the business later becomes the legal employer/payroller of US workers rather than functioning only as a recruitment/sourcing organization, additional payroll, tax, employment and insurance requirements will need to be assessed separately.

---

# 16. Standard Recruitment Process (SOP)

Every recruiter should follow the same standard process.

```text
Requirement Received
        │
        ▼
Requirement Analysis
        │
        ▼
Create / Validate CEIPAL Requisition
        │
        ▼
Recruiter Assignment
        │
        ▼
Define Candidate Profile
        │
        ▼
Boolean Search Strategy
        │
        ▼
CEIPAL / LinkedIn / Job Boards
        │
        ▼
Candidate Identification
        │
        ▼
Candidate Contact
        │
        ▼
Pre-Screening
        │
        ├── Skills
        ├── Experience
        ├── Location
        ├── Work Authorization
        ├── Rate / Salary
        ├── Availability
        └── Communication
        │
        ▼
Right-to-Represent
        │
        ▼
Recruiter Qualification
        │
        ▼
Lead / Manager Quality Review
        │
        ▼
Client Submission
        │
        ▼
Interview Coordination
        │
        ▼
Client Feedback
        │
        ▼
Offer
        │
        ▼
Placement
        │
        ▼
Onboarding / Closure
```

---

# 17. Recruiter Training Plan

A structured onboarding program should be completed before recruiters are expected to operate independently.

## Week 1 – Foundation

### Day 1

- Company orientation
- Recruitment lifecycle
- Company policies
- Security awareness

### Day 2

- US staffing industry overview
- US geography
- US time zones
- Common staffing terminology

### Day 3

- W2 concepts
- C2C concepts
- Contract staffing
- Contract-to-hire
- Direct hire
- Work authorization awareness

### Day 4

- Job description analysis
- Skill identification
- Candidate persona creation
- Resume screening

### Day 5

- Boolean search
- LinkedIn sourcing
- Job-board sourcing
- Internal database sourcing

## Week 2 – Systems & Production

### Day 6

- CEIPAL user training
- Job requirements
- Candidate records
- Activities and notes

### Day 7

- Candidate calls
- Communication scripts
- Qualification questions
- Rate discussions

### Day 8

- RTR process
- Candidate submission
- Submission quality
- Duplicate candidate handling

### Day 9

- Mock calls
- Mock submissions
- Interview coordination
- Client communication

### Day 10

- Supervised live recruitment
- Quality review
- KPI expectations
- Production readiness assessment

---

# 18. US Shift Planning

Recruiter schedules should be aligned with the target US market and client requirements.

For example, a team primarily servicing Eastern/Central US business hours may operate approximately during an Indian evening/night shift.

US daylight-saving changes must be incorporated into shift planning.

The organization should also establish policies for:

- Night-shift attendance
- Employee transportation if provided/required
- Office security
- Emergency contacts
- Meal/break schedules
- Shift handover
- Late-night infrastructure support

---

# 19. Recruiter Performance KPIs

Recruiters should not be evaluated only by number of calls.

The complete recruitment funnel should be measured.

| KPI | Measurement |
|---|---|
| Requirements worked | Daily / Weekly |
| Candidates sourced | Daily |
| Candidate contacts | Daily |
| Meaningful conversations | Daily |
| Qualified candidates | Daily |
| RTR received | Daily |
| Client submissions | Daily / Weekly |
| Submission → Interview ratio | Percentage |
| Interview → Offer ratio | Percentage |
| Offer → Joining ratio | Percentage |
| Placements | Monthly |
| Time to first submission | Hours |
| Time to fill | Days |
| Candidate response rate | Percentage |
| Candidate database reuse | Percentage |

Quality should be measured together with activity.

---

# 20. Management Dashboard

Management should receive a daily and weekly recruitment dashboard.

Example:

```text
--------------------------------------------------
             RECRUITMENT DASHBOARD
--------------------------------------------------

Open Requirements                         28
Active Candidates                        186
Today's Qualified Candidates              34
Today's Submissions                       21
Interviews Scheduled                       7
Offers                                     3
Placements – Month to Date                 6

--------------------------------------------------
              RECRUITMENT FUNNEL
--------------------------------------------------

Sourced                                  850
   │
   ▼
Contacted                                410
   │
   ▼
Qualified                                126
   │
   ▼
Submitted                                 72
   │
   ▼
Interviewed                               24
   │
   ▼
Offered                                    9
   │
   ▼
Placed                                     6
```

Reports should be available by:

- Recruiter
- Team
- Client
- Requirement
- Technology / skill
- Week
- Month
- Submission status
- Interview status
- Placement

CEIPAL reporting should be used wherever practical to avoid parallel manual reporting systems.

---

# 21. Salary Planning Model

The following figures are budgeting assumptions only and should be validated against the hiring market at the time recruitment begins.

| Position | Qty | Monthly Planning Range |
|---|---:|---:|
| Junior Recruiter | 4 | ₹25,000–₹35,000 each |
| Recruiter | 3 | ₹35,000–₹50,000 each |
| Senior Recruiter / Lead | 1 | ₹55,000–₹75,000 |

### Preliminary recruiter payroll planning

Approximately **₹3.0–3.5 lakh per month** before employer-side costs, incentives, benefits and any separate management/operations staff.

A performance-linked incentive structure should be developed around successful placements and/or realized business outcomes rather than activity alone.

---

# 22. Preliminary One-Time Setup Budget (CAPEX / Setup)

| Category | Preliminary Budget |
|---|---:|
| IT Equipment & Recruiter Hardware | ₹8.00 L |
| Network / Internet Initial Setup | ₹0.50 L |
| Website Design & Development | ₹1.50 L |
| CEIPAL Setup / Implementation Allowance* | ₹1.00 L |
| Job Board / Sourcing Initial Provision* | ₹2.00 L |
| Security / Software Configuration | ₹0.50 L |
| Recruitment / HR / Onboarding | ₹0.50 L |
| Training | ₹0.50 L |
| Contingency | ₹1.00 L |
| **Preliminary Technology & Operational Setup** | **₹15.50 L** |

\* Subject to vendor quotation and selected subscription/contract.

### Recommended planning envelope

**₹15–16 lakh** for initial technology and operational setup.

This does **not** currently include:

- Office rent deposit
- Monthly office rent
- Furniture/interior fit-out
- Company incorporation costs
- Professional legal fees
- US entity setup, if required
- Employee transportation
- Major electrical/HVAC modifications

These should be added after office and legal structure decisions are finalized.

---

# 23. Preliminary Monthly Operating Budget (OPEX)

| Expense | Monthly Planning Budget |
|---|---:|
| 8 Recruiter Salaries | ₹3.0–3.5 L |
| Manager / Operations / Admin if additional | ₹0.5–1.0 L |
| CEIPAL Licensing* | ₹0.5–1.0 L |
| Job Boards / Candidate Sourcing* | ₹1.0–2.0 L |
| US Calling / VoIP | ₹0.2–0.4 L |
| Microsoft 365 / Collaboration | ₹0.10–0.15 L |
| Internet + Static IPs | ₹0.10–0.20 L |
| Security / Cloud / Backup | ₹0.10–0.20 L |
| Electricity / Office Operations | ₹0.20–0.40 L |
| Incentives / Miscellaneous | ₹0.30–0.60 L |
| **Estimated Operating Range Before Rent** | **~₹6–9 L / month** |

\* Vendor pricing and the number/type of licenses can materially change the monthly total.

Office rent, transport and other location-specific expenses should be added separately.

---

# 24. Procurement Strategy

Procurement should be completed in stages rather than purchasing every software subscription immediately.

## Stage 1 – Mandatory before recruiter joining

- Laptops
- Headsets
- Keyboard/mouse
- Network
- Primary and backup internet
- Firewall
- Microsoft 365
- CEIPAL
- Corporate domain/email
- Security tools

## Stage 2 – Before production go-live

- US calling platform
- Required job boards
- LinkedIn sourcing seats
- Website
- Backup platform
- Reporting configuration

## Stage 3 – After utilization data

- Additional job-board seats
- Additional LinkedIn seats
- Advanced CEIPAL modules/integrations
- Additional automation
- Additional recruiter licenses

This avoids unnecessary recurring expenses before the team reaches production.

---

# 25. 60-Day Implementation Plan

## Phase 1 – Business Foundation

### Days 1–7

- Confirm business/legal operating model
- Confirm services
- Confirm target industries
- Confirm initial budget
- Finalize office
- Finalize domain/brand
- Initiate vendor quotations
- Define organization structure

### Deliverable

**Approved business and implementation baseline**

---

## Phase 2 – Infrastructure

### Days 5–15

- Procure laptops
- Procure peripherals
- Install LAN
- Install managed switch
- Configure firewall
- Install primary ISP
- Install backup ISP
- Configure static IPs
- Configure Wi-Fi
- Install UPS
- Configure printer
- Configure conference room

### Deliverable

**Production-ready office infrastructure**

---

## Phase 3 – Software & Security

### Days 10–25

- Configure Microsoft 365
- Configure corporate email
- Implement MFA
- Configure CEIPAL
- Configure users/roles
- Configure recruitment workflow
- Configure VoIP
- Configure job-board integrations
- Configure endpoint security
- Configure backups
- Configure management reports

### Deliverable

**Recruitment technology environment ready for training**

---

## Phase 4 – Website

### Days 10–30

- UI/UX design
- Website development
- Employer pages
- Candidate pages
- Jobs section
- Resume/application functionality
- Privacy pages
- Contact/enquiry forms
- Analytics
- CEIPAL integration where applicable
- Testing
- Production deployment

### Deliverable

**Public company recruitment website**

---

## Phase 5 – Recruiter Hiring

### Days 10–30

- Define recruiter job descriptions
- Source candidates
- Conduct interviews
- Recruitment assessments
- Select 8 recruiters
- Complete offers
- Background/document checks as applicable
- Confirm joining dates

### Deliverable

**Initial recruitment team onboarded**

---

## Phase 6 – Training

### Days 25–40

- US staffing training
- CEIPAL training
- Sourcing training
- Job-board training
- Calling training
- Security training
- Compliance training
- Mock calls
- Mock submissions

### Deliverable

**Production-ready recruiters**

---

## Phase 7 – Controlled Production

### Days 41–50

- Begin live requirements
- Manager reviews submissions
- Monitor recruiter calls
- Review candidate quality
- Validate CEIPAL usage
- Measure initial KPIs
- Correct workflow issues

### Deliverable

**Controlled live recruitment operation**

---

## Phase 8 – Full Production

### Days 51–60

- All recruiters enter production
- Daily dashboard begins
- Weekly management review begins
- Client SLA measurement begins
- Recruiter KPI reporting begins
- Continuous improvement process begins

### Deliverable

**Full production go-live**

---

# 26. 30 / 60 / 90-Day Operating Objectives

## First 30 Days

Primary objective: **Build the foundation**

- Infrastructure operational
- CEIPAL configured
- Corporate communication operational
- Recruiters hired
- Website under development / launched
- SOPs documented

## By Day 60

Primary objective: **Production go-live**

- 8 recruiters operational
- Requirements managed through CEIPAL
- Candidate communication operational
- Job boards active
- Management dashboard operational
- Submission quality controls active

## By Day 90

Primary objective: **Optimize performance**

Management should review:

- Cost per recruiter
- Cost per submission
- Submission quality
- Interview ratios
- Placement ratios
- Job-board utilization
- CEIPAL utilization
- Recruiter productivity
- Client response times
- Candidate response rates
- Recurring software costs

Low-utilization subscriptions should be reduced and high-performing sourcing channels expanded.

---

# 27. Automation Roadmap

The company should use CEIPAL as its initial recruitment platform rather than attempting to build a custom ATS before operational processes are understood.

However, the surrounding recruitment lifecycle should be designed with future automation in mind.

```text
                   CLIENT / VMS
                        │
                        ▼
                   REQUIREMENT
                        │
                        ▼
                ┌──────────────┐
                │    CEIPAL    │
                └──────┬───────┘
                       │
                       ▼
            Requirement Analysis
                       │
           ┌───────────┼───────────┐
           │           │           │
           ▼           ▼           ▼
       Job Boards   LinkedIn   CEIPAL Database
           │           │           │
           └───────────┼───────────┘
                       │
                       ▼
               Candidate Matching
                       │
                       ▼
                Recruiter Review
                       │
                       ▼
              Email / Call / SMS
                       │
                       ▼
                 Pre-Screening
                       │
                       ▼
                   Submission
                       │
                       ▼
                   Interview
                       │
                       ▼
               Offer / Placement
                       │
                       ▼
                Analytics & KPIs
```

Potential future automation opportunities include:

- Automated requirement parsing
- AI-based skill extraction
- Candidate matching/scoring
- Candidate rediscovery from CEIPAL
- Automated recruiter task creation
- Email sequence automation
- Interview scheduling
- Candidate follow-up reminders
- Submission quality checks
- Duplicate candidate detection
- Recruiter productivity analytics
- Client response tracking
- Automated daily/weekly management reports

The recommended approach is to operate CEIPAL for approximately **3–6 months**, collect actual operational data and then identify the highest-value automation opportunities.

---

# 28. Operational Governance

The following management rhythm is recommended.

## Daily

- Team stand-up
- Priority requirements
- Candidate/submission review
- Blocker resolution
- CEIPAL data-quality check

## Weekly

- Recruiter KPI review
- Requirement aging
- Submission-to-interview ratios
- Client feedback
- Job-board utilization
- Placement pipeline

## Monthly

- Recruiter performance
- Client performance
- Revenue / placement analysis
- Software utilization
- Job-board ROI
- Security/access review
- Hiring requirements
- Capacity planning

## Quarterly

- Vendor review
- CEIPAL utilization review
- Automation opportunities
- Security review
- Client concentration risk
- Hiring/expansion decision

---

# 29. Scalability Plan

The initial infrastructure should be designed for eight recruiters but avoid unnecessary redesign when the company grows.

### Stage 1

**8 recruiters**

Focus on process standardization and initial client delivery.

### Stage 2

**15–20 recruiters**

Potential additions:

- Dedicated team leads
- Dedicated HR/admin
- Additional CEIPAL licenses
- Additional calling capacity
- Additional sourcing licenses
- Expanded network switch/AP capacity

### Stage 3

**25–50+ recruiters**

Consider:

- Dedicated operations manager
- Dedicated IT/security administration
- Recruitment pods by client/technology
- Dedicated sourcing team
- Business development team
- Automated reporting/data warehouse
- Advanced workflow automation
- Formal security/compliance program

---

# 30. Key Decisions Required Before Procurement

The following decisions should be finalized before locking the budget:

1. Final office location and capacity
2. Whether all 8 positions are recruiters or one is a team lead
3. Target US recruitment industries
4. IT-only vs IT + non-IT recruitment
5. Client / MSP / VMS business model
6. CEIPAL modules and final user count
7. Job-board selection
8. Number of LinkedIn premium sourcing seats
9. US calling provider
10. Microsoft 365 license type
11. Website integration depth with CEIPAL
12. Primary and secondary ISP
13. Employee transportation policy for night shifts
14. Security/EDR platform
15. Office furniture and interior requirements
16. Legal structure for India/US operations

---

# 31. Cost Summary

## Initial technology and operational setup

**Planning range: ₹15–16 lakh**

Excludes office rent/deposit, major interiors/furniture and legal/entity setup.

## Monthly operating expense

**Planning range before office rent: approximately ₹6–9 lakh/month**

The largest variables are:

- CEIPAL licensing
- Job-board subscriptions
- LinkedIn licensing
- Recruiter compensation
- Management staffing
- Calling usage

Final commercial budgeting should therefore be completed after quotations from CEIPAL, sourcing vendors, ISP providers and the selected telephony provider.

---

# 32. Success Criteria

The initial implementation can be considered successful when:

- 8 recruiters are fully operational
- All recruiters use CEIPAL consistently
- Every requirement is tracked centrally
- Candidate activity is recorded centrally
- US calling is stable
- Internet failover is operational
- Candidate data is secured
- Recruitment SOPs are followed
- Management receives reliable KPI reports
- Submission quality is measurable
- Client feedback is tracked
- Recruitment funnel conversion is visible
- Infrastructure can support planned expansion

---

# 33. Recommended Next Steps

Immediately after approval of this plan:

1. Finalize the legal/business operating model.
2. Confirm office premises and seating capacity.
3. Obtain quotations for laptops and infrastructure.
4. Obtain two business ISP quotations with static IPs.
5. Finalize CEIPAL licensing and implementation scope.
6. Evaluate US VoIP providers.
7. Finalize initial job-board subscriptions.
8. Finalize Microsoft 365 licensing.
9. Start website design and development.
10. Begin recruiter hiring.
11. Prepare detailed recruitment SOPs.
12. Prepare security and employee policies.
13. Configure CEIPAL workflows and reporting.
14. Conduct recruiter training.
15. Start controlled production.
16. Review operations at 30, 60 and 90 days.

---

# 34. Conclusion

The proposed approach establishes more than an eight-person recruitment office. It creates a structured foundation for a scalable US recruitment business.

The initial priority is to establish reliable infrastructure, implement **CEIPAL as the central recruitment platform**, hire and train the recruitment team, standardize recruitment processes, protect candidate information and make management performance measurable from the first day of production.

Once the operation has accumulated sufficient real-world recruitment data, automation can be introduced around CEIPAL to reduce repetitive work, improve candidate matching, accelerate submissions and provide stronger management intelligence.

This phased approach minimizes unnecessary early investment while establishing the technical and operational foundation required for future growth.

---

## Document Notes

- Currency values are shown in Indian Rupees (₹) unless otherwise specified.
- Costs are preliminary planning estimates and are not vendor quotations.
- Taxes, implementation fees and contract-specific charges may apply.
- Software licensing should be validated directly with vendors before commercial approval.
- Legal, employment, privacy and regulatory requirements should be validated by appropriately qualified professionals for the final operating model.

---

**End of Document**
