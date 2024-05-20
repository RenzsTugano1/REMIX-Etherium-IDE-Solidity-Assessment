# REMIX-Etherium-IDE-Solidity-Assessment

This Solidity Program is a  simple requirement that requires public variables, mapping variables, mint function and burn function for our so-called contract.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. 
There will be public variables in our contract because for that store the details about your coin (Token Name, Token Abbr., Total Supply)
Our contract will have a mapping of addresses to balances (address => uint)
We will have a mint function that takes two parameters: an address and a value. 
The function then increases the total supply by that number and increases the balance of the “sender” address by that amount
We will also have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”.
Lastly, our burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned.


## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.18+commit.87f61d96.js

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

```javascript
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
   string public tokenName =  "Renzo";
   string public tokenAbbrv = "Renzs";
   uint public totalSupply = 0;
    // mapping variable here
   mapping(address => uint) public balance;

    // mint function
   function mint(address _address, uint _value) public { 
      totalSupply += _value;
      balance[_address] += _value;
   }

   // burn function
   function burn(address _address, uint _value) public {
      if (balance[_address] >= _value) {
         totalSupply -= _value;
         balance[_address] -= _value;
      }
   }
}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, find the account at the top of deploy and transaction, then press copy account to clip board on the left side of the account. In mint press the down arrow on the left side and you will see the address here, and paste the copy into the account.

Below the address there is a value on the right side of the search bar. Type 1000 and press transact at the bottom. In the balance paste the copy of the account. 

In burn, press the down arrow and in the address, paste the copy of the account. In value type 500.

At the bottom find the total supply and press it. Once you press 500 will appear in the uint. You finally finished.

## Authors

Renzo Tugano BSIT 
@RenzsTugano1

# License

Copyright (c) 2024 RenzsTugano1

