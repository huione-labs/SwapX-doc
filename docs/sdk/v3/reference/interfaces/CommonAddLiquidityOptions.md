---
sidebar_label: "常见的增加流动性选项"
sidebar_position: 5
---

# Interface: CommonAddLiquidityOptions

Options for producing the calldata to add liquidity.

## Table of contents

### Properties

- [deadline](CommonAddLiquidityOptions#deadline)
- [slippageTolerance](CommonAddLiquidityOptions#slippagetolerance)
- [token0Permit](CommonAddLiquidityOptions#token0permit)
- [token1Permit](CommonAddLiquidityOptions#token1permit)
- [useNative](CommonAddLiquidityOptions#usenative)

## Properties

### deadline

**deadline**: `BigintIsh`

When the transaction expires, in epoch seconds.

#### Defined in

[nonfungiblePositionManager.ts:56](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L56)

---

### slippageTolerance

**slippageTolerance**: `Percent`

How much the pool price is allowed to move.

#### Defined in

[nonfungiblePositionManager.ts:51](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L51)

---

### token0Permit

`Optional` **token0Permit**: [`PermitOptions`](modules#permitoptions)

The optional permit parameters for spending token0

#### Defined in

[nonfungiblePositionManager.ts:66](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L66)

---

### token1Permit

`Optional` **token1Permit**: [`PermitOptions`](modules#permitoptions)

The optional permit parameters for spending token1

#### Defined in

[nonfungiblePositionManager.ts:71](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L71)

---

### useNative

`Optional` **useNative**: `NativeCurrency`

Whether to spend ether. If true, one of the pool tokens must be WETH, by default false

#### Defined in

[nonfungiblePositionManager.ts:61](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L61)
