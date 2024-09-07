# Uniswap V3 Core – Compatibility Layer

## Overview
This repository contains a fork of the [Uniswap V3 Core](https://github.com/Uniswap/v3-core) protocol, designed to ensure compatibility with the latest Solidity versions. The primary focus of this fork is to facilitate interaction and integration testing with external smart contracts, while avoiding any modifications to the core logic of Uniswap V3, aside from necessary adjustments for Solidity compiler compatibility.

## Purpose
This compatibility layer has been created with two goals in mind:
- **Ensure Compatibility**: Update the Uniswap V3 core contracts to work seamlessly with Solidity 0.8.x and newer versions, ensuring that external projects do not face version incompatibility issues.
- **Enable Testing**: Provide an environment where developers can test their smart contracts against the Uniswap V3 protocol, using modern Solidity tooling, without needing to modify the protocol's fundamental behavior.

## What’s Included
The repository includes:
- Updated Solidity contracts for compatibility with version 0.8.x and above.
- Key components from the Uniswap V3 core:
  ### Callback Interfaces:
  Interfaces for implementing key callbacks required by the Uniswap V3 protocol such as minting, swapping, and flash loan callbacks.
    - **IUniswapV3FlashCallback.sol**
    - **IUniswapV3MintCallback.sol**
    - **IUniswapV3SwapCallback.sol**
  ### Pool Contracts:
  Essential pool-related interfaces and contracts, including actions, state, events, and deployment logic.
    - **IUniswapV3PoolActions.sol**
    - **IUniswapV3PoolDerivedState.sol**
    - **IUniswapV3PoolImmutables.sol**
    - **UniswapV3Pool.sol**
    - **UniswapV3PoolDeployer.sol**
  ### Library Contracts:
  Utility libraries to perform complex calculations used throughout the protocol, including math functions for liquidity, price, and ticks.
    - **LiquidityMath.sol**
    - **SqrtPriceMath.sol**
    - **FullMath.sol**
    - **TickMath.sol**

## What’s Not Changed
In keeping with the goal of maintaining the integrity of the original protocol:
- No changes have been made to the core logic or functionality of Uniswap V3, except for those required to ensure compatibility with newer Solidity compiler versions.
- The operational and fee structures remain the same as in the original Uniswap V3 Core.

## Directory Structure
```bash
contracts/
  ├── interfaces/
  │   ├── callback/
  │   │   ├── IUniswapV3FlashCallback.sol
  │   │   ├── IUniswapV3MintCallback.sol
  │   │   └── IUniswapV3SwapCallback.sol
  │   └── pool/
  │       ├── IUniswapV3PoolActions.sol
  │       ├── IUniswapV3PoolDerivedState.sol
  │       ├── IUniswapV3PoolEvents.sol
  │       ├── IUniswapV3PoolImmutables.sol
  │       ├── IUniswapV3PoolOwnerActions.sol
  │       ├── IUniswapV3PoolState.sol
  │       └── IUniswapV3PoolDeployer.sol
  ├── UniswapV3Pool.sol
  ├── UniswapV3Factory.sol
  ├── libraries/
  │   ├── BitMath.sol
  │   ├── FixedPoint96.sol
  │   ├── FullMath.sol
  │   ├── LiquidityMath.sol
  │   ├── SqrtPriceMath.sol
  │   ├── TickMath.sol
  │   ├── Oracle.sol
  │   └── TransferHelper.sol
  ├── test/
  │   ├── UniswapV3Factory.sol
  │   ├── UniswapV3Pool.sol
  │   └── UniswapV3PoolDeployer.sol
.gitignore
LICENSE
README.md
yarn.lock
hardhat.config.ts
```

## Key Folders
**contracts/:** Contains all the Solidity contracts used in Uniswap V3. This includes the interfaces, core pool logic, and necessary libraries.
**libraries/**: A collection of utility contracts that handle essential mathematical and computational logic used throughout the protocol.
**test/**: Sample contracts to facilitate testing of Uniswap V3 pool and factory contracts.

## Installation
To use this compatibility layer for testing or integrating external projects:

### 1. Clone the Repository:
```bash
git clone https://github.com/vale-dinap/uniswap-V3-core.git
```

### 2. Install Dependencies:
Make sure you have installed the necessary dependencies by running:
```bash
yarn install
```

### 3. Compile Contracts:
Ensure the Solidity compiler version is compatible with the updated contracts:
```bash
forge build
```

### 4. Run Tests:
Test the contracts using Foundry or your preferred testing framework:
```bash
forge test
```

## Contributing
Contributions are welcome, especially if they help to further improve compatibility or testing capabilities. Please open an issue or a pull request if you encounter bugs, or if you have suggestions for improvements.

## License
This project is licensed under the same terms as the original Uniswap V3 Core. All rights to the original Uniswap V3 Core code remain with [Uniswap Labs](https://uniswap.org/).
