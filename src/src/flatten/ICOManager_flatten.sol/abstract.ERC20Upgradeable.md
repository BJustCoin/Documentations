# ERC20Upgradeable
[Git Source](https://github.com/BJustCoin/BJustCoin/blob/e7038856495a90d82d025f98c39648e6605afbeb/src/flatten/ICOManager_flatten.sol)

**Inherits:**
[Initializable](/src/flatten/ICOManager_flatten.sol/abstract.Initializable.md), [ContextUpgradeable](/src/flatten/ICOManager_flatten.sol/abstract.ContextUpgradeable.md), [IERC20](/src/flatten/ICOManager_flatten.sol/interface.IERC20.md), [IERC20Metadata](/src/flatten/ICOManager_flatten.sol/interface.IERC20Metadata.md), [IERC20Errors](/src/flatten/ICOManager_flatten.sol/interface.IERC20Errors.md)

*Implementation of the {IERC20} interface.
This implementation is agnostic to the way tokens are created. This means
that a supply mechanism has to be added in a derived contract using {_mint}.
TIP: For a detailed writeup see our guide
https://forum.openzeppelin.com/t/how-to-implement-erc20-supply-mechanisms/226[How
to implement supply mechanisms].
The default value of {decimals} is 18. To change this, you should override
this function so it returns a different value.
We have followed general OpenZeppelin Contracts guidelines: functions revert
instead returning `false` on failure. This behavior is nonetheless
conventional and does not conflict with the expectations of ERC20
applications.
Additionally, an {Approval} event is emitted on calls to {transferFrom}.
This allows applications to reconstruct the allowance for all accounts just
by listening to said events. Other implementations of the EIP may not emit
these events, as it isn't required by the specification.*


## State Variables
### ERC20StorageLocation

```solidity
bytes32 private constant ERC20StorageLocation = 0x52c63247e1f47db19d5ce0460030c497f067ca4cebf71ba98eeadabe20bace00;
```


## Functions
### _getERC20Storage


```solidity
function _getERC20Storage() private pure returns (ERC20Storage storage $);
```

### __ERC20_init

*Sets the values for [name](/src/flatten/ICOManager_flatten.sol/abstract.ERC20Upgradeable.md#name) and {symbol}.
All two of these values are immutable: they can only be set once during
construction.*


```solidity
function __ERC20_init(string memory name_, string memory symbol_) internal onlyInitializing;
```

### __ERC20_init_unchained


```solidity
function __ERC20_init_unchained(string memory name_, string memory symbol_) internal onlyInitializing;
```

### name

*Returns the name of the token.*


```solidity
function name() public view virtual returns (string memory);
```

### symbol

*Returns the symbol of the token, usually a shorter version of the
name.*


```solidity
function symbol() public view virtual returns (string memory);
```

### decimals

*Returns the number of decimals used to get its user representation.
For example, if `decimals` equals `2`, a balance of `505` tokens should
be displayed to a user as `5.05` (`505 / 10 ** 2`).
Tokens usually opt for a value of 18, imitating the relationship between
Ether and Wei. This is the default value returned by this function, unless
it's overridden.
NOTE: This information is only used for _display_ purposes: it in
no way affects any of the arithmetic of the contract, including
[IERC20-balanceOf](/src/flatten/VestingToken_flatten.sol/interface.IERC20.md#balanceof) and {IERC20-transfer}.*


```solidity
function decimals() public view virtual returns (uint8);
```

### totalSupply

*See [IERC20-totalSupply](/src/flatten/VestingToken_flatten.sol/interface.IERC20.md#totalsupply).*


```solidity
function totalSupply() public view virtual returns (uint256);
```

### balanceOf

*See [IERC20-balanceOf](/src/flatten/VestingToken_flatten.sol/interface.IERC20.md#balanceof).*


```solidity
function balanceOf(address account) public view virtual returns (uint256);
```

### transfer

*See [IERC20-transfer](/src/flatten/VestingToken_flatten.sol/interface.IERC20.md#transfer).
Requirements:
- `to` cannot be the zero address.
- the caller must have a balance of at least `value`.*


```solidity
function transfer(address to, uint256 value) public virtual returns (bool);
```

### allowance

*See [IERC20-allowance](/src/flatten/VestingToken_flatten.sol/interface.IERC20.md#allowance).*


```solidity
function allowance(address owner, address spender) public view virtual returns (uint256);
```

### approve

*See [IERC20-approve](/src/flatten/VestingToken_flatten.sol/interface.IERC20.md#approve).
NOTE: If `value` is the maximum `uint256`, the allowance is not updated on
`transferFrom`. This is semantically equivalent to an infinite approval.
Requirements:
- `spender` cannot be the zero address.*


```solidity
function approve(address spender, uint256 value) public virtual returns (bool);
```

### transferFrom

*See [IERC20-transferFrom](/src/flatten/VestingToken_flatten.sol/interface.IERC20.md#transferfrom).
Emits an {Approval} event indicating the updated allowance. This is not
required by the EIP. See the note at the beginning of {ERC20}.
NOTE: Does not update the allowance if the current allowance
is the maximum `uint256`.
Requirements:
- `from` and `to` cannot be the zero address.
- `from` must have a balance of at least `value`.
- the caller must have allowance for ``from``'s tokens of at least
`value`.*


```solidity
function transferFrom(address from, address to, uint256 value) public virtual returns (bool);
```

### _transfer

*Moves a `value` amount of tokens from `from` to `to`.
This internal function is equivalent to [transfer](/src/flatten/ICOManager_flatten.sol/abstract.ERC20Upgradeable.md#transfer), and can be used to
e.g. implement automatic token fees, slashing mechanisms, etc.
Emits a {Transfer} event.
NOTE: This function is not virtual, {_update} should be overridden instead.*


```solidity
function _transfer(address from, address to, uint256 value) internal;
```

### _update

*Transfers a `value` amount of tokens from `from` to `to`, or alternatively mints (or burns) if `from`
(or `to`) is the zero address. All customizations to transfers, mints, and burns should be done by overriding
this function.
Emits a {Transfer} event.*


```solidity
function _update(address from, address to, uint256 value) internal virtual;
```

### _mint

*Creates a `value` amount of tokens and assigns them to `account`, by transferring it from address(0).
Relies on the `_update` mechanism
Emits a {Transfer} event with `from` set to the zero address.
NOTE: This function is not virtual, {_update} should be overridden instead.*


```solidity
function _mint(address account, uint256 value) internal;
```

### _burn

*Destroys a `value` amount of tokens from `account`, lowering the total supply.
Relies on the `_update` mechanism.
Emits a {Transfer} event with `to` set to the zero address.
NOTE: This function is not virtual, {_update} should be overridden instead*


```solidity
function _burn(address account, uint256 value) internal;
```

### _approve

*Sets `value` as the allowance of `spender` over the `owner` s tokens.
This internal function is equivalent to `approve`, and can be used to
e.g. set automatic allowances for certain subsystems, etc.
Emits an {Approval} event.
Requirements:
- `owner` cannot be the zero address.
- `spender` cannot be the zero address.
Overrides to this logic should be done to the variant with an additional `bool emitEvent` argument.*


```solidity
function _approve(address owner, address spender, uint256 value) internal;
```

### _approve

*Variant of [_approve](/src/flatten/ICOManager_flatten.sol/abstract.ERC20Upgradeable.md#_approve) with an optional flag to enable or disable the {Approval} event.
By default (when calling {_approve}) the flag is set to true. On the other hand, approval changes made by
`_spendAllowance` during the `transferFrom` operation set the flag to false. This saves gas by not emitting any
`Approval` event during `transferFrom` operations.
Anyone who wishes to continue emitting `Approval` events on the`transferFrom` operation can force the flag to
true using the following override:
```
function _approve(address owner, address spender, uint256 value, bool) internal virtual override {
super._approve(owner, spender, value, true);
}
```
Requirements are the same as {_approve}.*


```solidity
function _approve(address owner, address spender, uint256 value, bool emitEvent) internal virtual;
```

### _spendAllowance

*Updates `owner` s allowance for `spender` based on spent `value`.
Does not update the allowance value in case of infinite allowance.
Revert if not enough allowance is available.
Does not emit an {Approval} event.*


```solidity
function _spendAllowance(address owner, address spender, uint256 value) internal virtual;
```

## Structs
### ERC20Storage

```solidity
struct ERC20Storage {
    mapping(address account => uint256) _balances;
    mapping(address account => mapping(address spender => uint256)) _allowances;
    uint256 _totalSupply;
    string _name;
    string _symbol;
}
```

