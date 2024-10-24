# Vesting
[Git Source](https://github.com/BJustCoin-creator/BJC/blob/afa8ae44b1c3660a047e437225fc640502d221b6/src/IVestingToken.sol)


```solidity
struct Vesting {
    uint256 startTime;
    uint256 cliff;
    uint8 initialUnlock;
    Schedule[] schedule;
}
```

