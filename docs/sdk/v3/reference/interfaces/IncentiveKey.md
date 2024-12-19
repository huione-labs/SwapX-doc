---
sidebar_label: "激励关键"
sidebar_position: 7
---

# Interface: IncentiveKey

Represents a unique staking program.

## Table of contents

### Properties

- [endTime](IncentiveKey#endtime)
- [pool](IncentiveKey#pool)
- [refundee](IncentiveKey#refundee)
- [rewardToken](IncentiveKey#rewardtoken)
- [startTime](IncentiveKey#starttime)

## Properties

### endTime

**endTime**: `BigintIsh`

The time that the incentive program ends.

#### Defined in

[staker.ts:28](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L28)

---

### pool

**pool**: [`Pool`](classes/Pool)

The pool that the staked positions must provide in.

#### Defined in

[staker.ts:20](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L20)

---

### refundee

**refundee**: `string`

The address which receives any remaining reward tokens at `endTime`.

#### Defined in

[staker.ts:32](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L32)

---

### rewardToken

**rewardToken**: `Token`

The token rewarded for participating in the staking program.

#### Defined in

[staker.ts:16](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L16)

---

### startTime

**startTime**: `BigintIsh`

The time when the incentive program begins.

#### Defined in

[staker.ts:24](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/staker.ts#L24)
