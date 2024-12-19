---
sidebar_label: "付款"
sidebar_position: 6
---

# Class: Payments

## Table of contents

### Constructors

- [constructor](Payments#constructor)

### Properties

- [INTERFACE](Payments#interface)

### Methods

- [encodeFeeBips](Payments#encodefeebips)
- [encodeRefundETH](Payments#encoderefundeth)
- [encodeSweepToken](Payments#encodesweeptoken)
- [encodeUnwrapWETH9](Payments#encodeunwrapweth9)

## Constructors

### constructor

• `Private` **new Payments**()

Cannot be constructed.

#### Defined in

[payments.ts:25](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/payments.ts#L25)

## Properties

### INTERFACE

▪ `Static` **INTERFACE**: `Interface`

#### Defined in

[payments.ts:20](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/payments.ts#L20)

## Methods

### encodeFeeBips

▸ `Static` `Private` **encodeFeeBips**(`fee`): `string`

#### Parameters

| Name  | Type      |
| :---- | :-------- |
| `fee` | `Percent` |

#### Returns

`string`

#### Defined in

[payments.ts:27](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/payments.ts#L27)

---

### encodeRefundETH

▸ `Static` **encodeRefundETH**(): `string`

#### Returns

`string`

#### Defined in

[payments.ts:73](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/payments.ts#L73)

---

### encodeSweepToken

▸ `Static` **encodeSweepToken**(`token`, `amountMinimum`, `recipient`, `feeOptions?`): `string`

#### Parameters

| Name            | Type                                     |
| :-------------- | :--------------------------------------- |
| `token`         | `Token`                                  |
| `amountMinimum` | `default`                                |
| `recipient`     | `string`                                 |
| `feeOptions?`   | [`FeeOptions`](../interfaces/FeeOptions) |

#### Returns

`string`

#### Defined in

[payments.ts:49](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/payments.ts#L49)

---

### encodeUnwrapWETH9

▸ `Static` **encodeUnwrapWETH9**(`amountMinimum`, `recipient`, `feeOptions?`): `string`

#### Parameters

| Name            | Type                                     |
| :-------------- | :--------------------------------------- |
| `amountMinimum` | `default`                                |
| `recipient`     | `string`                                 |
| `feeOptions?`   | [`FeeOptions`](../interfaces/FeeOptions) |

#### Returns

`string`

#### Defined in

[payments.ts:31](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/payments.ts#L31)
