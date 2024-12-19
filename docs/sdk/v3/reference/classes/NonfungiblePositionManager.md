---
sidebar_label: "非同质化仓位经理"
sidebar_position: 4
---

# Class: NonfungiblePositionManager

## Table of contents

### Constructors

- [constructor](NonfungiblePositionManager#constructor)

### Properties

- [INTERFACE](NonfungiblePositionManager#interface)

### Methods

- [addCallParameters](NonfungiblePositionManager#addcallparameters)
- [collectCallParameters](NonfungiblePositionManager#collectcallparameters)
- [createCallParameters](NonfungiblePositionManager#createcallparameters)
- [encodeCollect](NonfungiblePositionManager#encodecollect)
- [encodeCreate](NonfungiblePositionManager#encodecreate)
- [removeCallParameters](NonfungiblePositionManager#removecallparameters)
- [safeTransferFromParameters](NonfungiblePositionManager#safetransferfromparameters)

## Constructors

### constructor

• `Private` **new NonfungiblePositionManager**()

Cannot be constructed.

#### Defined in

[nonfungiblePositionManager.ts:181](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L181)

## Properties

### INTERFACE

▪ `Static` **INTERFACE**: `Interface`

#### Defined in

[nonfungiblePositionManager.ts:176](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L176)

## Methods

### addCallParameters

▸ `Static` **addCallParameters**(`position`, `options`): [`MethodParameters`](../interfaces/MethodParameters)

#### Parameters

| Name       | Type                                                    |
| :--------- | :------------------------------------------------------ |
| `position` | [`Position`](Position)                                  |
| `options`  | [`AddLiquidityOptions`](../modules#addliquidityoptions) |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

#### Defined in

[nonfungiblePositionManager.ts:199](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L199)

---

### collectCallParameters

▸ `Static` **collectCallParameters**(`options`): [`MethodParameters`](../interfaces/MethodParameters)

#### Parameters

| Name      | Type                                             |
| :-------- | :----------------------------------------------- |
| `options` | [`CollectOptions`](../interfaces/CollectOptions) |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

#### Defined in

[nonfungiblePositionManager.ts:326](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L326)

---

### createCallParameters

▸ `Static` **createCallParameters**(`pool`): [`MethodParameters`](../interfaces/MethodParameters)

#### Parameters

| Name   | Type           |
| :----- | :------------- |
| `pool` | [`Pool`](Pool) |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

#### Defined in

[nonfungiblePositionManager.ts:192](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L192)

---

### encodeCollect

▸ `Static` `Private` **encodeCollect**(`options`): `string`[]

#### Parameters

| Name      | Type                                             |
| :-------- | :----------------------------------------------- |
| `options` | [`CollectOptions`](../interfaces/CollectOptions) |

#### Returns

`string`[]

#### Defined in

[nonfungiblePositionManager.ts:286](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L286)

---

### encodeCreate

▸ `Static` `Private` **encodeCreate**(`pool`): `string`

#### Parameters

| Name   | Type           |
| :----- | :------------- |
| `pool` | [`Pool`](Pool) |

#### Returns

`string`

#### Defined in

[nonfungiblePositionManager.ts:183](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L183)

---

### removeCallParameters

▸ `Static` **removeCallParameters**(`position`, `options`): [`MethodParameters`](../interfaces/MethodParameters)

Produces the calldata for completely or partially exiting a position

#### Parameters

| Name       | Type                                                             | Description                                                  |
| :--------- | :--------------------------------------------------------------- | :----------------------------------------------------------- |
| `position` | [`Position`](Position)                                           | The position to exit                                         |
| `options`  | [`RemoveLiquidityOptions`](../interfaces/RemoveLiquidityOptions) | Additional information necessary for generating the calldata |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

The call parameters

#### Defined in

[nonfungiblePositionManager.ts:341](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L341)

---

### safeTransferFromParameters

▸ `Static` **safeTransferFromParameters**(`options`): [`MethodParameters`](../interfaces/MethodParameters)

#### Parameters

| Name      | Type                                                       |
| :-------- | :--------------------------------------------------------- |
| `options` | [`SafeTransferOptions`](../interfaces/SafeTransferOptions) |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

#### Defined in

[nonfungiblePositionManager.ts:416](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L416)
