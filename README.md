# LayerZero Cross-Chain Project

This repository contains the LayerZero Cross-Chain Project, which aims to implement cross-chain functionality using LayerZero technologies. 

## Project Structure

- `artifacts/`: Contains compiled contract artifacts.
- `contracts/`: Includes the smart contract source code.
- `deploy/`: Holds deployment scripts.


## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/)
- [Yarn](https://yarnpkg.com/)

### Clone Additional Repository

Clone the additional repository for OmniCounter deployment:

```bash
git clone https://github.com/jaguard2021/Layerzero-omnicounter-deploy.git
```

### Compilation

```bash
npx hardhat compile
```

### Deployment

Replace NETWORK_NAME with the target network (e.g., mumbai, fuji).

```bash 
npx hardhat --network NETWORK_NAME deploy --tags OmniCounter
```

### Interacting with the Contracts

Explore and interact with deployed contracts using Hardhat tasks.

Deploy both OmniCounters:

```bash
npx hardhat --network mumbai deploy --tags OmniCounter
npx hardhat --network fuji deploy --tags OmniCounter
```

Set Trusted Remote

```bash 
npx hardhat --network mumbai setTrustedRemote --target-network fuji --contract OmniCounter
npx hardhat --network fuji setTrustedRemote --target-network mumbai --contract OmniCounter
```

Send a cross chain message from mumbai to fuji !

```bash 
npx hardhat --network mumbai incrementCounter --target-network fuji
```



