---
sidebar_label: "平方价格数学"
sidebar_position: 12
---

# Class: SqrtPriceMath

## Table of contents

### Constructors

- [constructor](SqrtPriceMath#constructor)

### Methods

- [getAmount0Delta](SqrtPriceMath#getamount0delta)
- [getAmount1Delta](SqrtPriceMath#getamount1delta)
- [getNextSqrtPriceFromAmount0RoundingUp](SqrtPriceMath#getnextsqrtpricefromamount0roundingup)
- [getNextSqrtPriceFromAmount1RoundingDown](SqrtPriceMath#getnextsqrtpricefromamount1roundingdown)
- [getNextSqrtPriceFromInput](SqrtPriceMath#getnextsqrtpricefrominput)
- [getNextSqrtPriceFromOutput](SqrtPriceMath#getnextsqrtpricefromoutput)

## Constructors

### constructor

• `Private` **new SqrtPriceMath**()

Cannot be constructed.

#### Defined in

[utils/sqrtPriceMath.ts:23](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/sqrtPriceMath.ts#L23)

## Methods

### getAmount0Delta

▸ `Static` **getAmount0Delta**(`sqrtRatioAX96`, `sqrtRatioBX96`, `liquidity`, `roundUp`): `default`

#### Parameters

| Name            | Type      |
| :-------------- | :-------- |
| `sqrtRatioAX96` | `default` |
| `sqrtRatioBX96` | `default` |
| `liquidity`     | `default` |
| `roundUp`       | `boolean` |

#### Returns

`default`

#### Defined in

[utils/sqrtPriceMath.ts:25](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/sqrtPriceMath.ts#L25)

---

### getAmount1Delta

▸ `Static` **getAmount1Delta**(`sqrtRatioAX96`, `sqrtRatioBX96`, `liquidity`, `roundUp`): `default`

#### Parameters

| Name            | Type      |
| :-------------- | :-------- |
| `sqrtRatioAX96` | `default` |
| `sqrtRatioBX96` | `default` |
| `liquidity`     | `default` |
| `roundUp`       | `boolean` |

#### Returns

`default`

#### Defined in

[utils/sqrtPriceMath.ts:38](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/sqrtPriceMath.ts#L38)

---

### getNextSqrtPriceFromAmount0RoundingUp

▸ `Static` `Private` **getNextSqrtPriceFromAmount0RoundingUp**(`sqrtPX96`, `liquidity`, `amount`, `add`): `default`

#### Parameters

| Name        | Type      |
| :---------- | :-------- |
| `sqrtPX96`  | `default` |
| `liquidity` | `default` |
| `amount`    | `default` |
| `add`       | `boolean` |

#### Returns

`default`

#### Defined in

[utils/sqrtPriceMath.ts:71](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/sqrtPriceMath.ts#L71)

---

### getNextSqrtPriceFromAmount1RoundingDown

▸ `Static` `Private` **getNextSqrtPriceFromAmount1RoundingDown**(`sqrtPX96`, `liquidity`, `amount`, `add`): `default`

#### Parameters

| Name        | Type      |
| :---------- | :-------- |
| `sqrtPX96`  | `default` |
| `liquidity` | `default` |
| `amount`    | `default` |
| `add`       | `boolean` |

#### Returns

`default`

#### Defined in

[utils/sqrtPriceMath.ts:100](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/sqrtPriceMath.ts#L100)

---

### getNextSqrtPriceFromInput

▸ `Static` **getNextSqrtPriceFromInput**(`sqrtPX96`, `liquidity`, `amountIn`, `zeroForOne`): `default`

#### Parameters

| Name         | Type      |
| :----------- | :-------- |
| `sqrtPX96`   | `default` |
| `liquidity`  | `default` |
| `amountIn`   | `default` |
| `zeroForOne` | `boolean` |

#### Returns

`default`

#### Defined in

[utils/sqrtPriceMath.ts:48](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/sqrtPriceMath.ts#L48)

---

### getNextSqrtPriceFromOutput

▸ `Static` **getNextSqrtPriceFromOutput**(`sqrtPX96`, `liquidity`, `amountOut`, `zeroForOne`): `default`

#### Parameters

| Name         | Type      |
| :----------- | :-------- |
| `sqrtPX96`   | `default` |
| `liquidity`  | `default` |
| `amountOut`  | `default` |
| `zeroForOne` | `boolean` |

#### Returns

`default`

#### Defined in

[utils/sqrtPriceMath.ts:57](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/sqrtPriceMath.ts#L57)
