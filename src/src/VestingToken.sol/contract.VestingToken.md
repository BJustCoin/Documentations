# VestingToken
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/VestingToken.sol)

**Inherits:**
[IVestingToken](/src/flatten/ICOManager_flatten.sol/interface.IVestingToken.md), [Initializable](/src/flatten/ICOManager_flatten.sol/abstract.Initializable.md), [ERC20Upgradeable](/src/flatten/ICOManager_flatten.sol/abstract.ERC20Upgradeable.md)

Responsible for the logic of blocking/unblocking funds


## State Variables
### basisPoints

```solidity
uint256 public immutable basisPoints;
```


### _minter

```solidity
address private _minter;
```


### _vestingManager

```solidity
address private _vestingManager;
```


### _baseToken

```solidity
IERC20 private _baseToken;
```


### _vesting

```solidity
Vesting private _vesting;
```


### _initialLockedSupply

```solidity
uint256 private _initialLockedSupply;
```


### _initialLocked

```solidity
mapping(address => uint256) private _initialLocked;
```


### _released

```solidity
mapping(address => uint256) private _released;
```


## Functions
### constructor


```solidity
constructor(uint256 _basisPoints);
```

### onlyMinter


```solidity
modifier onlyMinter();
```

### onlyVestingManager


```solidity
modifier onlyVestingManager();
```

### initialize

initialization

*It is created and initialized only by the VestingManager contract*


```solidity
function initialize(string calldata _name, string calldata _symbol, address minter, address baseToken)
    public
    initializer;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`_name`|`string`| name vesting token|
|`_symbol`|`string`| symbol vesting token|
|`minter`|`address`| address the address that owns the right to mint tokens|
|`baseToken`|`address`| address base token.|


### getMinter


```solidity
function getMinter() public view returns (address);
```

### setVestingSchedule

The schedule is set by the VestingManager contract

*The schedule is set by the VestingManager contract*


```solidity
function setVestingSchedule(uint256 startTime, uint256 cliff, uint8 initialUnlock, Schedule[] calldata schedule)
    external
    onlyVestingManager;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`startTime`|`uint256`| start time|
|`cliff`|`uint256`| cliff time|
|`initialUnlock`|`uint8`| unlocked tokens after cliff time|
|`schedule`|`Schedule[]`| task scheduler|


### _checkVestingSchedule

*check vesting tasck schedule*


```solidity
function _checkVestingSchedule(uint256 startTime, uint256 cliff, Schedule[] calldata schedule, uint256 scheduleLength)
    private
    view;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`startTime`|`uint256`| start time|
|`cliff`|`uint256`| cliff time|
|`schedule`|`Schedule[]`| task shedule|
|`scheduleLength`|`uint256`| shedule lenght|


### mint

we are writing off base token and mint vestingToken

*we are writing off base token and mint vestingToken*


```solidity
function mint(address to, uint256 amount) external onlyMinter;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`to`|`address`| address to|
|`amount`|`uint256`| count token|


### claim

Burt vestingTokens and transfer the unlocked basic tokens to the beneficiary

*Burt vestingTokens and transfer the unlocked basic tokens to the beneficiary*


```solidity
function claim() external;
```

### getVestingSchedule

get vesting structure

*get vesting structure*


```solidity
function getVestingSchedule() public view returns (Vesting memory);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`Vesting`|Vesting  structure|


### unlockedSupply

number of unlocked tokens

*number of unlocked tokens*


```solidity
function unlockedSupply() external view returns (uint256);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`uint256`|uint256  count tokens|


### lockedSupply

number of locked tokens

*number of locked tokens*


```solidity
function lockedSupply() external view returns (uint256);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`uint256`|uint256  count tokens|


### availableBalanceOf

the wallet balance available for withdrawal

*the wallet balance available for withdrawal*


```solidity
function availableBalanceOf(address account) public view returns (uint256 releasable);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`account`|`address`| wallet address|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`releasable`|`uint256`| count tokens|


### _unlockedOf

*determining the number of unlocked tokens*


```solidity
function _unlockedOf(address account) private view returns (uint256);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`account`|`address`| wallet address|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`uint256`|uint256  count tokens|


### _totalUnlocked

*all unlocked tokens*


```solidity
function _totalUnlocked() private view returns (uint256);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`uint256`|uint256  count tokens|


### _computeUnlocked

The main function for calculating unlocked tokens

*It checks how many full periods have passed and how much time has passed since the last full period.*


```solidity
function _computeUnlocked(uint256 lockedTokens, uint256 time) private view returns (uint256 unlockedTokens);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`lockedTokens`|`uint256`| locked tokens|
|`time`|`uint256`| time elapsed since the beginning of the vesting|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`unlockedTokens`|`uint256`| unlocked tokens|


### _update

Available only mint and claim

*Available only mint and claim*


```solidity
function _update(address from, address to, uint256 amount) internal virtual override;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`from`|`address`| address from|
|`to`|`address`| addres to|
|`amount`|`uint256`| count tokens|


## Events
### MintTokens

```solidity
event MintTokens(address indexed token, address indexed to, uint256 tokenCount);
```

## Errors
### OnlyMinter

```solidity
error OnlyMinter();
```

### MinterNotSet

```solidity
error MinterNotSet();
```

### OnlyVestingManager

```solidity
error OnlyVestingManager();
```

### NotEnoughTokensToClaim

```solidity
error NotEnoughTokensToClaim();
```

### StartTimeAlreadyElapsed

```solidity
error StartTimeAlreadyElapsed();
```

### CliffBeforeStartTime

```solidity
error CliffBeforeStartTime();
```

### IncorrectSchedulePortions

```solidity
error IncorrectSchedulePortions();
```

### IncorrectScheduleTime

```solidity
error IncorrectScheduleTime(uint256 incorrectTime);
```

### TransfersNotAllowed

```solidity
error TransfersNotAllowed();
```

### MintingAfterCliffIsForbidden

```solidity
error MintingAfterCliffIsForbidden();
```

### PercentError

```solidity
error PercentError();
```

