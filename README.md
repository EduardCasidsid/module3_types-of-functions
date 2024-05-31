# Assessment3 Types Of Function

`Assessment3` is an ERC20-compliant token contract with custom events for transfer, minting, and burning operations. The token is named "Eduard" with the symbol "Ward."

# Features

- **ERC20 Standard**: The contract follows the ERC20 token standard using OpenZeppelin's implementation.
- **Custom Events**: Emits custom events (`TransferCustom`, `Burn`, `Mint`) to provide additional information about token transfers, burns, and mints.
- **Minting**: Allows the creation of new tokens.
- **Burning**: Allows users to destroy their tokens, reducing the total supply.

# Deployment

The contract initializes with an initial supply of tokens minted to the deployer's address.

# Initial Supply

The initial supply is set to `30 * (2 * uint256(decimals()))` tokens, where `decimals()` is typically 18 for ERC20 tokens. This means the initial supply is `30 * (2 * 10^18)` tokens.

# Events

- **TransferCustom**: Emitted when tokens are transferred.
  ```solidity
  event TransferCustom(address indexed from, address indexed to, uint256 value);
  ```

- **Burn**: Emitted when tokens are burned.
  ```solidity
  event Burn(address indexed burner, uint256 value);
  ```

- **Mint**: Emitted when new tokens are minted.
  ```solidity
  event Mint(address indexed to, uint256 value);
  ```

# Functions

# `transfer`

Transfers tokens from the caller to a recipient address and emits a `TransferCustom` event.

```solidity
function transfer(address recipient, uint256 amount) public virtual override returns (bool)
```

### `burn`

Allows the caller to burn a specified amount of their tokens and emits a `Burn` event.

```solidity
function burn(uint256 amount) public
```

### `mint`

Allows the creation of new tokens and assigns them to a specified address. Emits a `Mint` event.

```solidity
function mint(address to, uint256 amount) public
```

# Example Usage

### Deployment

Deploy the contract using Remix, Truffle, Hardhat, or any other Ethereum development framework.

### Transferring Tokens

```solidity
Assessment3 token = Assessment3(contractAddress);
token.transfer(recipientAddress, amount);
```

### Burning Tokens

```solidity
token.burn(amount);
```

### Minting Tokens

```solidity
token.mint(recipientAddress, amount);
```
# Owner
Eduard Casidsid

# License

This project is licensed under the MIT License.

