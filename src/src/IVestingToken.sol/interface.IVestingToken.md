# IVestingToken
[Git Source](https://github.com/BJustCoin-creator/BJC/blob/afa8ae44b1c3660a047e437225fc640502d221b6/src/IVestingToken.sol)

**Author:**
.

.

*.*


## Functions
### initialize


```solidity
function initialize(string calldata name, string calldata symbol, address minter, address token) external;
```

### setVestingSchedule

.

*.*


```solidity
function setVestingSchedule(uint256 startTime, uint256 cliff, uint8 initialUnlock, Schedule[] calldata schedule)
    external;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`startTime`|`uint256`| .|
|`cliff`|`uint256`| .|
|`initialUnlock`|`uint8`| .|
|`schedule`|`Schedule[]`| .|


### mint

.

*.*


```solidity
function mint(address to, uint256 amount) external;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`to`|`address`| .|
|`amount`|`uint256`| .|


### getVestingSchedule

.

*.*


```solidity
function getVestingSchedule() external view returns (Vesting memory);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`Vesting`|Vesting  .|

