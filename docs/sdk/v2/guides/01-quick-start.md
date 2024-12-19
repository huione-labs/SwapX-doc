---
sidebar_label: "第一步：快速启动"
sidebar_position: 1
---

The SwapX SDK exists to help developers build on top of SwapX. It's designed to run in any environment that can execute JavaScript (think websites, node scripts, etc.). While simple enough to use in a hackathon project, it's also robust enough to power production applications.

# Installation

The easiest way to consume the SDK is via [npm](https://github.com/SwapX/SwapX-v2-sdk). To install it in your project, simply run `yarn add @swapx/v2-sdk` (or `npm install @swapx/v2-sdk`). This also installs the sdk-core package that is used by both the V2 and V3 SDK and ethers as dependencies.

# Usage

To run code from the SDK in your application, use an `import` or `require` statement, depending on which your environment supports. Note that the guides following this page will use ES6 syntax.

## ES6 (import)

```typescript
import { ChainId } from "@swapx/sdk-core";
import { Pair } from "@swapx/v2-sdk";
console.log(`The chainId of mainnet is ${ChainId.MAINNET}.`);
```

## CommonJS (require)

```typescript
const CORE = require("@swapx/sdk-core");
const V2_SDK = require("@swapx/v2-sdk");
console.log(`The chainId of mainnet is ${CORE.ChainId.MAINNET}.`);
```

# Reference

Comprehensive reference material for the SDK is publicly available on the [SwapX Labs Github](https://github.com/SwapX).
