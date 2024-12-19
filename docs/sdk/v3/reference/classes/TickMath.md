---
sidebar_label: "滴答数学"
sidebar_position: 21
---

# Class: TickMath

## Table of contents

### Constructors

- [constructor](TickMath#constructor)

### Properties

- [MAX_SQRT_RATIO](TickMath#max_sqrt_ratio)
- [MAX_TICK](TickMath#max_tick)
- [MIN_SQRT_RATIO](TickMath#min_sqrt_ratio)
- [MIN_TICK](TickMath#min_tick)

### Methods

- [getSqrtRatioAtTick](TickMath#getsqrtratioattick)
- [getTickAtSqrtRatio](TickMath#gettickatsqrtratio)

## Constructors

### constructor

`Private` **new TickMath**()

Cannot be constructed.

#### Defined in

[utils/tickMath.ts:17](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickMath.ts#L17)

## Properties

### MAX_SQRT_RATIO

`Static` **MAX_SQRT_RATIO**: `default`

The sqrt ratio corresponding to the maximum tick that could be used on any pool.

#### Defined in

[utils/tickMath.ts:35](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickMath.ts#L35)

---

### MAX_TICK

`Static` **MAX_TICK**: `number` = `-TickMath.MIN_TICK`

The maximum tick that can be used on any pool.

#### Defined in

[utils/tickMath.ts:26](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickMath.ts#L26)

---

### MIN_SQRT_RATIO

`Static` **MIN_SQRT_RATIO**: `default`

The sqrt ratio corresponding to the minimum tick that could be used on any pool.

#### Defined in

[utils/tickMath.ts:31](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickMath.ts#L31)

---

### MIN_TICK

`Static` **MIN_TICK**: `number` = `-887272`

The minimum tick that can be used on any pool.

#### Defined in

[utils/tickMath.ts:22](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickMath.ts#L22)

## Methods

### getSqrtRatioAtTick

`Static` **getSqrtRatioAtTick**(`tick`): `default`

Returns the sqrt ratio as a Q64.96 for the given tick. The sqrt ratio is computed as sqrt(1.0001)^tick

#### Parameters

| Name   | Type     | Description                                  |
| :----- | :------- | :------------------------------------------- |
| `tick` | `number` | the tick for which to compute the sqrt ratio |

#### Returns

`default`

#### Defined in

[utils/tickMath.ts:41](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickMath.ts#L41)

---

### getTickAtSqrtRatio

`Static` **getTickAtSqrtRatio**(`sqrtRatioX96`): `number`

Returns the tick corresponding to a given sqrt ratio, s.t. \#getSqrtRatioAtTick(tick) &lt;= sqrtRatioX96
and \#getSqrtRatioAtTick(tick + 1) sqrtRatioX96

#### Parameters

| Name           | Type      | Description                                              |
| :------------- | :-------- | :------------------------------------------------------- |
| `sqrtRatioX96` | `default` | the sqrt ratio as a Q64.96 for which to compute the tick |

#### Returns

`number`

#### Defined in

[utils/tickMath.ts:82](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickMath.ts#L82)
