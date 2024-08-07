
# Multi-Send Application


The Multi-Send Application is a smart contract built on the Ethereum blockchain that allows users to send multiple transactions from a single wallet in one go. This application is useful for scenarios where multiple payments need to be processed simultaneously, saving time and reducing transaction fees.

## Features

- Send Ether to multiple recipients in a single transaction.
- Easy to deploy and use.
- Built with Solidity and compatible with Ethereum-based networks.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- You have installed [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/).
- You have installed [Truffle Suite](https://www.trufflesuite.com/).
- You have a MetaMask wallet or another Ethereum wallet.
- You have some Ether in a testnet wallet (Rinkeby, Kovan, or Ropsten).

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/multi-send-application.git
    ```

2. Navigate to the project directory:

    ```bash
    cd multi-send-application
    ```

3. Install the dependencies:

    ```bash
    npm install
    ```

## Usage

### Deploying the Contract

1. Open the `truffle-config.js` file and configure the network settings for the desired Ethereum testnet (e.g., Rinkeby, Kovan, or Ropsten).

2. Compile the smart contracts:

    ```bash
    truffle compile
    ```

3. Deploy the contracts to the specified network:

    ```bash
    truffle migrate --network <network-name>
    ```

### Interacting with the Contract

1. Open the `index.html` file in your preferred web browser.

2. Connect your MetaMask wallet to the web application.

3. Enter the recipient addresses and corresponding amounts in the provided fields.

4. Click the "Send" button to execute the multi-send transaction.

### Smart Contract Code

The smart contract is located in the `contracts` directory. Here is an overview of the `MultiSend.sol` contract:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MultiSend {
    function multiSend(address[] memory recipients, uint256[] memory amounts) public payable {
        require(recipients.length == amounts.length, "Arrays must be the same length");
        for (uint256 i = 0; i < recipients.length; i++) {
            (bool sent, ) = recipients[i].call{value: amounts[i]}("");
            require(sent, "Failed to send Ether");
        }
    }
}



## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


## API Reference

#### Get all items

```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |

#### add(num1, num2)

Takes two numbers and returns the sum.


## Appendix

Any additional information goes here


## Authors

- [@octokatherine](https://www.github.com/octokatherine)


## Badges

Add badges from somewhere like: [shields.io](https://shields.io/)

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)

