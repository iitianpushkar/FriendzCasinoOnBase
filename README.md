# 🎰 FriendzCasinoOnBase

A room-based multiplayer on-chain casino** built on **Base**—where friends gather, wager crypto, and enjoy fair, transparent games powered by blockchain.

> 🧑‍🤝‍🧑 Create rooms, invite your crew, place bets, and let smart contracts handle scoring and payouts with cryptographic trust.

---

## ⚙️ Tech Stack

- **Frontend**: [Next.js](https://nextjs.org/) – Modern React framework  
- **Backend**: Node.js – Real-time coordination and randomness server  
- **Blockchain**: [Base](https://base.org/) – Fast, low-fee L2 with smart account infrastructure  

---

## 🎯 Why Base?

- **Account Abstraction** with **Smart Wallets**: Passkeys based wallet creation for non-crypto-native users.  
- **Gasless UX** using **Paymasters**: Users can interact without needing ETH for gas, making onboarding seamless.

---

## Architecture
![Architecture](/frontend/public/Casino.png)

## 🎮 Current Game: Mines

### 🕹️ Game Workflow

1. **Room Creation**
   - Go to the sidebar and choose `Create Room`.
   - Set a `roomId` and define a `betAmount`.

2. **Room Joining**
   - Players select the `Mines` game and join using the `roomId`.

3. **Betting**
   - Each participant must place the bet to be considered active.

4. **Start Game**
   - The room **leader** initializes the game by choosing:
     - Number of **mines**.
     - Number of **gems**.

5. **Server Commits Random Mines**
   - Upon `GameStartedEvent`, the server:
     - Randomly selects mine positions.
     - Sends a **commitment hash** (not actual data) to the smart contract.

6. **Player Actions**
   - Players click to select grid cells and submit them.

7. **Reveal Phase**
   - After all submissions, the **leader** requests mine reveal.
   - Server sends mine data to the contract.
   - Contract verifies it matches the earlier hash.

8. **Scoring & Rewards**
   - ✅ If hash matches:
     - Top scorers (including ties) split the total pot.
   - ❌ If verification fails:
     - All bets are refunded.

---

## 🔐 Trust Through Transparency

- Random mine layout is committed via **hash** before gameplay.
- Players can't know mine positions in advance.
- Smart contract strictly checks for tampering or inconsistencies.

---

## 🚀 Future Additions

- 🎲 New Games: Dice, Roulette, Blackjack, etc.   
- 🏆 Leaderboards and Stats  
- 📱 Fully mobile-friendly experience

---

