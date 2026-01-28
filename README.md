# ROOTSTOCK ATM

Decentralized, Multi-Currency rBTC Integration for K1 Lightning ATMs

## 1. Executive Summary

K1, a fintech innovator based in El Salvador, operates a network of Bitcoin Lightning ATMs that provide users with direct, cash-based access to Bitcoin.

This proposal seeks support from the Rootstock Collective (or interested software developer) to develop and deploy a decentralized, multi-currency software upgrade for K1’s ATM platform—enabling customers worldwide to buy rBTC (Rootstock Bitcoin) directly with local cash.

Each ATM will operate independently, with its own wallet and on-chain transaction management, ensuring full decentralization. The new system will support local fiat currencies (e.g., USD in El Salvador, EUR in Europe) and use the ATM’s built-in camera to scan the user’s RSK wallet QR code from their mobile phone—providing a simple, intuitive, and non-custodial user experience.

A complementary dashboard application will allow operators to configure each ATM, monitor transactions, and manage wallets while maintaining the decentralized nature of the network.

This initiative expands real-world accessibility to the Rootstock ecosystem and advances Bitcoin-based DeFi adoption at the grassroots level.

--- 

## 2. Background

K1 Overview

Website: https://k1.sv

Headquarters: San Salvador, El Salvador

ATM Network: 150 units in operation, expanding internationally

Current capability: Bitcoin and Lightning transactions (cash-based)

K1’s mission is to make Bitcoin and blockchain-based finance accessible to everyone.

As K1 expands beyond El Salvador, local currency integration becomes essential.

Each ATM will be pre-configured for its regional currency (e.g., Euros in the EU, USD in the Americas, etc.), allowing seamless integration with local markets and compliance environments.

By introducing rBTC purchasing capabilities, K1 connects physical cash economies directly to Rootstock’s smart contract layer, unlocking Bitcoin-native DeFi for unbanked and cash-preferring populations.

---

## 3. Project Objective

To design, develop, and deploy a decentralized, multi-currency ATM software system that enables:

- Cash-to-rBTC transactions, using local fiat currencies.

- QR code wallet scanning via built-in ATM camera.

- Independent ATM operation, with each device running its own wallet.

- Decentralized configuration and monitoring via a secure dashboard.

The resulting network will be modular, open, and globally deployable - empowering anyone to access rBTC directly using cash without intermediaries.

---

## 4. Technical Design Overview

**Decentralized ATM Architecture**

Each ATM will run its own rBTC wallet managed via a lightweight Rootstock node or SDK.

Transactions are signed and broadcast directly from the ATM.

Private keys remain local to each ATM; no central custody or routing.

Wallets use HD key derivation for secure backups and rotation.


**Multi-Currency Configuration**

Each ATM is pre-configured for local currency (e.g., USD, EUR, GBP, MXN).

Exchange rates sourced from reliable oracles or APIs (e.g., CoinGecko, Rootstock oracles).

Operators can adjust fee margins, rate sources, and localization via the dashboard.

**QR Code Wallet Scanning**

The ATM’s built-in camera is used to scan the user’s RSK wallet QR code.

The system extracts the on-chain address and confirms validity before proceeding.

Eliminates manual address entry, improving user experience and accuracy.

**Operator Dashboard**

A secure, decentralized dashboard application will provide:

ATM registration and configuration (currency, exchange source, wallet info).

Transaction monitoring and reconciliation.

Real-time status indicators (uptime, balances, errors).

Encrypted communication with ATMs for management without centralized control.

**Transaction Flow**

User selects “Buy rBTC” at the ATM.

ATM fetches current exchange rate for local currency → rBTC.

User inserts local cash.

User presents RSK wallet QR code via mobile wallet app.

ATM scans code and verifies address.

ATM executes and broadcasts an on-chain rBTC transaction.

Transaction receipt and confirmation displayed on screen.

**Deliverables**

```
Deliverable	              Description

ATM Software Upgrade	  Core software enabling rBTC purchase, multi-currency, and QR scanning 

Dashboard Application	  Web-based interface for configuration, monitoring, and analytics

API & Node Integration    Secure node interaction layer for transaction broadcasting

Pilot Deployment	      3–5 ATMs in El Salvador and 1 EU-based pilot (Euro integration)

Documentation            Technical and operational manuals for operators

```

---

## 5. Impact & Alignment with Rootstock Collective Goals

This project strengthens Rootstock’s ecosystem by:

Expanding real-world access to rBTC through cash-based infrastructure.

Advancing decentralization, with each ATM operating autonomously.

Enhancing global adoption, by supporting multiple fiat currencies.

Driving financial inclusion, connecting unbanked users to Bitcoin-based DeFi.

The combination of physical access points, decentralized architecture, and local currency support represents a scalable blueprint for Rootstock adoption worldwide.

---

## 6. Future Development Opportunities

Following successful deployment, the framework can be expanded to:

Enable rBTC-to-cash withdrawals ( if ATM version has two way functionality)

Support token purchases or swaps (RIF, stablecoins, etc.).

Integrate Rootstock DeFi and savings dApps.

Deploy across partner ATM networks in Latin America, Europe, and Africa.
