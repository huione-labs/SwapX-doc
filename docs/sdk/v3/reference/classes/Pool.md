---
sidebar_label: "水池"
sidebar_position: 7
---

# Class: Pool

Represents a V3 pool

## Table of contents

### Constructors

- [constructor](Pool#constructor)

### Properties

- [\_token0Price](Pool#_token0price)
- [\_token1Price](Pool#_token1price)
- [fee](Pool#fee)
- [liquidity](Pool#liquidity)
- [sqrtRatioX96](Pool#sqrtratiox96)
- [tickCurrent](Pool#tickcurrent)
- [tickDataProvider](Pool#tickdataprovider)
- [token0](Pool#token0)
- [token1](Pool#token1)

### Accessors

- [chainId](Pool#chainid)
- [tickSpacing](Pool#tickspacing)
- [token0Price](Pool#token0price)
- [token1Price](Pool#token1price)

### Methods

- [getInputAmount](Pool#getinputamount)
- [getOutputAmount](Pool#getoutputamount)
- [involvesToken](Pool#involvestoken)
- [priceOf](Pool#priceof)
- [swap](Pool#swap)
- [getAddress](Pool#getaddress)

## Constructors

### constructor

**new Pool**(`tokenA`, `tokenB`, `fee`, `sqrtRatioX96`, `liquidity`, `tickCurrent`, `ticks?`)

Construct a pool

#### Parameters

| Name           | Type                                                                                                                               | Default value                   | Description                                                                                     |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------- | :------------------------------ | :---------------------------------------------------------------------------------------------- |
| `tokenA`       | `Token`                                                                                                                            | `undefined`                     | One of the tokens in the pool                                                                   |
| `tokenB`       | `Token`                                                                                                                            | `undefined`                     | The other token in the pool                                                                     |
| `fee`          | [`FeeAmount`](enums/FeeAmount)                                                                                                     | `undefined`                     | The fee in hundredths of a bips of the input amount of every swap that is collected by the pool |
| `sqrtRatioX96` | `BigintIsh`                                                                                                                        | `undefined`                     | The sqrt of the current ratio of amounts of token1 to token0                                    |
| `liquidity`    | `BigintIsh`                                                                                                                        | `undefined`                     | The current value of in range liquidity                                                         |
| `tickCurrent`  | `number`                                                                                                                           | `undefined`                     | The current tick of the pool                                                                    |
| `ticks`        | [`TickDataProvider`](interfaces/TickDataProvider) \| ([`Tick`](Tick) \| [`TickConstructorArgs`](interfaces/TickConstructorArgs))[] | `NO_TICK_DATA_PROVIDER_DEFAULT` | The current state of the pool ticks or a data provider that can return tick data                |

#### Defined in

[entities/pool.ts:70](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L70)

## Properties

### \_token0Price

`Private,Optional` **\_token0Price**: `Price <Token, Token>`

#### Defined in

[entities/pool.ts:41](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L41)

---

### \_token1Price

`Private,Optional` **\_token1Price**: `Price <Token, Token>`

#### Defined in

[entities/pool.ts:42](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L42)

---

### fee

`Readonly` **fee**: [`FeeAmount`](enums/FeeAmount)

#### Defined in

[entities/pool.ts:35](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L35)

---

### liquidity

`Readonly` **liquidity**: `default`

#### Defined in

[entities/pool.ts:37](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L37)

---

### sqrtRatioX96

`Readonly` **sqrtRatioX96**: `default`

#### Defined in

[entities/pool.ts:36](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L36)

---

### tickCurrent

`Readonly` **tickCurrent**: `number`

#### Defined in

[entities/pool.ts:38](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L38)

---

### tickDataProvider

`Readonly` **tickDataProvider**: [`TickDataProvider`](interfaces/TickDataProvider)

#### Defined in

[entities/pool.ts:39](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L39)

---

### token0

`Readonly` **token0**: `Token`

#### Defined in

[entities/pool.ts:33](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L33)

---

### token1

`Readonly` **token1**: `Token`

#### Defined in

[entities/pool.ts:34](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L34)

## Accessors

### chainId

`get` **chainId**(): `number`

Returns the chain ID of the tokens in the pool.

#### Returns

`number`

#### Defined in

[entities/pool.ts:149](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L149)

---

### tickSpacing

`get` **tickSpacing**(): `number`

#### Returns

`number`

#### Defined in

[entities/pool.ts:317](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L317)

---

### token0Price

`get` **token0Price**(): `Price <Token, Token>`

Returns the current mid price of the pool in terms of token0, i.e. the ratio of token1 over token0

#### Returns

`Price <Token, Token>`

#### Defined in

[entities/pool.ts:109](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L109)

---

### token1Price

`get` **token1Price**(): `Price <Token, Token>`

Returns the current mid price of the pool in terms of token1, i.e. the ratio of token0 over token1

#### Returns

`Price <Token, Token>`

#### Defined in

[entities/pool.ts:124](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L124)

## Methods

### getInputAmount

**getInputAmount**(`outputAmount`, `sqrtPriceLimitX96?`): `Promise <[CurrencyAmount <Token>`, [`Pool`](Pool)]>

Given a desired output amount of a token, return the computed input amount and a pool with state updated after the trade

#### Parameters

| Name                 | Type                     | Description                                                                                                                                                                        |
| :------------------- | :----------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `outputAmount`       | `CurrencyAmount <Token>` | the output amount for which to quote the input amount                                                                                                                              |
| `sqrtPriceLimitX96?` | `default`                | The Q64.96 sqrt price limit. If zero for one, the price cannot be less than this value after the swap. If one for zero, the price cannot be greater than this value after the swap |

#### Returns

`Promise <[CurrencyAmount <Token>`, [`Pool`](Pool)]>

The input amount and the pool with updated state

#### Defined in

[entities/pool.ts:185](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L185)

---

### getOutputAmount

**getOutputAmount**(`inputAmount`, `sqrtPriceLimitX96?`): `Promise <[CurrencyAmount <Token>`, [`Pool`](Pool)]>

Given an input amount of a token, return the computed output amount, and a pool with state updated after the trade

#### Parameters

| Name                 | Type                     | Description                                           |
| :------------------- | :----------------------- | :---------------------------------------------------- |
| `inputAmount`        | `CurrencyAmount <Token>` | The input amount for which to quote the output amount |
| `sqrtPriceLimitX96?` | `default`                | The Q64.96 sqrt price limit                           |

#### Returns

`Promise <[CurrencyAmount <Token>`, [`Pool`](Pool)]>

The output amount and the pool with updated state

#### Defined in

[entities/pool.ts:159](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L159)

---

### involvesToken

**involvesToken**(`token`): `boolean`

Returns true if the token is either token0 or token1

#### Parameters

| Name    | Type    | Description        |
| :------ | :------ | :----------------- |
| `token` | `Token` | The token to check |

#### Returns

`boolean`

True if token is either token0 or token

#### Defined in

[entities/pool.ts:102](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L102)

---

### priceOf

**priceOf**(`token`): `Price <Token, Token>`

Return the price of the given token in terms of the other token in the pool.

#### Parameters

| Name    | Type    | Description                  |
| :------ | :------ | :--------------------------- |
| `token` | `Token` | The token to return price of |

#### Returns

`Price <Token, Token>`

The price of the given token, in terms of the other.

#### Defined in

[entities/pool.ts:141](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L141)

---

### swap

`Private` **swap**(`zeroForOne`, `amountSpecified`, `sqrtPriceLimitX96?`): `Promise { amountCalculated: default;liquidity: default;sqrtRatioX96: default;tickCurrent: number }`

Executes a swap

#### Parameters

| Name                 | Type      | Description                                                                                                                                                                        |
| :------------------- | :-------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `zeroForOne`         | `boolean` | Whether the amount in is token0 or token1                                                                                                                                          |
| `amountSpecified`    | `default` | The amount of the swap, which implicitly configures the swap as exact input (positive), or exact output (negative)                                                                 |
| `sqrtPriceLimitX96?` | `default` | The Q64.96 sqrt price limit. If zero for one, the price cannot be less than this value after the swap. If one for zero, the price cannot be greater than this value after the swap |

#### Returns

`Promise { amountCalculated: default ; liquidity: default ; sqrtRatioX96: default ; tickCurrent: number }`

amountCalculated

sqrtRatioX96

liquidity

tickCurrent

#### Defined in

[entities/pool.ts:215](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L215)

---

### getAddress

`Static` **getAddress**(`tokenA`, `tokenB`, `fee`, `initCodeHashManualOverride?`, `factoryAddressOverride?`): `string`

#### Parameters

| Name                          | Type                           |
| :---------------------------- | :----------------------------- |
| `tokenA`                      | `Token`                        |
| `tokenB`                      | `Token`                        |
| `fee`                         | [`FeeAmount`](enums/FeeAmount) |
| `initCodeHashManualOverride?` | `string`                       |
| `factoryAddressOverride?`     | `string`                       |

#### Returns

`string`

#### Defined in

[entities/pool.ts:44](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/pool.ts#L44)
