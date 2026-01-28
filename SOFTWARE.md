# SOFTWARE


Below is a high-level outline for software to adapt an Android tablet–based ATM that exchanges cash for BTC Lightning sats, to also exchange to rBTC using the Rootstock blockchain.


---

## 1. System Overview

Goal: Enable a physical ATM (Android tablet + peripherals) to accept cash and dispense rBTC (Rootstock Bitcoin) to a user-provided address.

Key differences from Lightning ATM:

On-chain (or sidechain) settlement instead of invoice-based Lightning

Longer confirmation model

Gas management

Address validation for Rootstock



---

## 2. Functional Requirements

User Flow:

- User selects Buy rBTC

- User enters or scans Rootstock address

Machine displays:

- Exchange rate eg EURO → rBTC (set according to coin reader)

- Network fee

- Minimum confirmations / settlement disclaimer

- User inserts cash

System:

- Locks rate for a defined time window

- Broadcasts rBTC transaction


---

## 3. Wallet & Blockchain Interaction

rBTC Wallet Management

Must control one or more Rootstock-compatible wallets

Support:

Hot wallet for real-time dispensing

Optional warm/cold wallet refills


Secure private key storage (Android Keystore / HSM / external signer)


Rootstock Network

Connect to:

Self-hosted Rootstock node or

Trusted RPC provider


Capabilities:

Get current gas price

Broadcast transactions

Track confirmations

Query balances




---

## 4. Address Handling

Accept Rootstock EVM addresses

Hex format (0x…)


QR scanning via tablet camera (built into ATM)

Validate:

Correct checksum (EIP-55)

Not a contract address (optional policy)


Display warning:

“Do not use Bitcoin mainnet addresses”




---

## 5. Exchange Rate & Pricing

Fiat → BTC → rBTC pricing logic

Sources:

Exchange APIs

Fixed operator-defined pricing


Spread & fees:

Operator margin

Network gas fees


Rate lock duration:

Short window (e.g., 2–5 minutes)




---

## 6. Hardware Integration Requirements

**Cash Acceptor**

Bill/coin acceptor interface

Requirements:

Real-time denomination detection

Jam/error handling


**Android Tablet**

Minimum OS version defined

Camera access for QR scanning

USB / serial / GPIO support for peripherals



---

## 7. Security Requirements

**Key Security**

No plain-text private keys on disk

Use:

Android Keystore

Encrypted storage


Backup & recovery process defined


**Transaction Security**

Rate-limit withdrawals

Per-transaction max limits

Daily volume caps

Operator emergency stop / kill switch


---

## 8. Compliance & Policy Layer (Configurable)


Transaction logging:

Fiat amount

rBTC amount

Address

Timestamp


Configurable by jurisdiction



---

## 9. Backend / Operator Services

**Operator Dashboard**

Machine status

Wallet balances

Cash levels

Transaction history

Error logs


**Machine Management**

Remote updates

Parameter configuration:

Fees

Limits

Enable/disable Lightning vs rBTC


Health checks & alerts



---

**Failure & Edge Case Handling**

Cash inserted but tx fails

Retry logic

Manual reconciliation process


Network congestion

Dynamic gas adjustment


Power loss mid-transaction

Transaction journal



---

## 10. Differences vs Lightning ATM (Key Design Impacts)

```

Aspect	    Lightning	      rBTC

Settlement	Instant	        Delayed (blocks)

UX	        Invoice-based	  Address-based

Fees	      Routing fees	  Gas fees

Risk	      Low volatility. Higher exposure


```

---

## 11. Non-Functional Requirements

High availability

Offline tolerance (queue tx until online)

Modular blockchain layer

Auditability

Localization / multi-language UI















