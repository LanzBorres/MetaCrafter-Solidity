# MetaCrafterSolidity Assesment
In this assessment, I learned how to make our own token using Solidity programming language.

## Description

This program is a simple contract written in Solidity on how to make our very own token on the Ethereum blockchain.

## Getting Started

### Executing program

To run this program, we will use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are in the webpage go click file explorer then create new space choose blank template and name your waorkspace name then ok. 
 After that you can now copy and paste the code below:

 ```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;




/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value.
       The function then increases the total supply by that number and increases the balance
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens.
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal
       to the amount that is supposed to be burned.
*/
contract MetaSol {


    string public tokenName = "YOUTHTALENT";
    string public tokenAbbrv = "YOTA";
    uint public totalSupply = 0;


    mapping (address => uint) public balances;


    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }


    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value){
           totalSupply -= _value;
           balances[_address] -= _value;
        }
    }
 


}

```
To test the code, go to "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "MetaSol.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MetaSol" contract from the dropdown menu, and then click on the "Deploy" button.


Once you see the "MetaSol" pop out in the Deployed contracts, go click the arrow then you will see the burn,mint,balances,tokenAbbrv,tokenName, and totalSupply. 
