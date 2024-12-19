---
sidebar_label: "赌注"
sidebar_position: 13
---

# Class: Staker

## Table of contents

### Constructors

- [constructor](Staker#constructor)

### Properties

- [INCENTIVE_KEY_ABI](Staker#incentive_key_abi)
- [INTERFACE](Staker#interface)

### Methods

- [\_encodeIncentiveKey](Staker#_encodeincentivekey)
- [collectRewards](Staker#collectrewards)
- [encodeClaim](Staker#encodeclaim)
- [encodeDeposit](Staker#encodedeposit)
- [withdrawToken](Staker#withdrawtoken)

## Constructors

### constructor

• `Protected` **new Staker**()

#### Defined in

[staker.ts:72](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L72)

## Properties

### INCENTIVE_KEY_ABI

▪ `Static` `Private` **INCENTIVE_KEY_ABI**: `string` = `'tuple(address rewardToken, address pool, uint256 startTime, uint256 endTime, address refundee)'`

#### Defined in

[staker.ts:73](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L73)

---

### INTERFACE

▪ `Static` **INTERFACE**: `Interface`

#### Defined in

[staker.ts:70](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L70)

## Methods

### \_encodeIncentiveKey

▸ `Static` `Private` **\_encodeIncentiveKey**(`incentiveKey`): `Object`

#### Parameters

| Name           | Type                                         | Description                                                  |
| :------------- | :------------------------------------------- | :----------------------------------------------------------- |
| `incentiveKey` | [`IncentiveKey`](../interfaces/IncentiveKey) | An `IncentiveKey` which represents a unique staking program. |

#### Returns

`Object`

An encoded IncentiveKey to be read by ethers

#### Defined in

[staker.ts:194](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L194)

---

### collectRewards

▸ `Static` **collectRewards**(`incentiveKeys`, `options`): [`MethodParameters`](../interfaces/MethodParameters)

Note: A `tokenId` can be staked in many programs but to claim rewards and continue the program you must unstake, claim, and then restake.

#### Parameters

| Name            | Type                                                                                           | Description                                                                                                                                                                                                              |
| :-------------- | :--------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `incentiveKeys` | [`IncentiveKey`](../interfaces/IncentiveKey) \| [`IncentiveKey`](../interfaces/IncentiveKey)[] | An IncentiveKey or array of IncentiveKeys that `tokenId` is staked in. Input an array of IncentiveKeys to claim rewards for each program.                                                                                |
| `options`       | [`ClaimOptions`](../interfaces/ClaimOptions)                                                   | ClaimOptions to specify tokenId, recipient, and amount wanting to collect. Note that you can only specify one amount and one recipient across the various programs if you are collecting from multiple programs at once. |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

#### Defined in

[staker.ts:107](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L107)

---

### encodeClaim

▸ `Static` `Private` **encodeClaim**(`incentiveKey`, `options`): `string`[]

To claim rewards, must unstake and then claim.

#### Parameters

| Name           | Type                                         | Description                                                                  |
| :------------- | :------------------------------------------- | :--------------------------------------------------------------------------- |
| `incentiveKey` | [`IncentiveKey`](../interfaces/IncentiveKey) | The unique identifier of a staking program.                                  |
| `options`      | [`ClaimOptions`](../interfaces/ClaimOptions) | Options for producing the calldata to claim. Can't claim unless you unstake. |

#### Returns

`string`[]

The calldatas for 'unstakeToken' and 'claimReward'.

#### Defined in

[staker.ts:82](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L82)

---

### encodeDeposit

▸ `Static` **encodeDeposit**(`incentiveKeys`): `string`

#### Parameters

| Name            | Type                                                                                           | Description                                                                                                        |
| :-------------- | :--------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------- |
| `incentiveKeys` | [`IncentiveKey`](../interfaces/IncentiveKey) \| [`IncentiveKey`](../interfaces/IncentiveKey)[] | A single IncentiveKey or array of IncentiveKeys to be encoded and used in the data parameter in `safeTransferFrom` |

#### Returns

`string`

An IncentiveKey as a string

#### Defined in

[staker.ts:173](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L173)

---

### withdrawToken

▸ `Static` **withdrawToken**(`incentiveKeys`, `withdrawOptions`): [`MethodParameters`](../interfaces/MethodParameters)

#### Parameters

| Name              | Type                                                                                           | Description                                                                                                                              |
| :---------------- | :--------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| `incentiveKeys`   | [`IncentiveKey`](../interfaces/IncentiveKey) \| [`IncentiveKey`](../interfaces/IncentiveKey)[] | A list of incentiveKeys to unstake from. Should include all incentiveKeys (unique staking programs) that `options.tokenId` is staked in. |
| `withdrawOptions` | [`FullWithdrawOptions`](../modules#fullwithdrawoptions)                                        | Options for producing claim calldata and withdraw calldata. Can't withdraw without unstaking all programs for `tokenId`.                 |

#### Returns

[`MethodParameters`](../interfaces/MethodParameters)

Calldata for unstaking, claiming, and withdrawing.

#### Defined in

[staker.ts:136](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L136)
