# 🧾 AITT — On‑Chain AI Transparency Verification System

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
* 💾 **Persistent File Storage:** Secure local storage on VPS via Docker volumes.
* ⚙️ Smart Contract Integration via Backend Signing
* 🚀 **Automated CI/CD:** Full pipeline from GitHub to Production.
* 🔒 **Auto-SSL:** Automatic HTTPS provisioning via Let's Encrypt.

## ⚙️ Setup (Local Development)

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

## 🚢 Deployment & Infrastructure (Production)

The project utilizes a robust **Docker-based** infrastructure with a fully automated **CI/CD pipeline**.

### Architecture
* **Containerization:** Frontend (Nginx static serve) and Backend (Node.js) are built as Docker images and stored in **GitHub Container Registry (GHCR)**.
* **Reverse Proxy:** Uses `nginx-proxy` and `acme-companion` to automatically route traffic and manage SSL certificates.
* **Persistence:** Uploaded documents are stored on the host VPS (`/uploads`) and mounted into the backend container (`/data`) to ensure data persists across deployments.

### CI/CD Workflow (GitHub Actions)
1.  **Build:** Commits to `main` trigger parallel builds for Frontend and Backend.
2.  **Publish:** Optimized images are pushed to GHCR.
3.  **Deploy:** The pipeline securely connects to the VPS via SSH to:
    *   Update the `docker-compose.yml` configuration.
    *   Apply per-vhost Nginx settings (e.g., upload limits).
    *   Pull new images and restart containers with zero-downtime logic (where applicable).

## 🔗 Smart Contract Details

* **Contract ID:** `CC4PAMOJ75KHHK75D7XGJ4FDLNE27L674W5CUNRKTH4BMGARXR6QMQU7`

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
* **Infrastructure:** Docker, Docker Compose, Nginx Proxy, Let's Encrypt
* **CI/CD:** GitHub Actions, GHCR
* **Hashing:** SHA-256
* **Auth:** Role-based JWT
 

## 🪪 License

This project is licensed under the **MIT License**.