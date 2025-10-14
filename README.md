# 🧾 AITTsoroban — On‑Chain AI Transparency Verification System

A complete end-to-end platform for **secure document verification** using the **Soroban smart contract**, **ExpressJS backend**, and **React dashboard**.

## 📂 Project Structure

```
root/
│
├── smart-contract/      # Soroban smart contract (Rust)
│   └── lib.rs
│
├── backend/             # ExpressJS server (API + DB + blockchain integration)
│   ├── src/
│   └── .env.example
│
└── frontend/            # React dashboard (JWT auth + upload + verify)
    ├── src/
    └── .env.example
```

## 🚀 Overview

This project enables **uploading, storing, and verifying file hashes (SHA-256)** on-chain via the Soroban network.

### Components

* **Smart Contract (Soroban):**  Stores and verifies file hashes on-chain with whitelist-controlled upload access.
* **Backend (ExpressJS):**  Handles authentication, file hashing, DB storage, and contract interactions.
* **Frontend (React Dashboard):**  UI for users, regulators, and admins to register, upload, verify, and manage roles.

## 🔑 Features

* ✅ Role-based JWT Authentication (Company / Regulator / Super Admin)
* 🧾 File Hashing (SHA-256) and On-Chain Storage
* 🔍 Public File Verification by Hash
* 👨‍💼 Admin Dashboard for Role Promotion and Management
* 💾 Local/Cloud File Storage
* ⚙️ Smart Contract Integration via Backend Signing

## ⚙️ Setup

### 1. Clone Repository

```
git clone https://github.com/<your-username>/AITTsoroban.git
cd AITTsoroban
```

### 2. Install Dependencies

```
cd backend && npm install
cd ../frontend && npm install
```

### 3. Environment Configuration

```
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env
```

### 4. Run Services

```
# Terminal 1
cd backend
npm run dev

# Terminal 2
cd frontend
npm start
```

## 🔗 Smart Contract Details

* **Contract ID:** `CBOCCS4EYS5WV273UJRHBM6QN4NGBV5Y4EGKON3UYBBEQ62LVHV3ZMLS`

## 🧠 Roles Overview

| Role         | Permissions                             |
| ------------ | --------------------------------------- |
| Company User | Register, view, and verify documents    |
| Regulator    | Upload verified docs to chain           |
| Super Admin  | Full control, whitelist, and promotions |

## 🧩 Tech Stack

* **Smart Contract:** Soroban (Rust)
* **Backend:** Node.js, Express, MongoDB
* **Frontend:** React, JWT, TailwindCSS
* **Hashing:** SHA-256
* **Auth:** Role-based JWT


## 🪪 License

This project is licensed under the **MIT License**. 
