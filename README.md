# Stellar Waves (Built for Base)

Stellar Waves is a lightweight, read-only tool designed to interact with the Base network, including both Base Mainnet and Base Sepolia. This tool facilitates network identity validation, blockchain data inspection, and contract verification using Coinbase Wallet SDK and direct references through Basescan.

---

## Key Features

- **Coinbase Wallet SDK Integration** for seamless wallet connection (EIP-1193)  
- **ChainId Validation** for Base Mainnet (8453) and Sepolia (84532)  
- **Network Snapshot** to retrieve block height, gas price, and other block metrics  
- **Address Inspection** to examine balances, transaction counts, and bytecode presence  
- **ERC-20 Token Inspection** for metadata, total supply, and token holder balances  
- **Basescan Verification** to independently validate contracts and addresses  

---

## Repository Structure

- **app/stellar-waves.ts**  
  The core script that connects to Coinbase Wallet and interacts with Base RPC endpoints to retrieve blockchain data and execute queries.

- **config/base.networks.json**  
  Contains configuration settings, including the RPC URLs, explorers, and chainIds for both Base Mainnet and Sepolia.

- **docs/architecture.md**  
  A breakdown of the project’s architecture, its design decisions, and its integration with Base’s read-only model.

- **scripts/sample-addresses.json**  
  Sample addresses used for conducting repeatable checks and testing.

- **contracts/**  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - `mapping.sol` — a minimal contract to validate the deployment process  
  - `ERC721.sol` — a stateful contract for interaction testing  
  - `minitoken.sol` — a lightweight contract used for read-only queries  

- **package.json**  
  The dependency file that includes the necessary libraries and references to Coinbase and Base repositories.

- **README.md**  
  This document, which explains how to set up, use, and contribute to the project.

---

## Supported Base Networks

- **Base Sepolia**  
  ChainId (decimal): 84532  
  Explorer: [sepolia.basescan.org](https://sepolia.basescan.org)

- **Base Mainnet**  
  ChainId (decimal): 8453  
  Explorer: [basescan.org](https://basescan.org)

---

## Functionality

Stellar Waves provides a straightforward method for developers to verify network consistency and interact with Base’s blockchain:
- By connecting to a Coinbase Wallet via the **Coinbase Wallet SDK**, you can authenticate and interact with Base networks.
- The tool fetches real-time block and gas data, checks balances and transactions, and verifies deployed contracts using Basescan.
- The entire process remains read-only, meaning no data is written to the blockchain.

---

## Tooling & Dependencies

This repository relies on open-source libraries from Coinbase and Base:
- **Coinbase Wallet SDK** for secure wallet connectivity  
- **OnchainKit** for interacting with Base’s native primitives  
- **Viem** for efficient and type-safe RPC communication with Base  
- Direct dependencies from **Base** and **Coinbase GitHub repositories**

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Base Sepolia Testnet Deployments

The following contracts have been deployed on the Base Sepolia test network to validate the functionality of the tools and confirm network interactions before moving to the Base Mainnet:

**Network**: Base Sepolia  
**ChainId (decimal)**: 84532  
**Explorer**: [sepolia.basescan.org](https://sepolia.basescan.org)

**Contract mapping.sol address**:  
0xC45117895807cc45cCDf87D621f631df2297098E 

Deployment and verification:
- [Deployment link](https://sepolia.basescan.org/address/0xC45117895807cc45cCDf87D621f631df2297098E)
- [Code verification](https://sepolia.basescan.org/0xC45117895807cc45cCDf87D621f631df2297098E/0#code)

**Contract ERC721.sol address**:  
0xE90BB539FdA657eEBBAa86fac18E0D746F514263 

Deployment and verification:
- [Deployment link](https://sepolia.basescan.org/address/0xE90BB539FdA657eEBBAa86fac18E0D746F514263)
- [Code verification](https://sepolia.basescan.org/0xE90BB539FdA657eEBBAa86fac18E0D746F514263/0#code)

**Contract minitoken.sol address**:  
0x27442993C042b966F21d1717AF7919A7a3B129Dc

Deployment and verification:
- [Deployment link](https://sepolia.basescan.org/address/0x27442993C042b966F21d1717AF7919A7a3B129Dc)
- [Code verification](https://sepolia.basescan.org/0x27442993C042b966F21d1717AF7919A7a3B129Dc/0#code)

These deployments are intended to test Base tools and network compatibility before launching on the Mainnet.

---

## Author

GitHub: [https://github.com/BotanicGliders](https://github.com/BotanicGliders)  

Email: botanic.03gliders@icloud.com 

Public contact: [https://x.com/of3442](https://x.com/of3442)  
