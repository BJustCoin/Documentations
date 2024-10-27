# Oracle
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/flatten/ICOManager_flatten.sol)


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


```solidity
function getLatestPrice() public view returns (int256);
```

## Errors
### GetLastPriceError

```solidity
error GetLastPriceError();
```

