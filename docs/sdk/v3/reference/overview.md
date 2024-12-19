## Table of contents

### Enumerations

- [FeeAmount](enums/FeeAmount)

### Classes

- [FullMath](classes/FullMath)
- [LiquidityMath](classes/LiquidityMath)
- [Multicall](classes/Multicall)
- [NoTickDataProvider](classes/NoTickDataProvider)
- [NonfungiblePositionManager](classes/NonfungiblePositionManager)
- [Payments](classes/Payments)
- [Pool](classes/Pool)
- [Position](classes/Position)
- [PositionLibrary](classes/PositionLibrary)
- [Route](classes/Route)
- [SelfPermit](classes/SelfPermit)
- [SqrtPriceMath](classes/SqrtPriceMath)
- [Staker](classes/Staker)
- [SwapMath](classes/SwapMath)
- [SwapQuoter](classes/SwapQuoter)
- [SwapRouter](classes/SwapRouter)
- [Tick](classes/Tick)
- [TickLibrary](classes/TickLibrary)
- [TickList](classes/TickList)
- [TickListDataProvider](classes/TickListDataProvider)
- [TickMath](classes/TickMath)
- [Trade](classes/Trade)

### Interfaces

- [AllowedPermitArguments](interfaces/AllowedPermitArguments)
- [BestTradeOptions](interfaces/BestTradeOptions)
- [ClaimOptions](interfaces/ClaimOptions)
- [CollectOptions](interfaces/CollectOptions)
- [CommonAddLiquidityOptions](interfaces/CommonAddLiquidityOptions)
- [FeeOptions](interfaces/FeeOptions)
- [IncentiveKey](interfaces/IncentiveKey)
- [IncreaseSpecificOptions](interfaces/IncreaseSpecificOptions)
- [MethodParameters](interfaces/MethodParameters)
- [MintSpecificOptions](interfaces/MintSpecificOptions)
- [NFTPermitOptions](interfaces/NFTPermitOptions)
- [QuoteOptions](interfaces/QuoteOptions)
- [RemoveLiquidityOptions](interfaces/RemoveLiquidityOptions)
- [SafeTransferOptions](interfaces/SafeTransferOptions)
- [StandardPermitArguments](interfaces/StandardPermitArguments)
- [SwapOptions](interfaces/SwapOptions)
- [TickConstructorArgs](interfaces/TickConstructorArgs)
- [TickDataProvider](interfaces/TickDataProvider)
- [WithdrawOptions](interfaces/WithdrawOptions)

### Type Aliases

- [AddLiquidityOptions](modules#addliquidityoptions)
- [FullWithdrawOptions](modules#fullwithdrawoptions)
- [IncreaseOptions](modules#increaseoptions)
- [MintOptions](modules#mintoptions)
- [PermitOptions](modules#permitoptions)

### Variables

- [ADDRESS_ZERO](modules#address_zero)
- [FACTORY_ADDRESS](modules#factory_address)
- [POOL_INIT_CODE_HASH](modules#pool_init_code_hash)
- [TICK_SPACINGS](modules#tick_spacings)

### Functions

- [computePoolAddress](modules#computepooladdress)
- [encodeRouteToPath](modules#encoderoutetopath)
- [encodeSqrtRatioX96](modules#encodesqrtratiox96)
- [isSorted](modules#issorted)
- [maxLiquidityForAmounts](modules#maxliquidityforamounts)
- [mostSignificantBit](modules#mostsignificantbit)
- [nearestUsableTick](modules#nearestusabletick)
- [priceToClosestTick](modules#pricetoclosesttick)
- [subIn256](modules#subin256)
- [tickToPrice](modules#ticktoprice)
- [toHex](modules#tohex)
- [tradeComparator](modules#tradecomparator)

## Type Aliases

### AddLiquidityOptions

Ƭ **AddLiquidityOptions**: [`MintOptions`](modules#mintoptions) \| [`IncreaseOptions`](modules#increaseoptions)

#### Defined in

[nonfungiblePositionManager.ts:77](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L77)

---

### FullWithdrawOptions

Ƭ **FullWithdrawOptions**: [`ClaimOptions`](interfaces/ClaimOptions) & [`WithdrawOptions`](interfaces/WithdrawOptions)

#### Defined in

[staker.ts:8](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L8)

---

### IncreaseOptions

Ƭ **IncreaseOptions**: [`CommonAddLiquidityOptions`](interfaces/CommonAddLiquidityOptions) & [`IncreaseSpecificOptions`](interfaces/IncreaseSpecificOptions)

#### Defined in

[nonfungiblePositionManager.ts:75](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L75)

---

### MintOptions

Ƭ **MintOptions**: [`CommonAddLiquidityOptions`](interfaces/CommonAddLiquidityOptions) & [`MintSpecificOptions`](interfaces/MintSpecificOptions)

#### Defined in

[nonfungiblePositionManager.ts:74](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L74)

---

### PermitOptions

Ƭ **PermitOptions**: [`StandardPermitArguments`](interfaces/StandardPermitArguments) \| [`AllowedPermitArguments`](interfaces/AllowedPermitArguments)

#### Defined in

[selfPermit.ts:22](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/selfPermit.ts#L22)

## Variables

### ADDRESS_ZERO

`Const` **ADDRESS_ZERO**: `"0x0000000000000000000000000000000000000000"`

#### Defined in

[constants.ts:3](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/constants.ts#L3)

---

### FACTORY_ADDRESS

`Const` **FACTORY_ADDRESS**: `"0x1F98431c8aD98523631AE4a59f267346ea31F984"`

#### Defined in

[constants.ts:1](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/constants.ts#L1)

---

### POOL_INIT_CODE_HASH

`Const` **POOL_INIT_CODE_HASH**: `"0xe34f199b19b2b4f47f68442619d555527d244f78a3297ea89325f843f87b8b54"`

#### Defined in

[constants.ts:5](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/constants.ts#L5)

---

### TICK_SPACINGS

`Const` **TICK_SPACINGS**: \{ [amount in FeeAmount]: number \}

The default factory tick spacings by fee amount.

#### Defined in

[constants.ts:20](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/constants.ts#L20)

## Functions

### computePoolAddress

**computePoolAddress**(`__namedParameters`): `string`

Computes a pool address

#### Parameters

| Name                                            | Type                           |
| :---------------------------------------------- | :----------------------------- |
| `__namedParameters`                             | `Object`                       |
| `__namedParameters.factoryAddress`              | `string`                       |
| `__namedParameters.fee`                         | [`FeeAmount`](enums/FeeAmount) |
| `__namedParameters.initCodeHashManualOverride?` | `string`                       |
| `__namedParameters.tokenA`                      | `Token`                        |
| `__namedParameters.tokenB`                      | `Token`                        |

#### Returns

`string`

The pool address

#### Defined in

[utils/computePoolAddress.ts:16](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/computePoolAddress.ts#L16)

---

### encodeRouteToPath

**encodeRouteToPath**(`route`, `exactOutput`): `string`

Converts a route to a hex encoded path

#### Parameters

| Name          | Type                                            | Description                                                                   |
| :------------ | :---------------------------------------------- | :---------------------------------------------------------------------------- |
| `route`       | [`Route`](classes/Route) `Currency`, `Currency` | the v3 path to convert to an encoded path                                     |
| `exactOutput` | `boolean`                                       | whether the route should be encoded in reverse, for making exact output swaps |

#### Returns

`string`

#### Defined in

[utils/encodeRouteToPath.ts:11](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/encodeRouteToPath.ts#L11)

---

### encodeSqrtRatioX96

**encodeSqrtRatioX96**(`amount1`, `amount0`): `JSBI`

Returns the sqrt ratio as a Q64.96 corresponding to a given ratio of amount1 and amount0

#### Parameters

| Name      | Type        | Description                                       |
| :-------- | :---------- | :------------------------------------------------ |
| `amount1` | `BigintIsh` | The numerator amount i.e., the amount of token1   |
| `amount0` | `BigintIsh` | The denominator amount i.e., the amount of token0 |

#### Returns

`JSBI`

The sqrt ratio

#### Defined in

[utils/encodeSqrtRatioX96.ts:11](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/encodeSqrtRatioX96.ts#L11)

---

### isSorted

**isSorted** `T` (`list`, `comparator`): `boolean`

Determines if a tick list is sorted

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Parameters

| Name         | Type                             | Description    |
| :----------- | :------------------------------- | :------------- |
| `list`       | `T`[]                            | The tick list  |
| `comparator` | (`a`: `T`, `b`: `T`) => `number` | The comparator |

#### Returns

`boolean`

true if sorted

#### Defined in

[utils/isSorted.ts:7](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/isSorted.ts#L7)

---

### maxLiquidityForAmounts

**maxLiquidityForAmounts**(`sqrtRatioCurrentX96`, `sqrtRatioAX96`, `sqrtRatioBX96`, `amount0`, `amount1`, `useFullPrecision`): `JSBI`

Computes the maximum amount of liquidity received for a given amount of token0, token1,
and the prices at the tick boundaries.

#### Parameters

| Name                  | Type        | Description                                                                                                               |
| :-------------------- | :---------- | :------------------------------------------------------------------------------------------------------------------------ |
| `sqrtRatioCurrentX96` | `default`   | the current price                                                                                                         |
| `sqrtRatioAX96`       | `default`   | price at lower boundary                                                                                                   |
| `sqrtRatioBX96`       | `default`   | price at upper boundary                                                                                                   |
| `amount0`             | `BigintIsh` | token0 amount                                                                                                             |
| `amount1`             | `BigintIsh` | token1 amount                                                                                                             |
| `useFullPrecision`    | `boolean`   | if false, liquidity will be maximized according to what the router can calculate, not what core can theoretically support |

#### Returns

`JSBI`

#### Defined in

[utils/maxLiquidityForAmounts.ts:68](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/maxLiquidityForAmounts.ts#L68)

---

### mostSignificantBit

**mostSignificantBit**(`x`): `number`

#### Parameters

| Name | Type      |
| :--- | :-------- |
| `x`  | `default` |

#### Returns

`number`

#### Defined in

[utils/mostSignificantBit.ts:12](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/mostSignificantBit.ts#L12)

---

### nearestUsableTick

**nearestUsableTick**(`tick`, `tickSpacing`): `number`

Returns the closest tick that is nearest a given tick and usable for the given tick spacing

#### Parameters

| Name          | Type     | Description             |
| :------------ | :------- | :---------------------- |
| `tick`        | `number` | the target tick         |
| `tickSpacing` | `number` | the spacing of the pool |

#### Returns

`number`

#### Defined in

[utils/nearestUsableTick.ts:9](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/nearestUsableTick.ts#L9)

---

### priceToClosestTick

**priceToClosestTick**(`price`): `number`

Returns the first tick for which the given price is greater than or equal to the tick price

#### Parameters

| Name    | Type                     | Description                                                                                                                                                                      |
| :------ | :----------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `price` | `Price` `Token`, `Token` | for which to return the closest tick that represents a price less than or equal to the input price, i.e. the price of the returned tick is less than or equal to the input price |

#### Returns

`number`

#### Defined in

[utils/priceTickConversions.ts:29](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/priceTickConversions.ts#L29)

---

### subIn256

**subIn256**(`x`, `y`): `JSBI`

#### Parameters

| Name | Type      |
| :--- | :-------- |
| `x`  | `default` |
| `y`  | `default` |

#### Returns

`JSBI`

#### Defined in

[utils/tickLibrary.ts:11](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/tickLibrary.ts#L11)

---

### tickToPrice

**tickToPrice**(`baseToken`, `quoteToken`, `tick`): `Price` `Token`, `Token`

Returns a price object corresponding to the input tick and the base/quote token
Inputs must be tokens because the address order is used to interpret the price represented by the tick

#### Parameters

| Name         | Type     | Description                            |
| :----------- | :------- | :------------------------------------- |
| `baseToken`  | `Token`  | the base token of the price            |
| `quoteToken` | `Token`  | the quote token of the price           |
| `tick`       | `number` | the tick for which to return the price |

#### Returns

`Price` `Token`, `Token`

#### Defined in

[utils/priceTickConversions.ts:14](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/priceTickConversions.ts#L14)

---

### toHex

**toHex**(`bigintIsh`): `string`

Converts a big int to a hex string

#### Parameters

| Name        | Type        |
| :---------- | :---------- |
| `bigintIsh` | `BigintIsh` |

#### Returns

`string`

The hex encoded calldata

#### Defined in

[utils/calldata.ts:23](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/utils/calldata.ts#L23)

---

### tradeComparator

**tradeComparator** `TInput`, `TOutput`, `TTradeType` (`a`, `b`): `number`

Trades comparator, an extension of the input output comparator that also considers other dimensions of the trade in ranking them

#### Type parameters

| Name         | Type                | Description                                        |
| :----------- | :------------------ | :------------------------------------------------- |
| `TInput`     | extends `Currency`  | The input token, either Ether or an ERC-20         |
| `TOutput`    | extends `Currency`  | The output token, either Ether or an ERC-20        |
| `TTradeType` | extends `TradeType` | The trade type, either exact input or exact output |

#### Parameters

| Name | Type                                                       | Description                 |
| :--- | :--------------------------------------------------------- | :-------------------------- |
| `a`  | [`Trade`](classes/Trade) `TInput`, `TOutput`, `TTradeType` | The first trade to compare  |
| `b`  | [`Trade`](classes/Trade) `TInput`, `TOutput`, `TTradeType` | The second trade to compare |

#### Returns

`number`

A sorted ordering for two neighboring elements in a trade array

#### Defined in

[entities/trade.ts:16](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/entities/trade.ts#L16)
