---
sidebar_label: "收集选项"
sidebar_position: 4
---

# Interface: CollectOptions

## Table of contents

### Properties

- [expectedCurrencyOwed0](CollectOptions#expectedcurrencyowed0)
- [expectedCurrencyOwed1](CollectOptions#expectedcurrencyowed1)
- [recipient](CollectOptions#recipient)
- [tokenId](CollectOptions#tokenid)

## Properties

### expectedCurrencyOwed0

**expectedCurrencyOwed0**: `CurrencyAmount` `Currency`

Expected value of tokensOwed0, including as-of-yet-unaccounted-for fees/liquidity value to be burned

#### Defined in

[nonfungiblePositionManager.ts:114](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L114)

---

### expectedCurrencyOwed1

**expectedCurrencyOwed1**: `CurrencyAmount` `Currency`

Expected value of tokensOwed1, including as-of-yet-unaccounted-for fees/liquidity value to be burned

#### Defined in

[nonfungiblePositionManager.ts:119](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L119)

---

### recipient

**recipient**: `string`

The account that should receive the tokens.

#### Defined in

[nonfungiblePositionManager.ts:124](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L124)

---

### tokenId

**tokenId**: `BigintIsh`

Indicates the ID of the position to collect for.

#### Defined in

[nonfungiblePositionManager.ts:109](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L109)
