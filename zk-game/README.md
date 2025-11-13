# ARG25 Project Submission Template

Welcome to Invisible Garden- ARG25.

Each participant or team will maintain this README throughout the program.  
You’ll update your progress weekly **in the same PR**, so mentors and reviewers can track your journey end-to-end.

## Project Title

Zero-knowledge implementation of Rock Paper Scissors

## Team

- Dream Team
- mcmoodoo, fengshanshan, kavehtehrani
- Defiant, shanshan33, kwar13

## Project Description

🗒️ **PROJECT OPEN SOURCE REPO**: https://github.com/mcmoodoo/zk-ogs \
📼 **DEMO VIDEO**: https://youtu.be/WvKBrJiDE2w

A zero-knowledge implementation of the classic rock-paper-scissors game where Player 1 creates a game by committing it's move (`keccak256(move || salt)`) with a zk proof, Player 2 joins with their move directly, and Player 1 reveals with ZK proofs to resolve the game on-chain.

The project includes two game modes:

- **Basic RPS**: A simple rock-paper-scissors game where players commit and reveal moves using ZK proofs. No token betting required.
- **Degen RPS**: A token-betting version where players stake ERC20 tokens on each game. The winner takes the escrowed tokens.

### Game Flow

- **Player 1** creates a game by committing it's move (`keccak256(move || salt)`) with a zk proof and optionally escrowing tokens (in degen mode).
- **Player 2** joins any open game by submitting their move directly (no commitment needed) and matching the stake (in degen mode).
- Once matched, **Player 1** reveals the result with its original move plus salt and player2's move.
- The contract validates the commitment, verifies the ZK proof, and pays the escrowed tokens to the winner (or slashes Player 1 if they fail to reveal before expiry).

### ZK Proof Generation Flow

1. **Player 1 create the game** and committing it's move (`keccak256(move || salt)`) with a zk proof via Noir circuit
2. **Player 2 joins** and submits their move directly to the contract
3. **Player 1 reveals their move** with original (move + salt) and player2's move to reveal who wins the game


## Tech Stack

### Zero-Knowledge

- **Noir**: ZK circuit language for game logic verification
- **Barretenberg**: ZK proof generation backend 
- **Noir.js**: JavaScript bindings for Noir circuit execution

### Smart Contracts

- **Solidity** ^0.8.26
- **Foundry**: Development framework for smart contracts
- **OpenZeppelin Contracts**: ERC20 token handling and security patterns
- **Solmate**: Additional utility libraries

### Frontend

- **Vite**: Build tool and dev server
- **Ethers.js** v6: Ethereum interaction library
- **Tailwind CSS**: Styling framework

### Development Tools

- **Nargo**: Noir package manager and compiler
- **Forge**: Foundry's testing and deployment tool
- **MetaMask**: Wallet integration

## Objectives

1. **Implement ZK-verified game logic**: Create a Noir circuit that proves the correct winner determination in rock-paper-scissors without revealing Player 1's move until reveal phase.

2. **Build secure commit-reveal mechanism**: Enable Player 1 to commit to a move without revealing it, preventing front-running and ensuring fair gameplay.

3. **Create token-betting game mode**: Implement a "degen" version where players can stake ERC20 tokens, with winner-takes-all payouts.

4. **Develop user-friendly frontend**: Build an intuitive web interface for creating games, joining games, and generating/verifying ZK proofs.

5. **Ensure on-chain verification**: Design contracts that can verify ZK proofs on-chain to ensure game outcomes are correctly computed.

6. **Handle edge cases**: Implement timeout mechanisms, refund logic, and tie handling for robust game operation.

### Key Components

- **Circuit** (`circuit/src/main.nr`): Noir circuit that verifies the winner determination logic. Takes both player moves and the expected winner as inputs, proving the computation is correct.

- **DegenRPS Contract** (`degen-rps/src/DegenRPS.sol`): Main smart contract implementing the token-betting game with commit-reveal scheme, timeout handling, and winner-takes-all payouts.

- **Frontend** (`frontend/`): Web interface built with Vite that handles wallet connection, game creation/joining, ZK proof generation using Barretenberg, and contract interaction.

## 🧾 Learnings

_What did you learn or improve during ARG25?_

Zero-knowledge implementation of a classic commit-reveal scheme. The main improvement over a commit-reveal scheme is knowing that ZK guarantees a valid move has been made. After making this game, we've concluded that ZK really shines in multi-round games (e.g. battleship) where the information is being incrementally revealed. ZK guarantees that opponent cannot cheat mid-game and every move is valid without revealing anything. For instance in a classic commit-reveal you would only know whether your opponent cheated or not at the end. ZK guarantees that each move is valid given that each attack will be run through a board that cannot change throughout the game. 

## Next Steps

_If you plan to continue development beyond ARG25, what’s next?_

We started implementing a 'degen' version of this to integrate with uniswap v4 to make part of a submitted trade a chance based outcome based on the zk-rps game here. More information is under "future work" in the project's repo.

_This template is part of the [ARG25 Projects Repository](https://github.com/invisible-garden/arg25-projects)._  
_Update this file weekly by committing and pushing to your fork, then raising a PR at the end of each week._
