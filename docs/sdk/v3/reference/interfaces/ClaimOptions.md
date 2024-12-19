---
sidebar_label: "索赔选项"
sidebar_position: 3
---

# Interface: ClaimOptions

Options to specify when claiming rewards.

## Table of contents

### Properties

- [amount](ClaimOptions#amount)
- [recipient](ClaimOptions#recipient)
- [tokenId](ClaimOptions#tokenid)

## Properties

### amount

`Optional` **amount**: `BigintIsh`

The amount of `rewardToken` to claim. 0 claims all.

#### Defined in

[staker.ts:52](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L52)

---

### recipient

**recipient**: `string`

Address to send rewards to.

#### Defined in

[staker.ts:47](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L47)

---

### tokenId

**tokenId**: `BigintIsh`

The id of the NFT

#### Defined in

[staker.ts:42](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L42)
