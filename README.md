# Multi-Chain Stress Tester (Path B)

A professional-grade simulation tool for the **Alex000115** ecosystem. Before launching to mainnet, every protocol must survive the "Stress Test." This script uses Ethers.js and worker threads to simulate hundreds of unique users interacting with your contracts simultaneously. It measures how the Master Dashboard handles rapid state changes and identifies potential bottlenecks in your Solidity logic.

## Core Features
* **Concurrent Transaction Flooding:** Simulates $N$ users calling functions in parallel.
* **Gas Profiler:** Generates a report on the average, peak, and total gas costs for a protocol's lifecycle.
* **Latency Benchmarking:** Tracks the time between a transaction broadcast and the UI update in the Master Dashboard.
* **Flat Architecture:** Single-directory layout for the Simulation Engine, User Wallet Generator, and Report Exporter.



## Logic Flow
1. **Provision:** The script generates 50 ephemeral "Shadow Wallets" and funds them with testnet ETH.
2. **Execute:** Each wallet is assigned a task (e.g., "Bid on an AI Service" or "Release a Milestone").
3. **Monitor:** The script listens for events across all chains and logs the block-time for every confirmation.
4. **Report:** Outputs a JSON file containing the protocol's performance metrics under load.

## Setup
1. `npm install`
2. Configure `sim-settings.json` with your target contract addresses.
3. `node stress-test.js`
