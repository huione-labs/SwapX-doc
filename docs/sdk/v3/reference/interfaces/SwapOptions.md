---
sidebar_label: "掉期期权"
sidebar_position: 16
---

# Interface: SwapOptions

Options for producing the arguments to send calls to the router.

## Table of contents

### Properties

- [deadline](SwapOptions#deadline)
- [fee](SwapOptions#fee)
- [inputTokenPermit](SwapOptions#inputtokenpermit)
- [recipient](SwapOptions#recipient)
- [slippageTolerance](SwapOptions#slippagetolerance)
- [sqrtPriceLimitX96](SwapOptions#sqrtpricelimitx96)

## Properties

### deadline

**deadline**: `BigintIsh`

When the transaction expires, in epoch seconds.

#### Defined in

[swapRouter.ts:30](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L30)

---

### fee

`Optional` **fee**: [`FeeOptions`](FeeOptions)

Optional information for taking a fee on output.

#### Defined in

[swapRouter.ts:45](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L45)

---

### inputTokenPermit

`Optional` **inputTokenPermit**: [`PermitOptions`](modules#permitoptions)

The optional permit parameters for spending the input.

#### Defined in

[swapRouter.ts:35](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L35)

---

### recipient

**recipient**: `string`

The account that should receive the output.

#### Defined in

[swapRouter.ts:25](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L25)

---

### slippageTolerance

**slippageTolerance**: `Percent`

How much the execution price is allowed to move unfavorably from the trade execution price.

#### Defined in

[swapRouter.ts:20](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L20)

---

### sqrtPriceLimitX96

`Optional` **sqrtPriceLimitX96**: `BigintIsh`

The optional price limit for the trade.

#### Defined in

[swapRouter.ts:40](https://github.com/SwapX/v3-sdk/blob/08a7c05/src/swapRouter.ts#L40)
