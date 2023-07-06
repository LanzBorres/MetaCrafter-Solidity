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
To test the code, follow these steps:

1. Open the "Solidity Compiler" tab in the left-hand sidebar.
2. Ensure that the "Compiler" option is set to "0.8.18" (or another compatible version).
3. Click the "compile MetaSol.sol" button to open the contract file.
4. Once the code is compiled without any errors, proceed to deploy the contract.
5. Switch to the "Deploy & Run Transactions" tab in the left-hand sidebar.
6. From the dropdown menu, select the "MetaSol" contract.
7. Click on the "Deploy" button to deploy the contract to the blockchain.
8. Once the deployment is successful, you will see the "MetaSol" contract listed under "Deployed contracts".
9. Click the arrow next to the contract to expand it and view its functions and variables.
10. You can interact with the contract by using the provided functions such as "burn", "mint", "balances", "tokenAbbrv", "tokenName", and "totalSupply".
11. To mint tokens, copy the Ethereum address from the "Account" section and paste it into the "mint" address field. Enter the desired token amount and click the "transact" button to verify the transaction.
12. After minting tokens, you can check the updated "totalSupply" value by clicking on it in the contract interface. You can also check the token balance for a specific address by pasting the Ethereum address into the "balance" field.
13. To burn tokens, click on the address field, paste the Ethereum address associated with the account holding the tokens, enter the desired amount to burn, and click the "transact" button to initiate the burning process.

By following these steps, you can test the functionalities of the contract, including minting tokens, checking balances, and burning tokens.
