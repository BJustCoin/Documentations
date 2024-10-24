# Oracle
[Git Source](https://github.com/BJustCoin-creator/BJC/blob/afa8ae44b1c3660a047e437225fc640502d221b6/src/Oracle.sol)


## State Variables
### priceFeed

```solidity
AggregatorV3Interface internal priceFeed;
```


## Functions
### constructor


```solidity
constructor();
```

### getLatestPrice


```solidity
function getLatestPrice() public view returns (int256 price);
```

## Errors
### GetLastPriceError

```solidity
error GetLastPriceError();
```

