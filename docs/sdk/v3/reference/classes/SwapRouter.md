---
sidebar_label: "交换路由器"
sidebar_position: 16
---

# Class: SwapRouter

Represents the SwapX V3 SwapRouter, and has static methods for helping execute trades.

## Table of contents

### Constructors

- [constructor](SwapRouter#constructor)

### Properties

- [INTERFACE](SwapRouter#interface)

### Methods

- [swapCallParameters](SwapRouter#swapcallparameters)

## Constructors

### constructor

`Private` **new SwapRouter**()

Cannot be constructed.

#### Defined in

[swapRouter.ts:57](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L57)

## Properties

### INTERFACE

`Static` **INTERFACE**: `Interface`

#### Defined in

[swapRouter.ts:52](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L52)

## Methods

### swapCallParameters

`Static` **swapCallParameters**(`trades`, `options`): [`MethodParameters`](../interfaces/MethodParameters)

Produces the on-chain method name to call and the hex encoded parameters to pass as arguments for a given trade.

#### Parameters

| Name      | Type                                                                                                           | Description                     |
| :-------- | :------------------------------------------------------------------------------------------------------------- | :------------------------------ |
| `trades`  | [`Trade`](Trade) `Currency`, `Currency`, `TradeType` \| [`Trade`](Trade) `Currency`, `Currency`, `TradeType`[] | -                               |
| `options` | [`SwapOptions`](../interfaces/SwapOptions)                                                                     | options for the call parameters |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

#### Defined in

[swapRouter.ts:64](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L64)
