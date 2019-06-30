# eth-todo-list

## Introduction

The code in this repository corresponds to the work done while following along with the tutorial [in this DApp University tutorial](https://www.youtube.com/watch?v=coQ5dg8wM2o)

## Table of Contents

- [eth-todo-list](#eth-todo-list)
  - [Introduction](#Introduction)
  - [Table of Contents](#Table-of-Contents)
  - [About](#About)
  - [Requirements](#Requirements)
  - [Installation](#Installation)
  - [Usage](#Usage)
  - [Testing](#Testing)
  - [Structure](#Structure)
  - [Issues](#Issues)
  - [Author](#Author)

## About

This repository is a beginner's tutorial to the Ethereum Blockchain, Solidity Contract Development, and connecting an app to a blockchain.

## Requirements

- [Truffle](https://www.trufflesuite.com/docs/truffle/getting-started/installation)
- [Ganache](https://www.trufflesuite.com/ganache)
- Solidity
- Node.js
- Chai
- Bootstrap
- Lite Server
- Nodemon
- [MetaMask](https://metamask.io)

## Installation

In your terminal, git clone the repository with the following command:

```bash
git clone https://github.com/biehlerj/holbertonschool-linux_programming
```

After you have cloned the repo make sure to run the following commands to have all your Node.js dependencies installed, the Solidity compiled, and the migrations run:

```npm
npm i[nstall]
truffle compile
truffle migrate [--reset]
```

## Usage

When you are ready to test the app set up Ganache. To do that open the desktop application for Ganache and select the `Quickstart` option. After selecting the quick start option run `npm run dev` on the command line (if you make any changes the solidity file or add extra contracts or functionality be sure to run `truffle migrate --reset` before running `npm run dev`).

Now that you have the app running make sure to set up your MetaMask extension correctly. If you have never set up MetaMask the easiest way to do so is to create a new wallet and follow the steps. After you have created a new wallet follow the following steps:

First, create a new network that corresponds to the blockchain that Ganache is running for you by selecting the `Custom RPC` option in the drop down menu at the top middle of the extension. In the `New RPC URL` field type the `RPC Server` info as specified by Ganache (typically this is set to `HTTP://127.0.0.1:7545`). After you have created the custom RPC create a new account by selecting the icon in the upper right corner of the extension and clicking import account. Make sure the type is set to `Private Key`. To get a key go to Ganache and click the key icon under the top most account (right under the mnemonic) and copy the key and paste it into the extension and create the account. After you've created the account you are good to go. Any changes you make while updating the app.js file or after running `truffle migrate --reset` will cause the app to reload.

## Testing

To test the app run the following command:

```npm
truffle test
```

If you want to add more tests for the `TodoList` add them under `test/TodoList.test.js`. If you create another contract that you want to test follow the convention set by `TodoList` (ex. `test/Foo.test.js`).

## Structure

1. [build](./build)
   1. [contracts](./build/contracts)
   | File | Description |
   | ---- | ----------- |
   | Migrations.json | JSON Data related to the Migrations Contract. This allows any connecting web app to read public information about the contract or use any public functions related to the contract |
   | TodoList.json | JSON Data related to the TodoList Contract. This allows any connection web app to read public information about the contract or use any public functions related to the contract |
2. [contracts](./contracts)
   | File | Description |
   | ---- | ----------- |
   | Migrations.sol | Solidity code that describes the structure of the Contract and any actions that can be made against the Contract |
   | TodoList.sol | Solidity code that describes the structure of the Contract and any actions that can be made against the Contract |
3. [migrations](./migrations)
   | File | Description |
   | ---- | ----------- |
   | 1_initial_migration.js | Initial migration file provided by Truffle |
   | 2_deploy_contracts.js | Migration file that deploys the TodoList contract to the blockchain |
4. [src](./src)
   | File | Description |
   | ---- | ----------- |
   | app.js | JavaScript code for the frontend of the TodoList. Allows a user to create, complete, or uncomplete a task. |
   | index.html | Basic HTML file that renders the tasks in the browser |
5. [test](./test)
   | File | Description |
   | ---- | ----------- |
   | TodoList.test.js | Tests for making sure a contract is successfully executed when a task is manipulated |
6. Base directory
   | File | Description |
   | ---- | ----------- |
   | .gitignore | Files to ignore adding to the git repo |
   | .soliumignore | Linter rules |
   | .soliumrc.json | Solium linting rules |
   | bs-config.json | Configuration for browers to know where to find the code it is looking for |
   | package-lock.json | Information about the node modules installed and their dependencies |
   | package.json | Information about the project, scripts that are available, and dependencies for Node.js |
   | README.md | This file describing the contents of the project |
   | truffle-config.js | Describes the details of where the blockchain is located for the project on the network and how to use the [solc](https://github.com/ethereum/solc-js#readme) Solidity JavaScript compiler. |

## Issues

All known issues that I could not fix are listed below and their implications:

| Issue | Cause | Implication |
| ----- | ----- | ----------- |
| Security vulnerabilities with packages in the `package.json`. | Issue with Node.js (version 12.3.1) packages `diff` and `web3` that are currently unfixable | `diff`: A vulnerability was found in diff before v3.5.0, the affected versions of this package are vulnerable to Regular Expression Denial of Service (ReDoS) attacks, `web3`: All versions of web3 are vulnerable to Insecure Credential Storage. |

## Author

The author of the tutorial is Gregory from [Dapp University](http://www.dappuniversity.com/) where you can find other Blockchain tutorials and information.

The code was formatted using linters by Jacob Biehler (me). You can find me on various forms of Social Media below:

[LinkedIn](https://www.linkedin.com/in/jacob-biehler-475573139/)

[Twitter](https://twitter.com/Biehlerj)

[GitHub](https://github.com/biehlerj)

Finally shameless plug for my new favorite browser where I tested all of my code. If you are privacy minded, interested in blockchain, and want a fast, smooth web experience check out [Brave Browser](https://brave.com/jac110).
