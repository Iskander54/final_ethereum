# landreg
## Codebase

### The stack
The platform runs a on ethereum smart contract Backend with ReactJS on the front ed.

## Getting started (without docker)

This section provides a high-level requirement & quick start guide. For detailed installations, such as getting started with Docker, or specific operating systems
### Prerequisites

- [node](https://nodejs.org/en/) : This should install both Node.js and npm
- [ganache](https://www.npmjs.com/package/ganache-cli) the command line, but I recommend the GUI (https://www.trufflesuite.com/ganache)
- [truffle](https://www.trufflesuite.com/truffle)
- [metamask](https://metamask.io/)

Get a look also at section [docker Installation](#docker-Installation).

### Installation

1. Make sure all the prerequisites are installed

1. Clone the repository, ie `git clone https://github.com/Iskander54/final_ethereum`

1. Go into ./landreg and type `npm install` to install dependencies of the Solidity backend

1. Go into ./client and type `npm install` to install dependencies of the ReactJS frontend

### Starting the application 

1. Launch ganache on port 8545

1. Make sure your Metamask is link to local network port 8545. 

1. Go into ./landreg and `truffle migrate` to push the contracts on the blockchain

1. Go into ./client and `npm run start` to launch the dev server (local port is 8545 in getWeb3.js, you can change it if needed)

1. Open your browser where metamask is installed and go on localhost:3000 ( Port may have change, check the npm run start logs)

## Using Docker

- [Docker](https://www.docker.com/)
- [Docker-compose](https://docs.docker.com/compose/): write the configuration of your containers in a `docker-compose.yml` file


0x42CAD0CA3716b4664c2658A0a48664369D511C54 , 80d7110b676b1cb7f719bc7aa639a10a6d1611f1bd5ff7e94995da52915710de
0xDf7064894A0da6b741b86104af7875647b7767A3 , ae327c532fcc5254b701ca2a10f198787b93d37fe5c78cfe8531ce4373aa182e
0x229846d7818D13a468cB9767c04e375a82CE0e3D , 85b4ae0e89b5dd0ac460dcf1806af39c0ce59ee567f56d520ba1c0144a5a1537
0x62bCb1BAa29f52b5CE165Db1A6aCEA9972b2f643 , d42e7182f3dda9b1b0353e083c178930bf169073a8b4634cc96cfcc48cd896b9