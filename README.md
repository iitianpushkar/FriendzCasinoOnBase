# 🎰 **FriendzCasinoOnBase**

> **A room-based multiplayer on-chain casino built on [Base](https://base.org)** – where friends gather, wager crypto, and enjoy provably fair games powered by blockchain.

🧑‍🤝‍🧑 Create private rooms, invite your crew, place bets, and let smart contracts handle scoring and payouts with cryptographic trust.

---

## ⚙️ Tech Stack

| Layer        | Stack                                                                 |
|--------------|-----------------------------------------------------------------------|
| **Frontend** | [Next.js](https://nextjs.org/) – Modern React framework              |
| **Backend**  | Node.js – Real-time coordination and randomness server               |
| **Blockchain** | [Base](https://base.org/) – Fast, low-fee L2 with smart account infra |

---

## 🎯 Why Base?

- 🔐 **Account Abstraction**: Passkey-based smart wallet creation for seamless onboarding.
- 🆓 **Gasless UX**: Integrated **Paymasters** allow users to interact without holding ETH.

---

## 🏗️ Architecture

![Architecture Diagram](/frontend/public/Casino.png)

---

## 🎮 Current Game: **Mines**

A cryptographically fair version of the classic “Mines” game – now multiplayer and on-chain.

### 🕹️ Game Workflow

1. **Room Creation**
   - Navigate to the sidebar → click `Create Room`.
   - Choose a `roomId` and set the `betAmount`.

2. **Room Joining**
   - Select the `Mines` game and enter using the shared `roomId`.

3. **Betting**
   - All players must place their bets to become active participants.

4. **Game Start (Leader)**
   - The room leader starts the game by choosing:
     - Number of **mines**.
     - Number of **gems**.

5. **Server Commitment**
   - On `GameStartedEvent`:
     - Server randomly selects mine positions.
     - Sends a **commitment hash** to the smart contract (not the actual data).

6. **Player Turns**
   - Each player clicks to choose grid cells and submits their selection.

7. **Reveal Phase**
   - After all moves, the **leader** requests the mine reveal.
   - Server sends actual mine data to the contract.
   - Contract verifies data against the original hash.

8. **Scoring & Rewards**
   - ✅ If hash is valid: Top scorers split the pot (including ties).
   - ❌ If mismatch: All bets are refunded.

---

## 🔐 Fairness Through Transparency

- ✅ Mine layout is committed via hash before gameplay.
- 🚫 No one can predict mine positions.
- 🔎 Smart contract enforces tamper-proof verification.

---

## 📦 Deployments

| Component                     | Link / Address |
|-------------------------------|----------------|
| **Frontend**                  | [Live Site](https://friendzcasino-on-base.vercel.app/) |
| **Smart Contract (Mainnet)**  | `0x76f9bA2F115Abe7899F124be06335F8133854FEd` |
| **Smart Contract (Sepolia)**  | `0x1cccf3b8ed254d2913d62793993925e8a8007a4f` |
| **Example Tx (Mainnet)**      | [Tx1](https://basescan.org/tx/0x23d7fbd35f3e01b4137c860d2fb18ab0fc9bf4351689455b9ac6d17279f9cd9b) · [Tx2](https://basescan.org/tx/0x343a4b77cd5fa10ff4080e2bbc4ee4412345f933a658c1e64980b6abff2969bf) |
| **Backend Server**            | Deployed on AWS |

---

## 📹 Demo Video

▶️ [Watch Demo](https://youtu.be/K_3fF6cZhGM?si=oflS3frMChzmS5t8)

---

## 🚀 Future Plans

- 🎲 Add more games: Dice, Roulette, Blackjack, and more  
- 📊 Leaderboards, stats, and achievements  
- 📱 Fully responsive, mobile-friendly UI  
