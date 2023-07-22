# SOLIDITYX
[![Solidity](https://img.shields.io/badge/Solidity-0.8.18-blue)](https://soliditylang.org/)
[![Metacrafter](https://img.shields.io/badge/Metacrafter-Amazing-orange)](https://www.metacrafters.io/)

A baisc Solidity program to create a dummy token `SOLIDITYX` .  

## Description

The program contains a simple smart contract, `MyToken` written in **Solidity** language. Basically we are keeping track of the `totalSupply` and the `balance` of each address.

To do so, program has two function, `mint` and `burn`. First one, add the value to the total supply and balance of given address while the second does the the opposite.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    string public tokenName = "SOLIDITYX";
    string public tokenAbbr = "SOLX";
    uint public totalSupply = 0;

    mapping(address => uint) public balances;

    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    
    function burn(address _address, uint _value) public {
        if(balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the `mint` or `burn` function. You can get the address from the remix ide sidebar only.

## Authors

Pranay Raj

[Linkedin](https://www.linkedin.com/in/masterpranay1)
