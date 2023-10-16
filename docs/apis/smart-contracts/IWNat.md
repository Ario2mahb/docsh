---
title: IWNat
---

<!-- This is an autogenerated file. Do not edit! -->

# `IWNat` { #ct_iwnat }

<div class="api-node-source" markdown>
[Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/userInterfaces/IWNat.sol)
</div>

<div class="api-node-internal" markdown>

Wrapped native token interface.

This contract converts native tokens into `WNAT` (wrapped native) tokens and vice versa.
`WNAT` tokens are a one-to-one [ERC20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/)
representation of native tokens, which are minted and burned as needed by this contract.

The wrapped versions of the native `FLR` and `SGB` tokens are called `WFLR` and `WSGB` respectively.

Code attribution: WETH9.

</div>

<div class="api-node-type" markdown>

## Functions

<div class="api-node" markdown>

### `deposit` { #fn_deposit_d0e30db0 }

<div class="api-node-source" markdown>
Defined in `IWNat` ([Docs](./IWNat.md), [Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/userInterfaces/IWNat.sol)).
</div>

<div class="api-node-internal" markdown>

```solidity
function deposit(
) external payable;
```

Deposits native tokens and mints the same amount of `WNAT` tokens,
which are added to the `msg.sender`'s balance.
This operation is commonly known as "wrapping".

</div>
</div>

<div class="api-node" markdown>

### `depositTo` { #fn_depositto_b760faf9 }

<div class="api-node-source" markdown>
Defined in `IWNat` ([Docs](./IWNat.md), [Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/userInterfaces/IWNat.sol)).
</div>

<div class="api-node-internal" markdown>

```solidity
function depositTo(
    address _recipient
) external payable;
```

Deposits native tokens and mints the same amount of `WNAT` tokens,
which are added to `_recipient`'s balance.
This operation is commonly known as "wrapping".

This is equivalent to using [`deposit`](#fn_deposit_d0e30db0) followed by `transfer`.

| Parameters | Type | Description |
| ---------- | ---- | ----------- |
| `_recipient` | `address` | The address to receive the minted `WNAT`. |

</div>
</div>

<div class="api-node" markdown>

### `withdraw` { #fn_withdraw_2e1a7d4d }

<div class="api-node-source" markdown>
Defined in `IWNat` ([Docs](./IWNat.md), [Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/userInterfaces/IWNat.sol)).
</div>

<div class="api-node-internal" markdown>

```solidity
function withdraw(
    uint256 _amount
) external;
```

Burns `_amount` of `WNAT` tokens from `msg.sender`'s `WNAT` balance and
transfers the same amount of native tokens to `msg.sender`.
This operation is commonly known as "unwrapping".

Reverts if `_amount` is higher than `msg.sender`'s `WNAT` balance.

| Parameters | Type | Description |
| ---------- | ---- | ----------- |
| `_amount` | `uint256` | The amount to withdraw. |

</div>
</div>

<div class="api-node" markdown>

### `withdrawFrom` { #fn_withdrawfrom_9470b0bd }

<div class="api-node-source" markdown>
Defined in `IWNat` ([Docs](./IWNat.md), [Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/userInterfaces/IWNat.sol)).
</div>

<div class="api-node-internal" markdown>

```solidity
function withdrawFrom(
    address _owner,
    uint256 _amount
) external;
```

Burns `_amount` of `WNAT` tokens from `_owner`'s `WNAT` balance and
transfers the same amount of native tokens to `msg.sender`.
This operation is commonly known as "unwrapping".

`msg.sender` must have been authorized to [`withdraw`](#fn_withdraw_2e1a7d4d) from `_owner`'s account
through ERC-20's approve mechanism.

Reverts if `_amount` is higher than `_owners`'s `WNAT` balance or than
`msg.sender`'s allowance over `_owner`'s tokens.

| Parameters | Type | Description |
| ---------- | ---- | ----------- |
| `_owner` | `address` | The address containing the tokens to withdraw. |
| `_amount` | `uint256` | The amount to withdraw. |

</div>
</div>

</div>
