# Token.sol

This is a simple Solidity program to getting started with creating our token. It takes a super beginner approach at understanding the internal workings in the operations of a cryptocurrency. This is a simple contract to explore the starting point of Web3 Development.

## Description

Solidity is a programming language used for creating smart contracts on the Ethereum blockchain network. This is a simple Solidity program to create a smart contract named "MyToken" to create a cryptocurrency by the name of "DATCOIN" abbreviated as "DTC" whose initial supply is 0. It contains a mapping of addresses to balances. Mapping is like dictionaries in Python for efficient retrieval of data. It also contains two functions. The mint function accepts an address and a value, and increments both the total supply and the balance of the address with the specified value. The burn function accepts the address and value, and if the sender has enough available balance, it decrements the total supply and balance of the address by the value.

## Getting Started

### Executing program
Remix is an online Solidity IDE available at https://remix.ethereum.org/. It has the look of Visual Studio Code and can be used to get started with Web3 Development. Go to the before stated website and create a new file with a .sol extension (e.g., Token.sol). Copy and paste the following code.

```javascript
pragma solidity ^0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "DATCOIN";
    string public tokenAbbr = "DTC";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public 
    {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public 
    {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }     
    }
}

```

Hit Control + S to compile. Then deploy the contract by clicking "Deploy & run transactions" on the left hand side bar. Click on the "Deploy" button. The contract is now deployed. Use the mint function to mint some tokens and the burn function to burn the cyptocurrency.

## Authors

Aditya
