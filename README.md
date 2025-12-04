# MyToken - ERC-20 Token Smart Contract

A complete ERC-20 token implementation in Solidity deployed and tested on the Ethereum blockchain.

## Token Details
- **Name:** MyToken
- **Symbol:** MTK
- **Decimals:** 18
- **Total Supply:** 1,000,000 tokens
- **Blockchain:** Ethereum (Tested on Remix JavaScript VM)
- **Solidity Version:** 0.8.0+

## Features
✅ Full ERC-20 Standard Compliance
✅ Transfer Function - Send tokens to another address
✅ Approve Function - Grant spending permissions to another address
✅ TransferFrom Function - Transfer tokens on behalf of another user
✅ Balance Tracking with `balanceOf` mapping
✅ Allowance Management with `allowance` mapping
✅ Transfer and Approval Events for transaction tracking

## Key Functions

### `transfer(address _to, uint256 _value)`
Transfer tokens from the caller to the specified address.
- **Parameters:**
  - `_to`: Recipient address
  - `_value`: Amount of tokens to transfer
- **Returns:** `true` if successful

### `approve(address _spender, uint256 _value)`
Allow a spender to use your tokens up to a specified amount.
- **Parameters:**
  - `_spender`: Address that will be allowed to spend
  - `_value`: Amount they are allowed to spend
- **Returns:** `true` if successful
- **Emits:** `Approval` event

### `transferFrom(address _from, address _to, uint256 _value)`
Transfer tokens on behalf of another address (requires prior approval).
- **Parameters:**
  - `_from`: Address tokens are being transferred from
  - `_to`: Recipient address
  - `_value`: Amount of tokens to transfer
- **Returns:** `true` if successful
- **Emits:** `Transfer` event

### `balanceOf(address account)`
Get the token balance of an address.
- **Returns:** Account's token balance

### `allowance(address owner, address spender)`
Check how many tokens a spender has been approved to use.
- **Returns:** Remaining allowance amount

## Events

### `Transfer(address indexed from, address indexed to, uint256 value)`
Emitted when tokens are transferred.

### `Approval(address indexed owner, address indexed spender, uint256 value)`
Emitted when approval is granted.

## How to Deploy

### Using Remix IDE (Recommended for Testing)
1. Go to [https://remix.ethereum.org](https://remix.ethereum.org)
2. Create a new file named `MyToken.sol`
3. Copy the contract code from `MyToken.sol`
4. Select Solidity Compiler version 0.8.x or higher
5. Compile the contract
6. In the Deploy panel, set `_totalSupply` parameter to `1000000000000000000000000` (1,000,000 tokens with 18 decimals)
7. Click "Deploy" to deploy on Remix JavaScript VM

## Usage Examples

### Transfer Tokens
```solidity
// Transfer 100 tokens to another address
Token.transfer(recipientAddress, 100000000000000000000);
```

### Approve Token Spending
```solidity
// Allow spender to use 50 tokens
Token.approve(spenderAddress, 50000000000000000000);
```

### Transfer on Behalf of Someone
```solidity
// Transfer 25 tokens from approved address to recipient
Token.transferFrom(approvedAddress, recipientAddress, 25000000000000000000);
```

### Check Balance
```solidity
// Get balance of an address
uint256 balance = Token.balanceOf(addressToCheck);
```

## Security Considerations
- ✅ Requires validation of recipient addresses (no zero address transfers)
- ✅ Checks for sufficient balance before transfers
- ✅ Validates allowance before transferFrom operations
- ✅ Emits events for all state-changing operations

## Contract Deployment Details
- **Deployment Address:** 0xD91...39138 (Remix VM)
- **Status:** ✅ Compiled and Tested
- **Network:** Ethereum (JavaScript VM)

## Testing
The contract has been tested with:
- ✅ Successful token transfers
- ✅ Approve and allowance functionality
- ✅ TransferFrom operations
- ✅ Balance tracking
- ✅ Event logging

## License
MIT License - Feel free to use and modify
