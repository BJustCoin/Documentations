# VestingManager
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/VestingManager.sol)

**Inherits:**
[Ownable](/src/flatten/ICOManager_flatten.sol/abstract.Ownable.md)

The main task of a smart contract is to create instances of vestingTokens and set a vesting schedule on them

**


## State Variables
### _vestingImplementation

```solidity
address private immutable _vestingImplementation;
```


## Functions
### constructor


```solidity
constructor(address implementation) Ownable(msg.sender);
```

### createVesting

The main function for creating an instance of a vestingTokens
setting the name and symbol
We specify the address of the token that will be blocked for vesting
We specify the address that will be able to use share tokens (for example, a sales contract)
Passing the schedule


```solidity
function createVesting(
    string calldata name,
    string calldata symbol,
    address baseToken,
    address minter,
    Vesting calldata vesting
) external onlyOwner returns (address vestingToken);
```

### _createVestingToken

*create new token*


```solidity
function _createVestingToken(string calldata name, string calldata symbol, address minter, address baseToken)
    private
    returns (address vestingToken);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`name`|`string`| name token|
|`symbol`|`string`|symvol token|
|`minter`|`address`| the address that owns the right to mint new token|
|`baseToken`|`address`| base token|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`vestingToken`|`address`| address new token|


## Events
### CreateVestingToken

```solidity
event CreateVestingToken(address indexed addressToken, string name, string symbol);
```

## Errors
### ImplementationError

```solidity
error ImplementationError();
```

