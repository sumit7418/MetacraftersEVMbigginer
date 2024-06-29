# HDFC BANK Token Smart Contract

## Overview

A smart contract implemented in Solidity for a custom token named "Thanons" (THNS) that supports minting and burning of tokens.

## Description

This Solidity smart contract allows for the minting and burning of tokens. The custom token created here is known as Thanons, with the abbreviation THNS. This code enables the creation of any amount of tokens as required and also allows for the burning of tokens as needed. It ensures that the balance of the account is greater than or equal to the amount that is to be burned. This basic code provides an understanding of how to mint and burn tokens in Solidity.

### Mapping Variable

- *balances*: Maps addresses to their respective token balances.

### Mint Function

The mint function allows new tokens to be created and assigned to a specific address. It takes two parameters:
1. *_address*: The address to which the new tokens will be assigned.
2. *_value*: The number of tokens to be created.

### Burn Function

The burn function allows tokens to be destroyed from a specific address. It takes two parameters:
1. *_address*: The address from which the tokens will be removed.
2. *_value*: The number of tokens to be destroyed.

## Author

- Author: https://github.com/sumit7418/

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Smart Contract Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

contract MyToken {
    // Public variables
    string public tokenName = "HDFC BANK";
    string public tokenAbbrev = "HDFC";
    uint public totalSupply = 100;

    // Mapping variable
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}# MetacraftersEVMbigginer
