# Foundry FundMe

FundMe is a decentralized application (dApp) built using Foundry, a smart contract development toolchain. FundMe allows users to raise and withdraw funds from the smart contract.

# Getting Started

Make sure you have intalled:

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`

- [foundry](https://getfoundry.sh/)
* You'll know you did it right if you can run `forge --version` and you see a response like `forge 0.2.0 (fca0a6c 2023-06-16T00:07:44.213322400Z)`

## Quickstart
```
cd foundry-fund-me-f23
forge build
```

## Projects

In this section, we provide an overview of how to create and work with existing FundMe projects using Foundry.

## Forge Overview

Learn how to use forge, Foundry's tool for compiling, testing, and deploying smart contracts.

# Usage

## Deploy:
```
forge script scripts/DeployFundMe.s.sol
```

## Testing

To run the tests localy, use:
```
forge test
```
To test specific function localy, use:
```
forge test --match-test testFunctionName
```

To run tests on Sepolia testnet:
```
forge test --fork-url $SEPOLIA_RPC_URL
```

## Test coverage

```
forge coverage
```

## Deployment to a mainnet or testnet

1. Setup environment variables.
Add `SEPOLIA_RPC_URL` and `PRIVATE_KEY` to a .env file (as enviroment variables).
Optionally, you can add `ETHERSCAN_API_KEY` if you want to verify you contract on [Etherscan](https://etherscan.io/).

2. Get tesnet ETH.
Go to the [sepolia faucet](https://sepoliafaucet.com/), login and paste you'r wallet address, then you will get 0.5 Sepolia ETH.

3. Deploy and verify.
```
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
```

## Scripts

Deploing locally using cast:
```
cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
```

or

```
forge script script/FundFundMe.s.sol --rpc-url sepolia  --private-key $PRIVATE_KEY  --broadcast
```

To check how much gas is being used, run the following code snippet:
```
forge snapshot
```
You'll see an output file called .gas-snapshot

To run code formatting:
```
forge fmt
```

# Thank you!
