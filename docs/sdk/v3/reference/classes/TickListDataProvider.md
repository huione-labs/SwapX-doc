---
sidebar_label: "勾选数据提供者"
sidebar_position: 20
---

# Class: TickListDataProvider

A data provider for ticks that is backed by an in-memory array of ticks.

## Implements

- [`TickDataProvider`](interfaces/TickDataProvider)

## Table of contents

### Constructors

- [constructor](TickListDataProvider#constructor)

### Properties

- [ticks](TickListDataProvider#ticks)

### Methods

- [getTick](TickListDataProvider#gettick)
- [nextInitializedTickWithinOneWord](TickListDataProvider#nextinitializedtickwithinoneword)

## Constructors

### constructor

**new TickListDataProvider**(`ticks`, `tickSpacing`)

#### Parameters

| Name          | Type                                                                          |
| :------------ | :---------------------------------------------------------------------------- |
| `ticks`       | ([`Tick`](Tick) \| [`TickConstructorArgs`](interfaces/TickConstructorArgs))[] |
| `tickSpacing` | `number`                                                                      |

#### Defined in

[entities/tickListDataProvider.ts:12](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/tickListDataProvider.ts#L12)

## Properties

### ticks

`Private` **ticks**: readonly [`Tick`](Tick)[]

#### Defined in

[entities/tickListDataProvider.ts:10](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/tickListDataProvider.ts#L10)

## Methods

### getTick

**getTick**(`tick`): `Promise { liquidityGross: BigintIsh ; liquidityNet: BigintIsh }`

Return information corresponding to a specific tick

#### Parameters

| Name   | Type     | Description      |
| :----- | :------- | :--------------- |
| `tick` | `number` | the tick to load |

#### Returns

`Promise { liquidityGross: BigintIsh ; liquidityNet: BigintIsh }`

#### Implementation of

[TickDataProvider](interfaces/TickDataProvider).[getTick](interfaces/TickDataProvider#gettick)

#### Defined in

[entities/tickListDataProvider.ts:18](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/tickListDataProvider.ts#L18)

---

### nextInitializedTickWithinOneWord

**nextInitializedTickWithinOneWord** (`tick`, `lte`, `tickSpacing`): `Promise [number, boolean]`

Return the next tick that is initialized within a single word

#### Parameters

| Name          | Type      | Description                                          |
| :------------ | :-------- | :--------------------------------------------------- |
| `tick`        | `number`  | The current tick                                     |
| `lte`         | `boolean` | Whether the next tick should be lte the current tick |
| `tickSpacing` | `number`  | The tick spacing of the pool                         |

#### Returns

`Promise [number, boolean]`

#### Implementation of

[TickDataProvider](interfaces/TickDataProvider).[nextInitializedTickWithinOneWord](interfaces/TickDataProvider#nextinitializedtickwithinoneword)

#### Defined in

[entities/tickListDataProvider.ts:22](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/tickListDataProvider.ts#L22)
