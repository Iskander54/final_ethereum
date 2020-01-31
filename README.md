# landreg

## Introduction

**LandReg** is a standalone smart contract that can be used to run a land registry. Plus, any user can lend money to any other user to buy one property. Each Property is identified by its PIN(int). 

It is written in [Solidity](https://solidity.readthedocs.io/en/v0.5.3/index.html) and compiled using `solc` version [0.5.0](https://github.com/ethereum/solidity/releases/tag/v0.5.0).

It can be deployed to an [Ethereum](https://ethereum.org) blockchain, be it the public [mainnet](https://etherscan.io), a public testnet like [Rinkeby](https://rinkeby.etherscan.io), a private blockchain, or on a local development blockchain like [Ganache](https://truffleframework.com/ganache).

It uses Ethereum's native [Ether](https://www.ethereum.org/ether) for and fees and payments required.

## High-level Solution

The **Land Registry** contracts manages a few features:

### Administrate the Registry

- **Add a Property** - Any user can add a property to the registry
- **Update a Property** - The contract owner can update a property to the registry
- **Delete a Property** - The contract owner can delete a property to the registry

### Lending money
- **Submit a transaction** - Any user can lend ether to any other user to transfer the ownership a property. For the ownership of the property to be transfer, every (lender of the money, the receiver that wants to buy a property and sell) party has to confirm the transaction. The smart contracts update directly the registry.
- **Confirm a transaction** Any user involved in a transaction can sign transaction it.
- **Revoke a transaction**  If you have changed your mind after having confirmed the transaction before all the parties have signed the transaction, you can revoke your confirmation. 

## Enhancements

A list of possible enhancements for this contract are:

- Implement a regularly payback from the one who receiver the money to the lender
- Implement a multi-ownership properties
- Use a token to represent a property



**Land Registry** was developed as [my](https://github.com/Iskander54) final project for the [ConsenSys Academy Developer Program Bootcamp](https://consensys.net/academy/bootcamp).

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

### Prerequisites
- [Docker](https://www.docker.com/)
- [Docker-compose](https://docs.docker.com/compose/): write the configuration of your containers in a `docker-compose.yml` file


1. Clone the repository, ie `git clone https://github.com/Iskander54/final_ethereum`

1. Go into the repository and type `docker-compose build` to build the image

1. Type `docker-compose up` to launch the app

1. Go to your browser on `localhost:3001`
### [Option] Run Docker with your own ganache

You can run the dApp with your own ganache, to do so :

1. Clone the repository, ie `git clone https://github.com/Iskander54/final_ethereum`

1. Go in the `final_ethereum/landreg`

1. Type `docker build -t landreg .`

1. Type `docker run landreg HOST=XXXX PORT=XXX NETWORKID=XXXX` using the corresponding ganache parameters (you can see the default environment variable in the dockerfile used for docker-compose)

In the docker-compose, Only 4 accounts have been imported :
- 0x42CAD0CA3716b4664c2658A0a48664369D511C54 , 80d7110b676b1cb7f719bc7aa639a10a6d1611f1bd5ff7e94995da52915710de
- 0xDf7064894A0da6b741b86104af7875647b7767A3 , ae327c532fcc5254b701ca2a10f198787b93d37fe5c78cfe8531ce4373aa182e
- 0x229846d7818D13a468cB9767c04e375a82CE0e3D , 85b4ae0e89b5dd0ac460dcf1806af39c0ce59ee567f56d520ba1c0144a5a1537
- 0x62bCb1BAa29f52b5CE165Db1A6aCEA9972b2f643 , d42e7182f3dda9b1b0353e083c178930bf169073a8b4634cc96cfcc48cd896b9

---

## Project Specifications

- [x] A README.md that explains the project
  - [x] What does it do?
  - [x] How to set it up.
    - [x] How to run a local development server.
- [x] It should be a [Truffle project](https://truffleframework.com/docs/truffle/getting-started/creating-a-project).
  - [x] All contracts should be in a `contracts` directory.
    - [x] `truffle compile` should successfully compile contracts.
  - [x] Migration contract and migration scripts should work.
    - [x] `truffle migrate` should successfully migrate contracts to a locally running `ganache-cli` test blockchain on port `8454`.
  - [x] All tests should be in a `tests` directory.
    - [x] `truffle test` should migrate contracts and run the tests.
- [x] Smart contract code should be commented according to the [specs in the documentation](https://solidity.readthedocs.io/en/v0.5.2/layout-of-source-files.html#comments).
- [x] Create at least 5 tests for each smart contract.
  - [x] Write a sentence or two explaining what the tests are covering, and explain why those tests were written.
- [x] A development server to serve the front-end interface of the application.
  - [x] It can be something as simple as the [lite-server](https://www.npmjs.com/package/lite-server) used in the [Truffle Pet Shop tutorial](https://truffleframework.com/tutorials/pet-shop).
- [x] A document [design_pattern_decisions.md](design_pattern_decisions.md) that explains the design patterns chosen.
- [x] A document [avoiding_common_attacks.md](avoiding_common_attacks.md) that explains what measures were taken to ensure that the contracts are not susceptible to common attacks.
- [x] Implement/use a library or an EthPM package.
  - [ ] If the project does not require a library or an EthPM package, demonstrate how it would do that in a contract called `LibraryDemo.sol`.
- [ ] Develop your application and run the other projects during evaluation in a VirtualBox VM running Ubuntu 16.04 to reduce the chances of runtime environment variables.


---

## Project Requirements

### User Interface

- [x] Run the dapp on a development server locally for testing and grading.
- [x] You should be able to visit a URL and interact with the application:
  - [x] App recognizes current account;
  - [x] Sign transactions using MetaMask or uPort;
  - [x] Contract state is updated;
  - [x] Update reflected in UI.

### Testing

- [x] Write 5 tests for each contract you wrote;
  - [x] Solidity **or** JavaScript.
- [x] Explain why you wrote those tests;
  - [x] Tests run with `truffle test`.

### Design Patterns

- [x] Implement a circuit breaker (emergency stop) pattern.
- [x] What other design patterns have you used / not used?
  - [x] Why did you choose the patterns that you did?
  - [ ] Why not others?

### Security Tools / Common Attacks

- [x] Explain what measures you have taken to ensure that your contracts are not susceptible to common attacks.

### Use a Library or Extend a Contract

- [x] Via EthPM or write your own.

### Deployment

- [x] Deploy your application onto one of the test networks.
- [x] Include a document called [deployed_addresses.txt](deployed_addresses.txt) that describes where your contracts live (which testnet and address).
- [x] Students can verify their source code using Etherscan https://etherscan.io/verifyContract for the appropriate testnet.
- [x] Evaluators can check by getting the provided contract ABI and calling a function on the deployed contract at https://www.myetherwallet.com/#contracts or checking the verification on Etherscan.

### Stretch

- [ ] Implement an upgradable design pattern.
- [ ] Write a smart contract in LLL or Vyper.
- [ ] Integrate with an additional service. For example:
  - [ ] IPFS - users can dynamically upload documents to IPFS that are referenced via their smart contract.
  - [ ] uPort
  - [ ] Ethereum Name Service - a name registered on the ENS resolves to the contract, verifiable on `https://rinkeby.etherscan.io/<contract_name>`
  - [ ] Oracle