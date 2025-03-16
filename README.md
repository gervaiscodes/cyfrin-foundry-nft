# Foundry NFT

## Overview
Foundry NFT is a Solidity-based smart contract project designed to manage the creation, deployment, and interaction of NFTs using Foundry as the testing and development framework. The project includes multiple Solidity contracts, integration tests, and deployment scripts.

## Project Structure

```
├── src/
│   ├── BasicNft.sol            # Basic NFT contract implementation
│   ├── MoodNft.sol             # Mood-based NFT contract
│   ├── Counter.sol             # Example counter contract
├── script/
│   ├── DeployBasicNft.s.sol    # Deployment script for Basic NFT
│   ├── DeployMoodNft.s.sol     # Deployment script for Mood NFT
│   ├── Interactions.s.sol      # Script to interact with deployed contracts
│   ├── Counter.s.sol           # Deployment script for Counter contract
├── test/
│   ├── BasicNftIntegrationTest.t.sol  # Integration tests for Basic NFT
│   ├── MoodNftTest.t.sol              # Unit tests for Mood NFT
│   ├── MoodNftIntegrationTest.t.sol   # Integration tests for Mood NFT
│   ├── DeployMoodNftTest.t.sol        # Tests for Mood NFT deployment
├── foundry.toml               # Foundry configuration file
├── Makefile                   # Build automation
├── README.md                  # Project documentation
```

## Prerequisites
- Install [Foundry](https://github.com/foundry-rs/foundry) by running:
  ```sh
  curl -L https://foundry.paradigm.xyz | bash
  foundryup
  ```
- Install dependencies:
  ```sh
  forge install
  ```

## Building the Project
To compile the smart contracts, run:
```sh
forge build
```

## Running Tests
To execute all tests, run:
```sh
forge test
```
For detailed test output with logs:
```sh
forge test -vvv
```

## Deploying Contracts
To deploy contracts using Foundry scripts:
```sh
forge script script/DeployBasicNft.s.sol --broadcast --rpc-url <RPC_URL>
```
Replace `<RPC_URL>` with your network endpoint.

## Interacting with Contracts
To interact with deployed contracts:
```sh
forge script script/Interactions.s.sol --rpc-url <RPC_URL>
```

## Configuration
The `foundry.toml` file includes configuration settings such as library mappings and filesystem permissions:
```toml
[profile.default]
src = "src"
out = "out"
libs = ["lib"]
remappings = ["@openzeppelin=lib/openzeppelin-contracts"]
fs_permissions = [{ access = "read", path = "./broadcast" }, { access = "read", path = "./img/" }]
```

## License
This project is licensed under the MIT License.
