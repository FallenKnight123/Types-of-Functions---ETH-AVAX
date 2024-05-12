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
// Deploy the contract
MyToken token = new MyToken("MyToken", "MTK", 18, 1000000);

// Mint tokens
token.mint(address recipient, uint256 amount);

// Transfer tokens
token.transfer(address recipient, uint256 amount);

// Burn tokens
token.burn(uint256 amount);

// Check ownership status
bool isOwner = token.isOwner();

```
