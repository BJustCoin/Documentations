# Oracle
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/Oracle.sol)


## State Variables
### priceFeed

```solidity
AggregatorV3Interface internal immutable priceFeed;
```


## Functions
### constructor


```solidity
constructor();
```

### getLatestPrice

usd/eth exchange rate in cents


```solidity
function getLatestPrice() public view returns (int256);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`int256`|int256  rate in cents|


## Errors
### GetLastPriceError

```solidity
error GetLastPriceError();
```

