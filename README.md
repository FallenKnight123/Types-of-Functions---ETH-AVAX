# MyToken Solidity Contract

This Solidity contract is an implementation of an ERC20 token named "MyToken" with the symbol "ETH". It provides functionalities for token minting, transferring, and burning.

## Functionality

- Only the contract owner can mint tokens.
- Any user can transfer tokens.
- Any user can burn tokens.

## Usage

### Remix IDE

1. Open the Remix IDE.
2. Create a new file and name it `MyToken.sol`.
3. Copy and paste the contract code into `MyToken.sol`.
4. Deploy the contract:
   - Select the appropriate compiler version (e.g., ^0.8.0).
   - Compile the contract.
   - Deploy the contract using the appropriate environment (e.g., JavaScript VM, Injected Web3, etc.).
5. Interact with the deployed contract:
   - Mint tokens by calling the `mint` function with the desired recipient address and amount.
   - Transfer tokens by calling the `transfer` function with the recipient address and amount.
   - Burn tokens by calling the `burn` function with the desired amount.

### Solidity Compiler

You can also compile and deploy the contract using other Solidity development tools or platforms.
