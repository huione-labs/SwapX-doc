# 无状态执行 SwapX V3 交换的路由器

## Functions

### constructor

```solidity
  function constructor(
  ) public
```

### SwapXV3SwapCallback

```solidity
  function SwapXV3SwapCallback(
    int256 amount0Delta,
    int256 amount1Delta,
    bytes data
  ) external
```

在通过 ISwapXV3Pool#swap 执行交换后，会调用 `msg.sender`。

在实现中，必须向池支付交换所需的代币。必须验证调用此方法的合约是否为由官方 SwapXV3Factory 部署的 SwapXV3Pool。如果没有代币被交换，amount0Delta 和 amount1Delta 可能都为 0。

#### 参数:

| Name           | Type   | Description                                                                                                                                                                             |
| :------------- | :----- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `amount0Delta` | int256 | 在交换结束时，池发送（负数）或接收（正数）的 token0 数量。如果为正数，回调必须向池发送该数量的 token0。 |
| `amount1Delta` | int256 | 在交换结束时，池发送（负数）或接收（正数）的 token1 数量。如果为正数，回调必须向池发送该数量的 token1。 |
| `data`         | bytes  | 通过 ISwapXV3PoolActions#swap 调用传递的任何数据                                                                                                           |

### exactInputSingle

```solidity
  function exactInputSingle(
    struct ISwapRouter.ExactInputSingleParams params
  ) external returns (uint256 amountOut)
```

将一种代币的 amountIn 交换为尽可能多的另一种代币。

#### 参数:

| Name     | Type                                      | Description                                                                            |
| :------- | :---------------------------------------- | :------------------------------------------------------------------------------------- |
| `params` | struct ISwapRouter.ExactInputSingleParams | 交换所需的参数，在 calldata 中编码为 ExactInputSingleParams。 |

#### 返回值:

| Name        | Type    | Description                      |
| :---------- | :------ | :------------------------------- |
| `amountOut` | uint256 | 接收的代币数量 |

### exactInput

```solidity
  function exactInput(
    struct ISwapRouter.ExactInputParams params
  ) external returns (uint256 amountOut)
```

将一种代币的 amountIn 沿指定路径交换为尽可能多的另一种代币。

#### 参数:

| Name     | Type                                | Description                                                                                |
| :------- | :---------------------------------- | :----------------------------------------------------------------------------------------- |
| `params` | struct ISwapRouter.ExactInputParams | 多跳交换所需的参数，在 calldata 中编码为 ExactInputParams。 |

#### 返回值:

| Name        | Type    | Description                      |
| :---------- | :------ | :------------------------------- |
| `amountOut` | uint256 | 接收的代币数量 |

### exactOutputSingle

```solidity
  function exactOutputSingle(
    struct ISwapRouter.ExactOutputSingleParams params
  ) external returns (uint256 amountIn)
```

用尽可能少的代币交换 amountOut 数量的另一种代币。


#### 参数:

| Name     | Type                                       | Description                                                                             |
| :------- | :----------------------------------------- | :-------------------------------------------------------------------------------------- |
| `params` | struct ISwapRouter.ExactOutputSingleParams | 交换所需的参数，在 calldata 中编码为 ExactOutputSingleParams。 |

#### 返回值:

| Name       | Type    | Description                   |
| :--------- | :------ | :---------------------------- |
| `amountIn` | uint256 | 输入代币的数量 |

### exactOutput

```solidity
  function exactOutput(
    struct ISwapRouter.ExactOutputParams params
  ) external returns (uint256 amountIn)
```

用尽可能少的代币沿指定路径（反向路径）交换 amountOut 数量的另一种代币。

#### 参数:

| Name     | Type                                 | Description                                                                                 |
| :------- | :----------------------------------- | :------------------------------------------------------------------------------------------ |
| `params` | struct ISwapRouter.ExactOutputParams | 多跳交换所需的参数，在 calldata 中编码为 ExactOutputParams。 |

#### 返回值:

| Name       | Type    | Description                   |
| :--------- | :------ | :---------------------------- |
| `amountIn` | uint256 |输入代币的数量 |
