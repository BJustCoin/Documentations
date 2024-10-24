# Vesting
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/a2ea42a40685967d519dc58bec22747464dbc3c6/src/IVestingToken.sol)


```solidity
struct Vesting {
    uint256 startTime;
    uint256 cliff;
    uint8 initialUnlock;
    Schedule[] schedule;
}
```

