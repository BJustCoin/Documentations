# SafeERC20
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/flatten/ICOManager_flatten.sol)

*Wrappers around ERC20 operations that throw on failure (when the token
contract returns false). Tokens that return no value (and instead revert or
throw on failure) are also supported, non-reverting calls are assumed to be
successful.
To use this library you can add a `using SafeERC20 for IERC20;` statement to your contract,
which allows you to call the safe operations as `token.safeTransfer(...)`, etc.*


## Functions
### safeTransfer

*Transfer `value` amount of `token` from the calling contract to `to`. If `token` returns no value,
non-reverting calls are assumed to be successful.*


```solidity
function safeTransfer(IERC20 token, address to, uint256 value) internal;
```

### safeTransferFrom

*Transfer `value` amount of `token` from `from` to `to`, spending the approval given by `from` to the
calling contract. If `token` returns no value, non-reverting calls are assumed to be successful.*


```solidity
function safeTransferFrom(IERC20 token, address from, address to, uint256 value) internal;
```

### safeIncreaseAllowance

*Increase the calling contract's allowance toward `spender` by `value`. If `token` returns no value,
non-reverting calls are assumed to be successful.*


```solidity
function safeIncreaseAllowance(IERC20 token, address spender, uint256 value) internal;
```

### safeDecreaseAllowance

*Decrease the calling contract's allowance toward `spender` by `requestedDecrease`. If `token` returns no
value, non-reverting calls are assumed to be successful.*


```solidity
function safeDecreaseAllowance(IERC20 token, address spender, uint256 requestedDecrease) internal;
```

### forceApprove

*Set the calling contract's allowance toward `spender` to `value`. If `token` returns no value,
non-reverting calls are assumed to be successful. Meant to be used with tokens that require the approval
to be set to zero before setting it to a non-zero value, such as USDT.*


```solidity
function forceApprove(IERC20 token, address spender, uint256 value) internal;
```

### _callOptionalReturn

*Imitates a Solidity high-level call (i.e. a regular function call to a contract), relaxing the requirement
on the return value: the return value is optional (but if data is returned, it must not be false).*


```solidity
function _callOptionalReturn(IERC20 token, bytes memory data) private;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`token`|`IERC20`|The token targeted by the call.|
|`data`|`bytes`|The call data (encoded using abi.encode or one of its variants).|


### _callOptionalReturnBool

*Imitates a Solidity high-level call (i.e. a regular function call to a contract), relaxing the requirement
on the return value: the return value is optional (but if data is returned, it must not be false).*


```solidity
function _callOptionalReturnBool(IERC20 token, bytes memory data) private returns (bool);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`token`|`IERC20`|The token targeted by the call.|
|`data`|`bytes`|The call data (encoded using abi.encode or one of its variants). This is a variant of [_callOptionalReturn](/src/flatten/ICOManager_flatten.sol/library.SafeERC20.md#_calloptionalreturn) that silents catches all reverts and returns a bool instead.|


## Errors
### SafeERC20FailedOperation
*An operation with an ERC20 token failed.*


```solidity
error SafeERC20FailedOperation(address token);
```

### SafeERC20FailedDecreaseAllowance
*Indicates a failed `decreaseAllowance` request.*


```solidity
error SafeERC20FailedDecreaseAllowance(address spender, uint256 currentAllowance, uint256 requestedDecrease);
```

