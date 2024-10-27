# VestingToken
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/flatten/VestingToken_flatten.sol)

**Inherits:**
[IVestingToken](/src/flatten/ICOManager_flatten.sol/interface.IVestingToken.md), [Initializable](/src/flatten/ICOManager_flatten.sol/abstract.Initializable.md), [ERC20Upgradeable](/src/flatten/ICOManager_flatten.sol/abstract.ERC20Upgradeable.md)

Отвечает за логику блокировки/разблокировки средств

*Код предоставлен исключительно в ознакомительных целях и не протестирован
Из контракта убрано все лишнее, включая некоторые проверки, геттеры/сеттеры и события*


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

Так как это прокси, нужно выполнить инициализацию

*Создается и инициализируется только контрактом VestingManager*


```solidity
function initialize(string calldata _name, string calldata _symbol, address minter, address baseToken)
    public
    initializer;
```

### getMinter


```solidity
function getMinter() public view returns (address);
```

### setVestingSchedule

Установка расписания также выполняется контрактом VestingManager

*Здесь важно проверить что расписание было передано корректное*


```solidity
function setVestingSchedule(uint256 startTime, uint256 cliff, uint8 initialUnlock, Schedule[] calldata schedule)
    external
    onlyVestingManager;
```

### _checkVestingSchedule


```solidity
function _checkVestingSchedule(uint256 startTime, uint256 cliff, Schedule[] calldata schedule, uint256 scheduleLength)
    private
    view;
```

### mint

Списываем токен который будем блокировать и минтим share-токен


```solidity
function mint(address to, uint256 amount) external onlyMinter;
```

### claim

Сжигаем share-токен и переводим бенефициару разблокированные базовые токены


```solidity
function claim() external;
```

### getVestingSchedule


```solidity
function getVestingSchedule() public view returns (Vesting memory);
```

### unlockedSupply


```solidity
function unlockedSupply() external view returns (uint256);
```

### lockedSupply


```solidity
function lockedSupply() external view returns (uint256);
```

### availableBalanceOf


```solidity
function availableBalanceOf(address account) public view returns (uint256 releasable);
```

### _unlockedOf


```solidity
function _unlockedOf(address account) private view returns (uint256);
```

### _totalUnlocked


```solidity
function _totalUnlocked() private view returns (uint256);
```

### _computeUnlocked

Основная функция для расчета разблокированных токенов

*Проверяется сколько прошло полных периодов и сколько времени прошло
после последнего полного периода.*


```solidity
function _computeUnlocked(uint256 lockedTokens, uint256 time) private view returns (uint256 unlockedTokens);
```

### _update

Трансферить токены нельзя, только минтить и сжигать


```solidity
function _update(address from, address to, uint256 amount) internal virtual override;
```

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

