# Bjustcoin
[Git Source](https://github.com/BJustCoin-creator/BJC/blob/afa8ae44b1c3660a047e437225fc640502d221b6/src/Bjustcoin.sol)

**Inherits:**
ERC20, Ownable

**Author:**
Code Tesla Labs

Token ICO

*Token ICO*


## State Variables
### INITIAL_SUPPLY

```solidity
uint256 private constant INITIAL_SUPPLY = 100_000_000 * 1e18;
```


### blacklists

```solidity
mapping(address => bool) public blacklists;
```


## Functions
### constructor


```solidity
constructor(address initialOwner) ERC20("Bjustcoin", "BJC") Ownable(initialOwner);
```

### blacklist

Adding or removing an address to the blacklist

*Adding or removing an address to the blacklist*


```solidity
function blacklist(address _address, bool _isBlacklisting) external onlyOwner;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`_address`|`address`| Address additing or removing to the blacklist|
|`_isBlacklisting`|`bool`| true - add; false - remove;|


### burn

burn BJustCoin

*burn BJustCoin*


```solidity
function burn(uint256 amount) external onlyOwner;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`amount`|`uint256`| count burn token|


### _update

token transfer

*token transfer*


```solidity
function _update(address from, address to, uint256 value) internal virtual override;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`from`|`address`| address from|
|`to`|`address`| address to|
|`value`|`uint256`| count tokens|


## Errors
### Blacklisted

```solidity
error Blacklisted();
```

