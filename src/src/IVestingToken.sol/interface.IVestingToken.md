# IVestingToken
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/a2ea42a40685967d519dc58bec22747464dbc3c6/src/IVestingToken.sol)

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


