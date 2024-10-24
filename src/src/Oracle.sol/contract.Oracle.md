# Oracle
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/a2ea42a40685967d519dc58bec22747464dbc3c6/src/Oracle.sol)


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

