

# 🗳️ Decentralized Voting System Using Ethereum Blockchain

## 📌 Introduction

The Decentralized Voting System is a blockchain-based application that provides a secure, transparent, and tamper-proof platform for conducting elections. Built on the Ethereum blockchain, this project uses smart contracts to ensure that votes are immutable and only registered users are allowed to participate in the voting process. It combines the power of blockchain with web technologies and a traditional backend to create a complete end-to-end digital voting system.

---

## 🎯 Purpose & Goals

- ✅ Ensure **secure and tamper-proof** elections
- ✅ Enable **real-time, transparent** result monitoring
- ✅ Restrict voting to **authorized users** only
- ✅ Prevent **double voting** or vote manipulation
- ✅ Build a **decentralized**, auditable election platform

---

## 🛠️ Tools and Technologies Used

| Layer            | Technology                         |
|------------------|-------------------------------------|
| **Blockchain**   | Ethereum (Ganache local blockchain) |
| **Smart Contract**| Solidity                            |
| **Development**  | Truffle framework                   |
| **Front-end**    | HTML, CSS, JavaScript, Web3.js      |
| **JS Bundling**  | Browserify                          |
| **Wallet**       | MetaMask                            |
| **Backend API**  | Python (FastAPI)                    |
| **Database**     | MySQL                               |
| **Web Server**   | Node.js                             |

---

## ⚙️ Installation & Setup Instructions

### 1️⃣ Install Required Software

Ensure the following are installed:
- Node.js and npm
- Python 3.8+ and pip
- MySQL Server
- Git (for code management)
- Ganache (local blockchain)
- MetaMask (browser extension)

---

### 2️⃣ Project Setup

#### 🧩 Install Node Dependencies

```bash
npm install
npm install -g truffle
npm install -g browserify
````

#### 🐍 Install Python Dependencies

```bash
pip install fastapi uvicorn[standard] mysql-connector-python pydantic python-dotenv PyJWT
```

---

### 3️⃣ MySQL Database Setup

1. Open MySQL terminal:

```bash
mysql -u root -p
```

2. Create database and table:

```sql
CREATE DATABASE voter_db;
USE voter_db;

CREATE TABLE voters (
    voter_id VARCHAR(36) PRIMARY KEY NOT NULL,
    role ENUM('admin', 'user') NOT NULL,
    password VARCHAR(255) NOT NULL
);

INSERT INTO voters VALUES
('123e4567-e89b-12d3-a456-426614174000', 'admin', 'adminpass'),
('987f6543-e21a-45d9-b456-426614174111', 'user', 'userpass');
```

---

### 4️⃣ Set Up `.env` File

Create a `.env` file inside `Database_API/` folder:

```
MYSQL_USER=root
MYSQL_PASSWORD=your_mysql_password
MYSQL_HOST=127.0.0.1
MYSQL_DB=voter_db
SECRET_KEY=somerandomkey
```

---

### 5️⃣ Start Ganache and Setup Workspace

1. Open Ganache GUI
2. Create new workspace named `development`
3. Add `truffle-config.js` as Truffle Project
4. Start the workspace

---

### 6️⃣ Compile and Migrate Smart Contracts

```bash
truffle compile
truffle migrate
```

---

### 7️⃣ Bundle Front-end JavaScript

Use Command Prompt (not PowerShell):

```bash
browserify src/js/app.js -o src/dist/app.bundle.js
browserify src/js/login.js -o src/dist/login.bundle.js
```

---

### 8️⃣ Run the Servers

#### 🔌 Start FastAPI Server

```bash
cd Database_API
uvicorn main:app --reload --host 127.0.0.1
```

Leave this terminal open.

#### 🌐 Start Node.js Web Server

```bash
cd ../
node index.js
```

---

### 9️⃣ Configure MetaMask

1. Open MetaMask
2. Add network:

   * **Network Name:** Localhost 7545
   * **RPC URL:** [http://localhost:7545](http://localhost:7545)
   * **Chain ID:** 1337
   * **Currency Symbol:** ETH
3. Import accounts from Ganache using private keys

---

### 🔟 Open the DApp

Open your browser and go to:

```
http://localhost:8080
```

#### 🧑‍💼 Admin Login

```
Voter ID:   123e4567-e89b-12d3-a456-426614174000
Password:   adminpass
```

#### 🙋‍♂️ User Login

```
Voter ID:   987f6543-e21a-45d9-b456-426614174111
Password:   userpass
```

---

## ✅ Features

* Admin can:

  * Add candidates
  * Set voting period
  * Monitor voting results

* Voters can:

  * Log in securely
  * View candidates
  * Vote only once
  * View voting status

---

## 📢 Notes

* All votes are recorded on the Ethereum blockchain
* Only authorized voters (stored in MySQL) can participate
* Each wallet address can vote only once
* Backend APIs handle voter login and verification

---


