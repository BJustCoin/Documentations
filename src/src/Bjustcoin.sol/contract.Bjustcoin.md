# Bjustcoin
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/Bjustcoin.sol)

**Inherits:**
[ERC20](/src/flatten/ICOManager_flatten.sol/abstract.ERC20.md), [Ownable](/src/flatten/ICOManager_flatten.sol/abstract.Ownable.md)

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

burn BJustCoin. It is used if, at the end of the ICO, there are unsold tokens allocated for all stages of the ICO

*burn BJustCoin. It is used if, at the end of the ICO, there are unsold tokens allocated for all stages of the ICO*


```solidity
function burn(uint256 amount) external onlyOwner;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`amount`|`uint256`| count burn token|


### _update

*moving tokens between wallets. If one of the participants is blacklisted, the Blacklisted error is called*


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

