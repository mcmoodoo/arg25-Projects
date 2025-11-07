# ARG25 Project Submission Template

Welcome to Invisible Garden- ARG25.

Each participant or team will maintain this README throughout the program.  
You’ll update your progress weekly **in the same PR**, so mentors and reviewers can track your journey end-to-end.

## Project Title

ZK Gaming Protocol

## Team

- Dream Team
- mcmoodoo, fengshanshan, kavehtehrani
- Defiant, shanshan33, kwar13

## Project Description

We're building the permissionless protocol for provably fair two-player games, starting with Rock-Paper-Scissors and expanding to support any hidden-information game through ZK proofs and shared relayer infrastructure.

**The Problem:**

- **Centralized gaming:** Great UX but requires trust (house could cheat, custody risk)
- **Existing crypto solutions:** Trustless but terrible UX (2-3 transactions per game, $10-30 gas, 60+ second waits)
- **Gap:** Players want both trustless guarantees AND instant gameplay

**Our Solution:**
Combine zero-knowledge cryptography (hide moves) with off-chain relayers (batch transactions) to deliver one-click, trustless gaming. Players click once, ZK proofs are generated in the browser, relayers coordinate off-chain, and settlement happens atomically on-chain. Result: 1 click per player, 30-40 seconds total, $0 gas for users.

**Vision:**
We're not just building a game—we're building the infrastructure layer for ALL two-player hidden-information games. Like Uniswap for DeFi or OpenSea for NFTs, we're creating the protocol that becomes the default gaming infrastructure in crypto.

🏗️ **[View System Architecture →](./assets/system-architecture.md)**

## Tech Stack

**Zero-Knowledge Proofs:**

- Groth16 / Plonky2 (ZK proof systems for move validation)
- Browser-based proof generation (~3 seconds, ~200 bytes proofs)

**Smart Contracts:**

- Solidity (EVM-compatible chains)
- Proof verification, game logic, escrow system
- Atomic settlement mechanism

**Off-Chain Infrastructure:**

- Relayer network (permissionless, economically secured)
- Off-chain coordination and batching
- Public relayer network (stake-based)

**User Interface:**

- Web-based interface (one-click gameplay)
- Real-time game matching
- Escrow management dashboard

**Other:**

- USDC/ERC20 for betting and escrow
- Developer SDK for game creation (Phase 2)
- Game registry smart contracts (Phase 2)

## Objectives

By the end of ARG25, we aim to achieve:

1. **Working Rock-Paper-Scissors Proof of Concept**
   - Fully functional RPS game with ZK proof generation
   - Browser-based one-click gameplay
   - Working relayer coordination (off-chain matching and batching)

2. **Core Protocol Infrastructure**
   - Smart contracts for proof verification and game logic
   - Escrow system (deposit once, play forever)
   - Basic relayer implementation with economic incentives

3. **Technical Validation**
   - Prove ZK + relayer architecture achieves target UX (1 click per player, <40 seconds)
   - Demonstrate cost reduction ($0 gas for users vs $20+ traditional)
   - Validate security model (trustless, permissionless)

4. **Foundation for Protocol Expansion**
   - Architecture designed for multi-game support
   - Reusable ZK circuits and smart contract patterns
   - Documentation for future game development

**Success Metric:** Launch a working RPS game that 10-50 early users can play, proving the tech works before scaling to full protocol.

**ARG25 Focus:** We're starting Phase 1 during this 3-week program, building the foundation for the core protocol and RPS proof of concept.

## 🧾 Learnings

_What did you learn or improve during ARG25?_

## Next Steps

_If you plan to continue development beyond ARG25, what’s next?_

_This template is part of the [ARG25 Projects Repository](https://github.com/invisible-garden/arg25-projects)._  
_Update this file weekly by committing and pushing to your fork, then raising a PR at the end of each week._
