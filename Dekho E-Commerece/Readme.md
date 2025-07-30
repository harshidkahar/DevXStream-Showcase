# 🛒 Dekho – Unified Buyer & Seller Live Commerce Platform

**Dekho** is a role-based live shopping and social commerce platform designed for seamless buying, selling, and live auction experiences — all within a **unified mobile app**. It features a powerful **admin panel built with ASP.NET**, a **scalable backend (Clean Architecture)**, and a real-time, event-driven architecture for streaming and bidding.

---

## 🧩 Key Features

- ✅ Single mobile app for Buyers & Sellers with role-switch toggle
- 📦 Product Listings, Auctions, Live Streaming
- 🔁 Real-time Bidding and Chat
- 🔐 KYC-based Seller Access
- 💰 Razorpay Checkout
- 🔔 Push Notifications with Firebase
- 🧑‍💼 Admin Panel to manage KYC, streams, payouts, reports, and referrals

---

## 🔧 Tech Stack Overview

| Layer       | Tech Stack                                    |
|-------------|-----------------------------------------------|
| **Mobile App** | React Native (Expo), Redux, Axios             |
| **Admin Panel** | ASP.NET Razor Pages (Frontend)               |
| **Backend API** | ASP.NET Core Web API (Clean Architecture)    |
| **Database**   | PostgreSQL / SQL Server                      |
| **Realtime**   | SignalR (Chat, Bids)                         |
| **Streaming**  | MUX / Agora SDK                             |
| **Storage**    | Azure Blob / AWS S3                          |
| **Auth**       | Firebase OTP (mobile), JWT (backend)         |
| **Payments**   | Razorpay (India), Stripe (optionally global) |
| **Notifications** | Firebase Cloud Messaging (FCM)         |
| **CI/CD**      | GitHub Actions, Docker (optional)            |

---

## 👥 User Roles & App Modes

### 🔹 Buyer (Default)
- Browse live shows, auctions, and products
- Add-to-cart, checkout via Razorpay
- Participate in giveaways (spin the wheel)
- Receive notifications, view order history

### 🔸 Seller (Post-KYC)
- Go Live with product pinning
- Add/manage products
- Track earnings and order stats
- Trigger giveaways, flash drops

### 🔐 Admin (ASP.NET Web App)
- Approve/Reject KYC applications
- View/manage users, products, streams
- Trigger payouts and campaigns
- Send push notifications and referrals

---

## 🧑‍💻 Mobile App (React Native)

- Built using Expo (React Native)
- Modular architecture: components, hooks, screens
- Role-based UI toggle (`useUserRole()` hook)
- Feature-gating for Seller tools post-KYC approval

### 🧩 Key Screens
- Login (OTP via Firebase)
- Buyer: Explore, Live Shows, Products, Checkout, Wheel Spin
- Seller: Go Live, Dashboard, Manage Products
- Shared: Profile, Notifications, Toggle Role

---

## 🖥️ Admin Panel (ASP.NET Razor Pages)

### 🔧 Tech Overview
- Built using **ASP.NET Razor Pages or MVC**
- Runs as a separate web project (in same solution or as sibling project)
- Communicates with **shared ASP.NET Core Web API**
- Secured using Admin-only JWT or cookie-based auth

### 📋 Features
| Feature            | Description                             |
|--------------------|-----------------------------------------|
| Dashboard          | Summary stats (users, sales, streams)   |
| KYC Approvals      | View submitted IDs & selfies            |
| User Management    | View, ban/unban users, assign roles     |
| Product Moderation | Review reported items, delete/block     |
| Stream Monitoring  | View live/recorded shows                |
| Payouts            | Approve & track seller payouts          |
| Notifications      | Push campaigns to buyers/sellers        |
| Referrals          | Manage and track referral codes         |

---

## 🔙 Backend (ASP.NET Core – Clean Architecture)

### 🧱 Project Structure
```
/Dekho.Backend
/API --> Controllers & Endpoints
/Application --> Use Cases, Services, DTOs
/Domain --> Entities, Enums, Interfaces
/Infrastructure --> Storage, Razorpay, FCM, MUX
/Persistence --> EF Core or Dapper DB Integration

/Dekho.AdminPanel
--> Razor Pages or MVC Frontend (secured admin UI)

/Dekho.MobileApp
--> React Native project (Expo)
```


### 🔐 Auth & Roles
- Firebase OTP → JWT issued by backend
- Claims: `role: buyer | seller | admin`, `isKYCApproved`
- Middleware validates access at API level

### 🌐 Core APIs
| Area         | Endpoints                              |
|--------------|----------------------------------------|
| Auth         | /auth/login, /auth/token                |
| User & KYC   | /users/me, /users/kyc, /admin/users     |
| Products     | /products, /products/upload             |
| Streaming    | /streams/start, /streams/metadata       |
| Bidding/Chat | /bids, /chat (SignalR endpoints)        |
| Orders       | /checkout, /orders, /webhooks/razorpay |
| Notifications| /notifications/send                    |

---

## 🔁 Realtime Features

- **SignalR Hub** for live bidding & chat
- Seller hosts stream via MUX/Agora
- Bids + messages emitted and broadcasted to viewers in real-time
- Backend saves live logs and metrics

---

## 💸 Payments

- Razorpay SDK for in-app mobile checkout
- Backend handles payment intents and webhooks
- Seller payouts via admin panel
- Stripe optional for global payments

---

## 🔔 Push Notifications

- Firebase Cloud Messaging (FCM)
- Tokens stored post-login
- Backend triggers notifications via Admin or events

---

## 📦 Storage & Media

| Media        | Storage Layer            |
|--------------|--------------------------|
| Product Images | Azure Blob / AWS S3    |
| Stream Metadata | MUX/Agora Webhooks    |
| ID/Docs (KYC) | Secured private blob    |

---

## 🛠 DevOps & Deployment

| Component      | Deployment Target         |
|----------------|----------------------------|
| Mobile App     | Android & iOS Stores       |
| Backend API    | Azure / DigitalOcean VPS   |
| Admin Panel    | IIS / Azure Web App        |
| CI/CD Pipeline | GitHub Actions (multi-env) |
| SSL            | Let's Encrypt / Azure SSL  |

---

## 📅 Project Phases & Timeline

### ✅ **Phase 1: MVP (0–2 Months)**
- Buyer flow (Explore, Checkout, Live View)
- Razorpay integration
- KYC UI (no approval flow)
- Admin login and base dashboard

### ✅ **Phase 2: Seller Tools (2–4 Months)**
- KYC approval workflow
- Seller dashboard, Go Live, Add Products
- Admin: KYC, product moderation, stream logs

### ✅ **Phase 3: Growth & Monetization (5–6 Months)**
- Push campaigns, referral system
- Coins/tips economy
- Analytics dashboard (admin + seller)
- Deep linking, admin view emulation

---

## 📁 Repository Structure
```
/dekho-backend --> ASP.NET Core backend
/dekho-app --> React Native mobile app
/dekho-admin --> ASP.NET Razor Pages web app
/docs --> Architecture, API specs, UI/UX
```


---

## 🔐 Security Considerations

- JWT with role claims & short TTL
- Role-based API middleware protection
- KYC media stored in secure private containers
- All admin actions logged
- API rate-limiting + validation middleware

---

## ✅ Status

| Area            | Status         |
|-----------------|----------------|
| Project Setup   | ✅ Complete     |
| UI/UX Designs   | ✅ In Progress  |
| MVP Dev         | 🔄 Ongoing      |
| Admin Panel     | 🔄 Ongoing      |
| API Integration | 🔄 Ongoing      |

---

## 🧠 Next Steps

- [ ] Define Low-Level Architecture (Entity Models, DB Schema, API Contracts)
- [ ] Finalize Admin Panel routes and access control
- [ ] Start frontend/backend integration testing
- [ ] Setup build & deployment environments

---

## 👨‍💻 Contributors

- **Mobile Developer**: React Native Developer  
- **Backend API**: ASP.NET Core Developer  
- **Admin Panel**: ASP.NET Razor Developer  
- **Project Manager**: Harshid Kahar  
- **DevOps/Infra**: (Optional or Shared Resource)

---

> For technical support or onboarding help, contact the DevXStream team at **devxstream@support.com** or open an issue in this repo.
