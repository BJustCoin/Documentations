# ICOManager
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/a2ea42a40685967d519dc58bec22747464dbc3c6/src/ICOManager.sol)

**Inherits:**
Ownable

**Author:**
Code Tesla Labs

Implements ICO mechanisms

*Implements ICO mechanisms*


## State Variables
### BASIS_TOKENS_FOR_VESTING_TOKENS

```solidity
uint256 private constant BASIS_TOKENS_FOR_VESTING_TOKENS = 5040;
```


### MONTH

```solidity
uint256 private constant MONTH = 365 days / 12;
```


### DEFAULT_RATE

```solidity
uint256 private constant DEFAULT_RATE = 257673;
```


### MIN_SOLD_VOLUME

```solidity
uint256 private constant MIN_SOLD_VOLUME = 1000;
```


### _oracle

```solidity
Oracle internal immutable _oracle;
```


### _vestingTokenImpl

```solidity
VestingToken internal immutable _vestingTokenImpl;
```


### _vestingManager

```solidity
VestingManager internal immutable _vestingManager;
```


### _baseToken

```solidity
Bjustcoin internal immutable _baseToken;
```


### icoStage

```solidity
ICOStage private icoStage;
```


### blacklists

```solidity
mapping(address => bool) public blacklists;
```


### tokenomicSettings

```solidity
mapping(TokenomicType => TokenomicSetting) private tokenomicSettings;
```


## Functions
### notInBlackList

we check whether the address is included in the blocked list

*we check whether the address is included in the blocked list*


```solidity
modifier notInBlackList(address to);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`to`|`address`| the address being checked|


### constructor


```solidity
constructor() Ownable(msg.sender);
```

### buyICOToken

purchase of an ICO stage token

*purchase stage token. The type of token depends on the ICO stage*


```solidity
function buyICOToken() external payable notInBlackList(msg.sender);
```

### buyAdvisorsToken

purchase of a Advisors token

*purchase of a Advisors token*


```solidity
function buyAdvisorsToken() external payable notInBlackList(msg.sender);
```

### buyTeamToken

purchase of a Team token

*purchase of a Team token*


```solidity
function buyTeamToken() external payable notInBlackList(msg.sender);
```

### buyFutureTeamToken

purchase of a Future Team token

*purchase of a Future Team token*


```solidity
function buyFutureTeamToken() external payable notInBlackList(msg.sender);
```

### buyIncentivesToken

purchase of a Incentives token

*purchase of a Incentives token*


```solidity
function buyIncentivesToken() external payable notInBlackList(msg.sender);
```

### buyLiquidityToken

purchase of a Liquidity token

*purchase of a Liquidity token*


```solidity
function buyLiquidityToken() external payable notInBlackList(msg.sender);
```

### buyEcosystemToken

purchase of a Ecosystem token

*purchase of a Ecosystem token*


```solidity
function buyEcosystemToken() external payable notInBlackList(msg.sender);
```

### buyLoyaltyToken

purchase of a Loyalty token

*purchase of a Loyalty token*


```solidity
function buyLoyaltyToken() external payable notInBlackList(msg.sender);
```

### withdraw

withdraw eth from the contract

*withdraw eth from the contract*


```solidity
function withdraw() external payable onlyOwner;
```

### blacklist

Adding or removing an address to the blacklist

*Adding or removing an address to the blacklist*


```solidity
function blacklist(address _address, bool _isBlacklisting) external payable onlyOwner;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`_address`|`address`| Address additing or removing to the blacklist|
|`_isBlacklisting`|`bool`| true - add; false - remov;|


### nextICOStage

Moving the ICO to the next stage

*Moving the ICO to the next stage*


```solidity
function nextICOStage() external payable onlyOwner;
```

### getBaseToken

get a Bjustcoin

*get a basic token*


```solidity
function getBaseToken() public view returns (Bjustcoin);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`Bjustcoin`|Bjustcoin  basic token|


### getICOStage

get ICO stage

*get ICO stage*


```solidity
function getICOStage() public view returns (ICOStage);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`ICOStage`|ICOStage  stage|


### strategicToken

get stategic token

*get stategic token*


```solidity
function strategicToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### seedToken

get seed token

*get seed token*


```solidity
function seedToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### privateSaleToken

get private sale token

*get private sale token*


```solidity
function privateSaleToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### idoToken

get IDO token

*get IDO token*


```solidity
function idoToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### publicSaleToken

get public sale token

*get public sale token*


```solidity
function publicSaleToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### advisorsToken

get advisors token

*get advisors token*


```solidity
function advisorsToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### teamToken

get teem token

*get teem token*


```solidity
function teamToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### futureTeamToken

get future team token

*get future team token*


```solidity
function futureTeamToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### incentivesToken

get incentives token

*get incentives token*


```solidity
function incentivesToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### liquidityToken

get liquidity token

*get liquidity token*


```solidity
function liquidityToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### ecosystemToken

get ecosystem token

*get ecosystem token*


```solidity
function ecosystemToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### loyaltyToken

get loyalty token

*get loyalty token*


```solidity
function loyaltyToken() public view returns (VestingToken);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`VestingToken`|VestingToken|


### getTokenomicType

get tokenomic type for ICO stage

*get tokenomic type for ICO stage*


```solidity
function getTokenomicType() public view returns (TokenomicType);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`TokenomicType`|TokenomicType|


### getRate

get rate eth/usd

*get rate eth/usd from oracle*


```solidity
function getRate() public view returns (uint256 rate);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`rate`|`uint256`| .|


### getTokenomicType

get tokenomic type

*get tokenomic type*


```solidity
function getTokenomicType(ICOStage _icoStage) private pure returns (TokenomicType);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`_icoStage`|`ICOStage`| ICO stage|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`TokenomicType`|TokenomicType|


### initTokenomics

Initial tokenomics params

*Initial tokenomics params*


```solidity
function initTokenomics() private;
```

### initVestingToken

Initial tokenomic vesting data

*Initial tokenomic vesting data*


```solidity
function initVestingToken(TokenomicSetting storage _settings) private;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`_settings`|`TokenomicSetting`| Settings tokenomic|


### buyToken

buy token

*buy token*


```solidity
function buyToken(TokenomicSetting storage settings) private;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`settings`|`TokenomicSetting`| setting tokens for purchase|


### buyStrategicToken

purchase strategic token

*purchase strategic token*


```solidity
function buyStrategicToken() private;
```

### buySeedToken

purchase seed token

*purchase seed token*


```solidity
function buySeedToken() private;
```

### buyPrivateSaleToken

purchase private sale token

*purchase private sale token*


```solidity
function buyPrivateSaleToken() private;
```

### buyIDOToken

purchase IDO token

*purchase IDO token*


```solidity
function buyIDOToken() private;
```

### buyPublicSaleToken

purchase public sale token

*purchase public sale token*


```solidity
function buyPublicSaleToken() private;
```

## Events
### ICOStageChanged

```solidity
event ICOStageChanged(address indexed from, ICOStage initialStage, ICOStage newStage);
```

### BuyToken

```solidity
event BuyToken(address indexed from, address indexed to, string tokenSimvol, uint256 tokenCount, uint256 rate);
```

## Errors
### Blacklisted

```solidity
error Blacklisted();
```

### ICONotStarted

```solidity
error ICONotStarted();
```

### ICOCompleted

```solidity
error ICOCompleted();
```

### TokenAlreadyExist

```solidity
error TokenAlreadyExist();
```

### MinSoldError

```solidity
error MinSoldError();
```

### InsufficientFunds

```solidity
error InsufficientFunds();
```

### WithdrawError

```solidity
error WithdrawError();
```

### NotApprove

```solidity
error NotApprove();
```

