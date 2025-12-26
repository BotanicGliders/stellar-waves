# Stellar Waves — Architecture Breakdown

This document outlines the design decisions and architectural choices made in **Stellar Waves**, focusing on its alignment with Base's network and read-only principles.

---

## Project Overview

**Stellar Waves** is designed to interact with **Base networks**, utilizing **Base Mainnet** for live operations and **Base Sepolia** for testing. The project follows a **read-only model** to ensure security, stability, and simplicity in operation.

### Key Features:
- **Read-only interactions**: The project focuses on querying data from the blockchain without modifying it.
- **Base integration**: All interactions are tailored for **Base networks**, primarily **Base Mainnet** and **Base Sepolia**.
- **Centralized network configuration**: All network details are stored in a single configuration file (`config/base.networks.json`), making updates and maintenance simpler.

---

## Base Integration

### 1. **RPC Endpoints**
Stellar Waves uses **Base's public RPC endpoints** for interaction:
- **Mainnet**: The live production environment where real transactions occur.
- **Sepolia**: A testnet that mimics the mainnet for safe contract testing and validation.

All RPC configurations are centralized in the `config/base.networks.json` file to avoid hardcoding values across the project.

### 2. **Explorer URLs**
Explorer URLs for Base Mainnet and Sepolia are configured to ensure users can view transaction data and contract details in **BaseScan**:
- **Base Mainnet Explorer**: [BaseScan](https://basescan.org)
- **Base Sepolia Explorer**: [BaseScan Sepolia](https://sepolia.basescan.org)

By integrating with BaseScan, Stellar Waves allows users to trace transactions, verify contract interactions, and inspect network data.

---

## Read-only Model

The **read-only model** is a core design principle for Stellar Waves, ensuring:
- **No transactions**: The project does not perform any transactions that alter the blockchain state.
- **Non-mutating interactions**: All interactions are limited to data querying, such as reading balances, checking contract code, and retrieving block metadata.

### Why Read-only?
- **Security**: Limiting the interactions to non-mutating operations minimizes risks.
- **Efficiency**: Read-only operations are less resource-intensive, and querying data from Base networks provides sufficient functionality for the project.
- **Simplified Validation**: Validation processes can focus solely on ensuring data retrieval, without concerns for transaction validity or on-chain changes.

---

## Design Decisions

### 1. **Centralized Configuration**
Storing network configurations in a single file (`config/base.networks.json`) simplifies the management of network settings across the project:
- New Base networks can be added with minimal code changes.
- The file serves as a clear and central source of truth for network parameters.

### 2. **Minimal Dependencies**
Stellar Waves avoids unnecessary external dependencies:
- Base-native libraries are used wherever possible.
- Only essential libraries are included to keep the project lean and maintainable.

### 3. **Testnet First**
Base Sepolia (the testnet) is used during development and validation. This ensures that all interactions can be safely tested without affecting the mainnet or requiring real funds. The process includes:
- Reading balances, contract data, and metadata.
- Verifying interactions using the **Base Sepolia** network before moving to **Base Mainnet**.

---

## Future Considerations

1. **Support for Additional Base Networks**:  
   As Base introduces new testnets or mainnets, Stellar Waves will integrate these networks by simply adding configuration entries to `base.networks.json`.

2. **Transaction Simulation**:  
   Though currently read-only, future versions of Stellar Waves may explore the ability to simulate transactions in Base, allowing for more complex contract validation and testing.

_Last updated: initial scaffold_
