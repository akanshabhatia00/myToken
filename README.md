# MyToken Project

## Overview

MyToken is a basic implementation of an ERC-20-like token on the Ethereum blockchain using Solidity. This smart contract allows for the minting and burning of tokens, and it keeps track of the total supply and individual balances.

## Features

- *Token Details*: The contract stores the token's name, abbreviation, and total supply.
- *Minting*: New tokens can be created and assigned to addresses.
- *Burning*: Tokens can be destroyed (burned) from addresses, reducing the total supply.
- *Balance Tracking*: The contract maintains a balance for each address that holds tokens.

## Token Specifications

- *Token Name*: BasicToken
- *Token Abbreviation*: BTK
- *Initial Total Supply*: 0 (can be increased by minting)

## Contract Code

solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract myToken {
    string public tokenName = "BasicToken";
    string public tokenAbbry = "BTK";
    uint public totalSupply = 0;

    mapping(address => uint) public balanceOf;

    function mint(address _address, uint _amount) public {
        totalSupply += _amount;
        balanceOf[_address] += _amount;
    }

    function burn(address _address, uint _amount) public {
        if (balanceOf[_address] >= _amount) {
            totalSupply -= _amount;
            balanceOf[_address] -= _amount;
        }
    }
}


## Functions

### mint

solidity
function mint(address _address, uint _amount) public


- *Description*: Mints new tokens and assigns them to the specified address.
- *Parameters*:
  - _address (address): The address to receive the minted tokens.
  - _amount (uint): The number of tokens to mint.
- *Effects*:
  - Increases the totalSupply by _amount.
  - Increases the balance of _address by _amount.

### burn

solidity
function burn(address _address, uint _amount) public


- *Description*: Burns tokens from the specified address, reducing the total supply.
- *Parameters*:
  - _address (address): The address from which the tokens will be burned.
  - _amount (uint): The number of tokens to burn.
- *Effects*:
  - Decreases the totalSupply by _amount if _address has at least _amount tokens.
  - Decreases the balance of _address by _amount.

## Getting Started

### Prerequisites

- *Solidity Compiler*: Version 0.8.18
- *Ethereum Development Environment*: Such as [Remix IDE](https://remix.ethereum.org/), [Truffle](https://www.trufflesuite.com/), or [Hardhat](https://hardhat.org/).

### Deployment

1. Open your preferred Ethereum development environment.
2. Create a new Solidity file and copy the contract code into it.
3. Compile the contract using Solidity version 0.8.18.
4. Deploy the contract to your chosen Ethereum network (local, testnet, or mainnet).

### Interacting with the Contract

- *Mint Tokens*: Call the mint function with the recipient's address and the amount of tokens to mint.
- *Burn Tokens*: Call the burn function with the address to burn from and the amount of tokens to burn.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by the ERC-20 token standard.
- Developed using Solidity and Ethereum tools.

---

