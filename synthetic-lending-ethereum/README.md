# ARG25 Project Submission Template

Welcome to Invisible Garden- ARG25.

Each participant or team will maintain this README throughout the program.  
You'll update your progress weekly **in the same PR**, so mentors and reviewers can track your journey end-to-end.

## Project Title

ERC-6909 Stable Vault Hook

## Team

- Team/Individual Name: Defiant Labs
- GitHub Handles: mcmoodoo, LeeMarreros, kavehtehrani
- Devfolio Handles: defiant, LeeMarreros, kwar13

## Project Description

We're building a Uniswap v4 Hook and Vault system designed for stable-asset markets, using ERC-6909 as the on-protocol accounting layer.

The Hook enables synthetic stablecoin minting (e.g., `sUSD`) directly through swap flows, while the Vault manages ERC-6909 collateral balances and debt positions. This design allows synthetic lending, credit-backed trading, and optimized stable AMM logic to coexist natively within Uniswap v4's pool and balance management system — without relying on off-protocol custody or external vaults.

The project explores atomic collateralization, on-chain solvency enforcement, and flash-resistant accounting leveraging ERC-6909's shared ledger model.

## Tech Stack

- **Smart Contracts:** Solidity (Cairo migration planned post-prototype)
- **Protocol:** Uniswap v4 (Hooks + PoolManager APIs)
- **Ledger Layer:** ERC-6909
- **Testing:** Foundry / `snforge`
- **Oracles:** Chainlink / TWAP Feeds
- **Frontend (planned):** Next.js + wagmi (for visualization of positions)

## Objectives

By the end of ARG25:

1. Implement a minimal Vault managing ERC-6909 collateral positions and sUSD debt.
2. Implement a Hook that interacts with the Vault to mint/repay during swap flows.
3. Demonstrate secure ERC-6909 accounting and liquidation logic.
4. Provide a working test suite covering minting, liquidation, and flash-loan resistance.

## Weekly Progress

### Week 1 (ends Oct 31)

**Goals:**

- Define the architecture and data flow between Hook, Vault, PoolManager, and ERC-6909.
- Write minimal interfaces (`IERC6909`, `IPoolManager`, `IOracle`, `IERC20Mintable`).
- Implement Vault core functions: `openOrIncreasePosition`, `withdraw`, `liquidate`.

**Progress Summary:**

- ✅ Completed high-level system design and interface definitions.
- ✅ Implemented minimal `Vault` contract (collateral custody, debt ledger, solvency check).
- ✅ Drafted Hook prototype with beforeSwap/afterSwap logic.
- 🧩 Pending integration testing with PoolManager ERC-6909 mock.

### Week 2 (ends Nov 7)

**Goals:**

- Build and test the full swap → mint → repay → liquidate flow using Foundry.
- Implement mock oracle and synthetic stablecoin (`sUSD`).
- Add reentrancy and flash-loan protection tests.
- Begin basic visualization (position dashboard).

**Progress Summary:**

### 🗓️ Week 3 (ends Nov 14)

**Goals:**

- Optimize hook logic for atomic minting & liquidation.
- Integrate TWAP oracle for price sanity.
- Publish test coverage and short demo.
- Prepare final presentation slides.

**Progress Summary:**

## Final Wrap-Up

_After Week 3, summarize your final state: deliverables, repo links, and outcomes._

- **Main Repository Link:**
- **Demo / Deployment Link (if any):**
- **Slides / Presentation (if any):**

## 🧾 Learnings

_What did you learn or improve during ARG25?_

## Next Steps

_If you plan to continue development beyond ARG25, what's next?_

_This template is part of the [ARG25 Projects Repository](https://github.com/invisible-garden/arg25-projects)._  
_Update this file weekly by committing and pushing to your fork, then raising a PR at the end of each week._
