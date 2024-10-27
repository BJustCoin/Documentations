# ContextUpgradeable
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/flatten/ICOManager_flatten.sol)

**Inherits:**
[Initializable](/src/flatten/ICOManager_flatten.sol/abstract.Initializable.md)

*Provides information about the current execution context, including the
sender of the transaction and its data. While these are generally available
via msg.sender and msg.data, they should not be accessed in such a direct
manner, since when dealing with meta-transactions the account sending and
paying for execution may not be the actual sender (as far as an application
is concerned).
This contract is only required for intermediate, library-like contracts.*


## Functions
### __Context_init


```solidity
function __Context_init() internal onlyInitializing;
```

### __Context_init_unchained


```solidity
function __Context_init_unchained() internal onlyInitializing;
```

### _msgSender


```solidity
function _msgSender() internal view virtual returns (address);
```

### _msgData


```solidity
function _msgData() internal view virtual returns (bytes calldata);
```

### _contextSuffixLength


```solidity
function _contextSuffixLength() internal view virtual returns (uint256);
```

