---
sidebar_label: "安全传输选项"
sidebar_position: 14
---

# Interface: SafeTransferOptions

## Table of contents

### Properties

- [data](SafeTransferOptions#data)
- [recipient](SafeTransferOptions#recipient)
- [sender](SafeTransferOptions#sender)
- [tokenId](SafeTransferOptions#tokenid)

## Properties

### data

`Optional` **data**: `string`

The optional parameter that passes data to the `onERC721Received` call for the staker

#### Defined in

[nonfungiblePositionManager.ts:97](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L97)

---

### recipient

**recipient**: `string`

The account that should receive the NFT.

#### Defined in

[nonfungiblePositionManager.ts:88](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L88)

---

### sender

**sender**: `string`

The account sending the NFT.

#### Defined in

[nonfungiblePositionManager.ts:83](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L83)

---

### tokenId

**tokenId**: `BigintIsh`

The id of the token being sent.

#### Defined in

[nonfungiblePositionManager.ts:93](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/nonfungiblePositionManager.ts#L93)
