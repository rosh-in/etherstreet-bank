# EtherStreet Bank

EtherStreet Bank is a DeFi borrowing dapp.  
Users connect their wallet, deposit ETH as collateral, and borrow a stablecoin against it.

## What it does

- Lets users **connect their wallet** (e.g. MetaMask).
- Allows them to **deposit ETH** as collateral.
- Lets them **borrow a stablecoin** up to a certain limit.
- Shows basic information like deposited collateral and borrowed amount.
- Runs on a test network so it’s safe to experiment.

## Why we built it

Most DeFi lending apps are powerful but hard to understand:

- Collateral and liquidation are confusing for new users.
- It’s not always clear how much you can safely borrow.
- Many UIs assume you already know how DeFi works.

EtherStreet Bank is a simple prototype to:

- Explain the borrowing flow in a clearer way.
- Show collateral and debt in one place.
- Make it easier to reason about “how much is safe”.

## How it works (high level)

- Users connect their wallet.
- When a user deposits ETH:
  - A Solidity contract records the amount they locked as collateral.
- When a user borrows:
  - The contract checks if they are within the allowed loan‑to‑value (LTV) ratio.
  - If they are, it mints / transfers a stablecoin to them (on testnet).
- The frontend reads data from the contract and displays:
  - Collateral balance.
  - Borrowed amount.

## Tech stack

- **Frontend**: React, JavaScript
- **Smart contracts**: Solidity.
- **Blockchain**: Polygon (testnet).
- **Tooling**: Hardhat, ethers.js.
