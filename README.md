# 🕹️ Bitcoin Nexus: Decentralized Gaming on Stacks Layer 2

**Bitcoin Nexus** is a comprehensive decentralized gaming platform built on **Stacks Layer 2**, combining the scalability of Stacks with the security of the Bitcoin blockchain. It allows players to collect NFTs, compete for Bitcoin rewards, and explore richly interactive game worlds with customizable avatars and progression mechanics.

---

## ⚙️ Key Features

* **NFT-Based Game Assets**: Mint, own, and trade unique game items (`nexus-asset`) and avatars (`nexus-avatar`).
* **Avatar Progression System**: Gain experience, level up, and unlock achievements.
* **Virtual Worlds**: Create and manage immersive game environments with configurable entry requirements.
* **Bitcoin-Backed Leaderboards**: Compete globally and earn Bitcoin rewards based on your performance.
* **Protocol Admin Control**: Ensure safe, authorized updates and asset minting through a whitelist system.

---

## 📐 System Architecture

### 🧱 Smart Contract Layer (Clarity on Stacks)

| Component                  | Purpose                                                |
| -------------------------- | ------------------------------------------------------ |
| `nexus-asset` NFT          | Represents in-game assets (items, tools, etc.)         |
| `nexus-avatar` NFT         | Represents a player’s customizable avatar              |
| `game-worlds` map          | Stores data for different virtual environments         |
| `avatar-metadata` map      | Tracks avatar levels, achievements, and equipped items |
| `leaderboard` map          | Stores player scores, ranks, and total rewards         |
| `protocol-admin-whitelist` | Controls administrative access                         |

### 🔄 Flow Diagram

```
+------------------------+
|    Protocol Admins     |
+-----------+------------+
            |
            v
+------------------------+
|   Initialize Protocol  |
|   Mint Assets/Worlds   |
+-----------+------------+
            |
            v
+------------------------+           +-----------------------------+
|     Players Join       | <-------> |  Leaderboard + Score Update |
|  (Create Avatar, Play) |           +-------------+---------------+
+-----------+------------+                         |
            |                                      v
            |                        +-----------------------------+
            |                        |  Distribute Bitcoin Rewards |
            +----------------------> +-----------------------------+
```

---

## 🧪 Contracts Overview

### Constants

* **Error codes**: Predefined set (e.g. `ERR-NOT-AUTHORIZED`, `ERR-INVALID-INPUT`, etc.)
* **Game mechanics**: `MAX-LEVEL`, `BASE-EXPERIENCE-REQUIRED`, etc.

### Core Contracts

#### Initialization

```clarity
(initialize-protocol entry-fee max-entries)
```

#### NFT Minting

```clarity
(mint-nexus-asset name description rarity power-level world-id attributes)
(create-avatar name world-access)
```

#### Gameplay Mechanics

```clarity
(update-avatar-experience avatar-id experience-gained)
(update-player-score player new-score)
(distribute-bitcoin-rewards)
```

#### World Creation

```clarity
(create-game-world name description entry-requirement)
```

#### Asset Transfer

```clarity
(transfer-game-asset token-id recipient)
```

---

## ✅ Security & Compliance

* Access to sensitive operations is strictly controlled via the `protocol-admin-whitelist`.
* Player ownership is enforced using NFT ownership checks.
* Data validation is performed via a comprehensive set of internal validation functions.

---

## 📊 Tokenomics & Leaderboards

* **Reward Model**: Rewards are distributed in Bitcoin based on leaderboard scores.
* **Leaderboard Entries**: Limited and configurable via `max-leaderboard-entries`.

---

## 📂 Project Structure

* `nexus.clar`: Core smart contract
* `README.md`: Documentation
* Future additions may include frontend (React + Hiro Wallet), backend leaderboard sync, and reward UTXO integration.

---

## 🚀 Getting Started (Development)

1. **Install Clarinet**

   ```bash
   npm install -g @hirosystems/clarinet
   ```

2. **Run Tests**

   ```bash
   clarinet test
   ```

3. **Deploy to Devnet**

   ```bash
   clarinet deployments
   ```

---

## 🤝 Contributing

We welcome PRs for bug fixes, new gameplay features, balancing logic, or Stacks-based tooling enhancements.
