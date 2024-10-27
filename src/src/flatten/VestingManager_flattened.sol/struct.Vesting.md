# Vesting
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/flatten/VestingManager_flattened.sol)


```solidity
struct Vesting {
    uint256 startTime;
    uint256 cliff;
    uint8 initialUnlock;
    Schedule[] schedule;
}
```

