---
sidebar_label: "勾选列表"
sidebar_position: 19
---

# Class: TickList

Utility methods for interacting with sorted lists of ticks

## Table of contents

### Constructors

- [constructor](TickList#constructor)

### Methods

- [binarySearch](TickList#binarysearch)
- [getTick](TickList#gettick)
- [isAtOrAboveLargest](TickList#isatorabovelargest)
- [isBelowSmallest](TickList#isbelowsmallest)
- [nextInitializedTick](TickList#nextinitializedtick)
- [nextInitializedTickWithinOneWord](TickList#nextinitializedtickwithinoneword)
- [validateList](TickList#validatelist)

## Constructors

### constructor

• `Private` **new TickList**()

Cannot be constructed

#### Defined in

[utils/tickList.ts:18](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L18)

## Methods

### binarySearch

▸ `Static` `Private` **binarySearch**(`ticks`, `tick`): `number`

Finds the largest tick in the list of ticks that is less than or equal to tick

#### Parameters

| Name    | Type                      | Description                                                      |
| :------ | :------------------------ | :--------------------------------------------------------------- |
| `ticks` | readonly [`Tick`](Tick)[] | list of ticks                                                    |
| `tick`  | `number`                  | tick to find the largest tick that is less than or equal to tick |

#### Returns

`number`

#### Defined in

[utils/tickList.ts:62](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L62)

---

### getTick

▸ `Static` **getTick**(`ticks`, `index`): [`Tick`](Tick)

#### Parameters

| Name    | Type                      |
| :------ | :------------------------ |
| `ticks` | readonly [`Tick`](Tick)[] |
| `index` | `number`                  |

#### Returns

[`Tick`](Tick)

#### Defined in

[utils/tickList.ts:50](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L50)

---

### isAtOrAboveLargest

▸ `Static` **isAtOrAboveLargest**(`ticks`, `tick`): `boolean`

#### Parameters

| Name    | Type                      |
| :------ | :------------------------ |
| `ticks` | readonly [`Tick`](Tick)[] |
| `tick`  | `number`                  |

#### Returns

`boolean`

#### Defined in

[utils/tickList.ts:45](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L45)

---

### isBelowSmallest

▸ `Static` **isBelowSmallest**(`ticks`, `tick`): `boolean`

#### Parameters

| Name    | Type                      |
| :------ | :------------------------ |
| `ticks` | readonly [`Tick`](Tick)[] |
| `tick`  | `number`                  |

#### Returns

`boolean`

#### Defined in

[utils/tickList.ts:40](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L40)

---

### nextInitializedTick

▸ `Static` **nextInitializedTick**(`ticks`, `tick`, `lte`): [`Tick`](Tick)

#### Parameters

| Name    | Type                      |
| :------ | :------------------------ |
| `ticks` | readonly [`Tick`](Tick)[] |
| `tick`  | `number`                  |
| `lte`   | `boolean`                 |

#### Returns

[`Tick`](Tick)

#### Defined in

[utils/tickList.ts:83](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L83)

---

### nextInitializedTickWithinOneWord

▸ `Static` **nextInitializedTickWithinOneWord**(`ticks`, `tick`, `lte`, `tickSpacing`): [`number`, `boolean`]

#### Parameters

| Name          | Type                      |
| :------------ | :------------------------ |
| `ticks`       | readonly [`Tick`](Tick)[] |
| `tick`        | `number`                  |
| `lte`         | `boolean`                 |
| `tickSpacing` | `number`                  |

#### Returns

[`number`, `boolean`]

#### Defined in

[utils/tickList.ts:101](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L101)

---

### validateList

▸ `Static` **validateList**(`ticks`, `tickSpacing`): `void`

#### Parameters

| Name          | Type             |
| :------------ | :--------------- |
| `ticks`       | [`Tick`](Tick)[] |
| `tickSpacing` | `number`         |

#### Returns

`void`

#### Defined in

[utils/tickList.ts:20](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickList.ts#L20)
