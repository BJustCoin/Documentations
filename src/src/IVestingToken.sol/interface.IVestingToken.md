# IVestingToken
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/IVestingToken.sol)


## Functions
### initialize


```solidity
function initialize(string calldata name, string calldata symbol, address minter, address token) external;
```

### setVestingSchedule


```solidity
function setVestingSchedule(uint256 startTime, uint256 cliff, uint8 initialUnlock, Schedule[] calldata schedule)
    external;
```

### mint


```solidity
function mint(address to, uint256 amount) external;
```

### getVestingSchedule


```solidity
function getVestingSchedule() external view returns (Vesting memory);
```

