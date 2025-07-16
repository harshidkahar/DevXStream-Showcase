# 🧾 Agent Portal & NSDL Account Opening System

A complete end-to-end solution for managing Business Correspondents (BCs), Agents, Wallets, and NSDL Bank Account Opening workflows. This portal streamlines agent onboarding, wallet top-ups, document management, and integrates seamlessly with the NSDL API for secure Aadhaar-based account registrations.

---

## 🚀 Features

### 🔐 Authentication & Roles
- Secure login with JWT tokens
- Role-based access: Admin, Distributor, Agent

### 👨‍💼 Agent Management
- Agent and distributor onboarding
- KYC document collection & approval
- Agent status tracking and wallet assignment

### 💰 Wallet System
- Recharge & debit agent wallet
- Transaction history and balance monitoring
- Admin-controlled credit distribution

### 🏦 NSDL Integration
- Aadhaar-based bank account creation
- Secure encryption & decryption for NSDL APIs (AES + PKCS#7)
- Request/response XML communication
- Real-time status tracking for submitted requests

### 📊 Dashboard & Admin Panel
- Real-time insights into agent activity
- Approve/reject onboarding requests
- Filter by district/state/distributor

---

## 🧱 Tech Stack

| Layer         | Technology                         |
|---------------|------------------------------------|
| Backend       | ASP.NET Core (.NET 9)            |
| Architecture  | Clean Architecture + CQRS          |
| ORM           | Dapper                             |
| Database      | SQL Server                         |
| Auth          | JWT Bearer Tokens                  |
| NSDL Crypto   | AES 128 CBC + PKCS#7 Padding       |
| API           | RESTful APIs                       |

---

## 🗂️ Project Structure

```
Agent-Portal-And-NSDL-Account-Opening-System/
├── 📦 GILAgent.API             # API Host project
├── 🧠 GILAgent.Application     # Application layer (CQRS, Handlers, DTOs)
├── 🧱 GILAgent.Domain          # Domain models and entities
├── 🧰 GILAgent.Infrastructure  # Repositories, Services, NSDL Integration, UnitOfWork, Dapper
├── 🧩 GILAgent.Common          # Shared Settings, Errors & Utility Functions
└── 📄 README.md                # Project documentation
```


---

## ⚙️ Getting Started

### 📥 1. Clone the Repo

```bash
git clone https://github.com/harshidkahar/Agent-Portal-And-NSDL-Account-Opening-System.git
cd Agent-Portal-And-NSDL-Account-Opening-System
```

🛠 2. Configure the Environment
Create an appsettings.json file inside the GILAgent.API project directory.

Paste the following and update the values as per your environment:

```
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",

  "ConnectionStrings": {
    "DefaultConnection": "Server=YourServerName;Database=DBName;User Id=UserName;Password=Password;TrustServerCertificate=True"
  },

  "JwtSettings": {
    "Secret": "YourSuperSecureKeyForJWTGeneration1234",
    "Issuer": "Issuer",
    "Audience": "Audience",
    "ExpiryMinutes": 60,
    "RefreshTokenValidityInDays": 30
  },

  "Serilog": {
    "MinimumLevel": "Information",
    "WriteTo": [
      { "Name": "Console" }
    ]
  },

  "SmtpSettings": {
    "Host": "smtp.gmail.com",
    "Port": 465,
    "UserName": "your@email.com",
    "Password": "your_password",
    "FromAddress": "abc@gmail.com",
    "FromName": "Agent Portal"
  },

  "Razorpay": {
    "Key": "rzp_test_4vEUSEcZpRw8sE",
    "Secret": "fSnCWgMnBX8exvFZ9taVkpMn",
    "WebhookSecret": "https://localhost:7289/api/wallet/payment-webhook"
  },

  "NSDL": {
    "BaseUrl": "https://agentbanking.nsdlbank.co.in/bcagentregistrationapi/default.aspx",
    "ChannelId": "YourChannelId",
    "AppId": "com.jarviswebbc.nsdlpb",
    "PartnerId": "YourPartnerId",
    "EncryptionKey": "YourEncryptionKey",
    "FetchCustomerApiUrl": "https://jiffyuat.nsdlbank.co.in/jarvisgwy/fetchpartnercustomer",
    "BCID": "YourBCID",
    "OpenAccountCallBackURL": "https://your-frontend-domain.com/nsdl/callback"
  },

  "AllowedOrigins": [
    "http://localhost:85",
    "https://your-angular-domain.com"
  ]
}
```

▶️ 3. Run the Application
# From solution root
dotnet build
dotnet run --project GILAgent.API


🔐 NSDL Integration Overview
The system supports integration with NSDL API for partner/customer registration, using:
```
AES 128-bit encryption (CBC mode)
PKCS#7 padding
XML-based request/response
Encrypted payloads using certificates
```
You can find the logic in:
```
GILAgent.Application
├── Helper/
    └── EncryptionHelper.cs
├── Services/
    └── NsdlApiService.cs
```
Implements XML serialization/deserialization for request/response

Handles:
```
Partner Registration
Customer Onboarding
Document Upload
Status Tracking
Ensure that encryption certificates are configured in GILAgent.Application.Helper module.
```

🛠 TODO / Upcoming Features
```
✅ Role-based dashboard analytics
⏳ PDF generation for NSDL forms
⏳ Email/SMS Notifications
⏳ Multilingual support
```
👨‍💻 Author
```
Name: Harshid Kahar	
Role: Architect & Lead Developer
📧 harshidkahar@gmail.com
This project is licensed under the MIT License - see the LICENSE file for details.
```
🙏 Acknowledgements
```
NSDL API Team (for integration guidelines)
Dapper ORM community
.NET Core Clean Architecture contributors
```
📬 Contact
```
For queries or implementation support:
Email: harshid10789@gmail.com / harshidkahar@gmail.com
LinkedIn: Harshid Kahar: https://www.linkedin.com/in/harshidkahar/
```
