+++
title = "Blockchain-Based E-KYC System"
date = 2023-05-05
description = "Blockchain-Based E-KYC System"
github = "https://github.com/patkarmandar/E-KYC" # Optional
demo = "" # Optional
tags = ["blockchain", "ethereum", "application"]
categories = ["web"]
featured = true
+++

The Blockchain-Based E-KYC System is a decentralized identity verification platform built on Ethereum that enables secure, tamper-proof, and reusable KYC records.

It eliminates repeated KYC processes by maintaining a central blockchain-based KYC registry controlled by a governing authority, allowing financial institutions to verify customers without duplicating verification efforts.

### Tech Stack
- Blockchain Platform: Ethereum
- Smart Contracts: Solidity
- Blockchain Tools: Truffle, Ganache
- Web3 Integration: Web3.js
- Wallet: MetaMask
- Backend: Node.js
- Frontend: React.js

### Key Highlights
- Decentralized E-KYC platform built on Ethereum
- Government-controlled central KYC registry on blockchain
- Cryptographically secure and tamper-proof KYC records
- Eliminates redundant re-KYC across multiple organizations
- Transparent, auditable, and trust-minimized system

### Features
- KYC Registry Management
    - Financial institutions and organizations can add customer KYC records to the blockchain-based registry.
    - KYC records are stored immutably using smart contracts.
- KYC Request Workflow
    - Organizations can request KYC access from customers.
    - Customers can view, approve, or deny KYC requests using their wallet.
    - All approvals and denials are recorded on-chain.
- Customer Control & Consent
    - Customers retain full control over their KYC data.
    - Consent is enforced through smart contracts, ensuring transparency and trust.
- KYC Verification & Reuse
    - Organizations can verify existing KYC records directly from the blockchain.
    - Prevents repeated KYC for the same customer across different institutions.
    - Reduces onboarding time and operational overhead.

### Prerequisites
- Node.js & npm
- Ganache (local Ethereum blockchain)
- MetaMask browser wallet
- Truffle (for compiling & deploying contracts)

### Installation
1. Clone the Repository
    ```
    git clone https://github.com/patkarmandar/E-KYC.git
    cd E-KYC
    ```
2. Install Dependencies (Smart Contracts & Backend)
    ```
    npm install
    ```
3. Start a Local Blockchain
    - Open Ganache (GUI or CLI).
    - Ensure the network RPC endpoint is set to default: `http://127.0.0.1:7545`
4. Configure MetaMask
    - Install MetaMask extension in your browser.
    - Add a new network -> Custom RPC with:
        - RPC URL: http://127.0.0.1:7545
        - Chain ID: 1337 (or Ganache network ID)
    - Import one account from Ganache using its private key.
5. Compile & Deploy Smart Contracts
    ```
    npx truffle compile
    npx truffle migrate --reset
    ```
6. Run the Frontend (React)
    - Open a new terminal inside the project:
    ```
    cd client
    npm start
    ```
    - This starts the React UI on: `http://localhost:3000`
7. Make sure Truffle config (truffle-config.js) network settings point to Ganache’s host and port.
