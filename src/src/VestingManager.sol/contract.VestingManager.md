# VestingManager
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/a2ea42a40685967d519dc58bec22747464dbc3c6/src/VestingManager.sol)

**Inherits:**
Ownable

Основная задача смарт-контракта создавать экземпляры share-токенов
и устанавливать на них расписание вестинга

**


## State Variables
### _vestingImplementation

```solidity
address private immutable _vestingImplementation;
```


## Functions
### constructor


```solidity
constructor(address implementation) Ownable(msg.sender);
```

### createVesting

Основная функция для создания экземпляра share-токена
Т.к. это создание ERC20 - задаем name и symbol
Указываем адрес токена который будет блокироваться под вестинг
Указываем адрес который сможет минтить share-токены (к примеру контракт продаж)
Передаем расписание


```solidity
function createVesting(
    string calldata name,
    string calldata symbol,
    address baseToken,
    address minter,
    Vesting calldata vesting
) external onlyOwner returns (address vestingToken);
```

### _createVestingToken


```solidity
function _createVestingToken(string calldata name, string calldata symbol, address minter, address baseToken)
    private
    returns (address vestingToken);
```

## Events
### CreateVestingToken

```solidity
event CreateVestingToken(address indexed addressToken, string name, string symbol);
```

## Errors
### ImplementationError

```solidity
error ImplementationError();
```

