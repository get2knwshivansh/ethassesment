# MyToken Smart Contract

This Solidity program is a simple ERC20-like token contract that demonstrates basic functionality for minting and burning tokens. It allows users to mint new tokens and burn existing ones while maintaining a balance system for each address. The contract includes basic features like token name, abbreviation, and total supply tracking.

## Description

The MyToken contract provides a simple token model, where users can mint new tokens, burn existing tokens, and check their token balances. This contract demonstrates key concepts in Solidity like public variables, mappings, and conditionals. It can be expanded upon to create more complex token functionality or integrated into other decentralized applications (dApps).

### Features
- *Public Variables:* Stores token details like name, abbreviation, and total supply.
- *Mapping:* Tracks balances for each address.
- *Mint Function:* Allows increasing the total supply and balance of a specified address.
- *Burn Function:* Allows reducing the total supply and balance of a specified address with a condition to prevent burning more than the balance.

## Requirements

1. *Token Details:*  
   The contract has public variables that store the token name, abbreviation, and total supply.
   
2. *Balances Mapping:*  
   The contract maintains a mapping that tracks the balance of each address.

3. *Minting Tokens:*  
   The mint function allows an address to receive new tokens and increases the total supply accordingly.

4. *Burning Tokens:*  
   The burn function decreases the total supply and the balance of the sender’s address, provided the sender has enough tokens.

## Getting Started

### Executing the Program

To run this program, you can use Remix, an online Solidity IDE. Follow the steps below to deploy and interact with the contract.

#### Steps:

1. Visit [Remix IDE](https://remix.ethereum.org/).

2. Create a new file with a .sol extension (e.g., MyToken.sol).

3. Copy and paste the following Solidity code into your file:

    solidity
    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;

    contract MyToken {

        // public variables here
        string public tokenName = "Shivansh";
        string public tokenAbbrv = "Shiv";
        uint public totalSupply = 0;

        // mapping variable here
        mapping(address => uint) public balances;

        // mint function
        function mint (address _address, uint _value) public {
            totalSupply += _value ;
            balances[_address] += _value;
        }

        // burn function
        function burn (address _address, uint _value) public{
            if (balances[_address] >= _value) {
                totalSupply -= _value;
                balances[_address] -= _value;
            }
        }
    }
    

4. Compile the contract:
   - Click on the "Solidity Compiler" tab in the left-hand sidebar.
   - Ensure the compiler version is set to 0.8.18 or a compatible version.
   - Click "Compile MyToken.sol."

5. Deploy the contract:
   - Open the "Deploy & Run Transactions" tab.
   - Select MyToken from the contract dropdown menu.
   - Click the "Deploy" button.

6. Interact with the contract:
   - Use the mint function to mint tokens for an address.
   - Use the burn function to burn tokens from an address.
   - Check the totalSupply and the balance of any address using the public variables.


## Author

Shivansh Mishra
[mishrashivansh231@gmail.com]


## License

This project is licensed under the MIT License.
