# Types-of-Functions---ETH-AVAX

## Introduction
This is a Solidity smart contract for creating and managing a custom ERC20 token called MyToken. The contract allows for token creation, minting, transferring, burning, and ownership management.

## Contract Details
- **Name:** MyToken
- **Symbol:** Custom token symbol
- **Decimals:** Number of decimal places
- **Total Supply:** Initial total supply of tokens
- **Owner:** Address of the contract owner

## Functions
- **Constructor:** Initializes the token with specified parameters.
- **mint:** Allows the owner to mint new tokens and assign them to a specified address.
- **transfer:** Enables users to transfer tokens to other addresses.
- **burn:** Allows users to burn a specific amount of their tokens.
- **isOwner:** Checks whether the caller is the owner of the contract.

## Usage
### Running on Remix
1. Open Remix IDE (https://remix.ethereum.org/).
2. Create a new Solidity file and paste the contract code.
3. Compile the contract by selecting the appropriate Solidity version and clicking the "Compile" button.
4. Deploy the contract by switching to the "Deploy & Run Transactions" tab, selecting the appropriate environment (e.g., JavaScript VM, Injected Web3), and clicking "Deploy".
5. Once deployed, interact with the contract using the provided functions in the Remix interface.

### Example Usage
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MyToken {
    string public name;
    string public symbol;
    uint8 public decimals;
    uint256 public totalSupply;
    address public owner;
    
    mapping(address => uint256) public balanceOf;
    
    event Transfer(address indexed from, address indexed to, uint256 value);
    event Burn(address indexed from, uint256 value);
    
    modifier onlyOwner() {
        require(msg.sender == owner, "Only owner can call this function");
        _;
    }
    
    constructor(
        string memory _name,
        string memory _symbol,
        uint8 _decimals,
        uint256 _initialSupply
    ) {
        name = _name;
        symbol = _symbol;
        decimals = _decimals;
        totalSupply = _initialSupply * 10 ** uint256(_decimals);
        owner = msg.sender;
        balanceOf[msg.sender] = totalSupply;
    }
    
    function mint(address _to, uint256 _amount) public onlyOwner {
        require(_to != address(0), "Invalid address");
        balanceOf[_to] += _amount;
        totalSupply += _amount;
        emit Transfer(address(0), _to, _amount);
    }
    
    function transfer(address _to, uint256 _value) public {
        require(_to != address(0), "Invalid address");
        require(balanceOf[msg.sender] >= _value, "Insufficient balance");
        
        balanceOf[msg.sender] -= _value;
        balanceOf[_to] += _value;
        emit Transfer(msg.sender, _to, _value);
    }
    
    function burn(uint256 _value) public {
        require(balanceOf[msg.sender] >= _value, "Insufficient balance");
        
        balanceOf[msg.sender] -= _value;
        totalSupply -= _value;
        emit Burn(msg.sender, _value);
    }
    
    function isOwner() public view returns (bool) {
        return msg.sender == owner;
    }
}

```
