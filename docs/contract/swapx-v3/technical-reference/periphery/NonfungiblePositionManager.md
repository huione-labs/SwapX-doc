# 将 SwapX V3 头寸封装为 ERC721 非同质化代币接口

## 函数

### 构造函数

```solidity
  function constructor(
  ) public
```

### positions

```solidity
  function positions(
    uint256 tokenId
  ) external view returns (uint96 nonce, address operator, address token0, address token1, uint24 fee, int24 tickLower, int24 tickUpper, uint128 liquidity, uint256 feeGrowthInside0LastX128, uint256 feeGrowthInside1LastX128, uint128 tokensOwed0, uint128 tokensOwed1)
```

返回与给定 tokenId 关联的头寸信息。

注意： 如果 tokenId 无效，则会抛出错误。

#### 参数:

| 名称      | 类型    | 描述                                      |
| :-------- | :------ | :----------------------------------------------- |
| `tokenId` | uint256 | 表示头寸的代币 ID |

#### 返回值:

| **名称**                   | **类型**   | **描述**                                                             |
|-----------------------------|------------|----------------------------------------------------------------------|
| `nonce`                    | `uint96`   | 许可的随机数                                                         |
| `operator`                 | `address`  | 被批准进行支出的地址                                                 |
| `token0`                   | `address`  | 特定池子的 `token0` 地址                                             |
| `token1`                   | `address`  | 特定池子的 `token1` 地址                                             |
| `fee`                      | `uint24`   | 与池子相关的手续费                                                   |
| `tickLower`                | `int24`    | 头寸的 tick 范围下限                                                 |
| `tickUpper`                | `int24`    | 头寸的 tick 范围上限                                                 |
| `liquidity`                | `uint128`  | 头寸的流动性                                                         |
| `feeGrowthInside0LastX128` | `uint256`  | 该头寸上次操作时 `token0` 的手续费增长                                |
| `feeGrowthInside1LastX128` | `uint256`  | 该头寸上次操作时 `token1` 的手续费增长                                |
| `tokensOwed0`              | `uint128`  | 截至上次计算时头寸未领取的 `token0` 数量                              |
| `tokensOwed1`              | `uint128`  | 截至上次计算时头寸未领取的 `token1` 数量                              |

### mint

```solidity
  function mint(
    struct INonfungiblePositionManager.MintParams params
  ) external returns (uint256 tokenId, uint128 liquidity, uint256 amount0, uint256 amount1)
```

创建一个新的头寸，并将其包装成 NFT。

当池子已存在并且已初始化时调用。如果池子已创建但未初始化，则不会有对应的方法，因此默认假设池子已初始化。

#### 参数:

| 名称     | 类型                                          | 描述                                                                  |
| :------- | :-------------------------------------------- | :--------------------------------------------------------------------------- |
| `params` | struct INonfungiblePositionManager.MintParams | 铸造头寸所需的参数，在 calldata 中编码为 MintParams |

#### 返回值:

| 名称        | 类型    | 描述                                             |
| :---------- | :------ | :------------------------------------------------------ |
| `tokenId`   | uint256 | 表示已铸造头寸的代币 ID |
| `liquidity` | uint128 | 该头寸的流动性               |
| `amount0`   | uint256 | token0 的数量                                   |
| `amount1`   | uint256 | token1 的数量                                |

### tokenURI

```solidity
  function tokenURI(
    uint256 tokenId
  ) public view returns (string)
```

Returns a URI describing a particular token ID

#### 参数:

| 名称      | 类型    | 描述                                              |
| :-------- | :------ | :------------------------------------------------------- |
| `tokenId` | uint256 | The ID of the token that represents the minted position  |

#### 返回值:

返回描述指定 tokenId 的 URI。

### baseURI

```solidity
  function baseURI(
  ) public returns (string)
```

### increaseLiquidity

```solidity
  function increaseLiquidity(
    struct INonfungiblePositionManager.IncreaseLiquidityParams params
  ) external returns (uint128 liquidity, uint256 amount0, uint256 amount1)
```

增加头寸中的流动性，所需的代币由 `msg.sender` 提供。

#### 参数:

| 名称     | 类型                                                       | 描述                                                         |
| :------- | :--------------------------------------------------------- | :------------------------------------------------------------------ |
| `params` | struct INonfungiblePositionManager.IncreaseLiquidityParams | 需要增加流动性的代币ID |

#### 返回值:

| 名称        | 类型    | 描述                                          |
| :---------- | :------ | :--------------------------------------------------- |
| `liquidity` | uint128 | 增加后头寸的流动性 |
| `amount0`   | uint256 | 达到增加流动性所需的 token0 数量  |
| `amount1`   | uint256 | 达到增加流动性所需的 token1 数量 |

### decreaseLiquidity

```solidity
  function decreaseLiquidity(
    struct INonfungiblePositionManager.DecreaseLiquidityParams params
  ) external returns (uint256 amount0, uint256 amount1)
```

减少头寸中的流动性，并将其记入该头寸的欠款中.

#### 参数:

| 名称     | 类型                                                       | 描述                                                         |
| :------- | :--------------------------------------------------------- | :------------------------------------------------------------------ |
| `params` | struct INonfungiblePositionManager.DecreaseLiquidityParams | 需要减少流动性的代币 ID |

#### 返回值:

| 名称      | 类型    | 描述                                                  |
| :-------- | :------ | :----------------------------------------------------------- |
| `amount0` | uint256 | 头寸欠款中记录的 token0 数量 |
| `amount1` | uint256 | 头寸欠款中记录的 token1 数量 |

### collect

```solidity
  function collect(
    struct INonfungiblePositionManager.CollectParams params
  ) external returns (uint256 amount0, uint256 amount1)
```

将指定头寸中最多的欠费收集并转给接收者。

#### 参数:

| 名称     | 类型                                             | 描述                                                     |
| :------- | :----------------------------------------------- | :-------------------------------------------------------------- |
| `params` | struct INonfungiblePositionManager.CollectParams | 需要收集代币的 NFT ID |


#### 返回值:

| 名称      | 类型    | 描述                            |
| :-------- | :------ | :------------------------------------- |
| `amount0` | uint256 | 收集到的 token0 的费用数量 |
| `amount1` | uint256 | 收集到的 token1 的费用数量 |

### burn

```solidity
  function burn(
    uint256 tokenId
  ) external
```

销毁指定的 tokenId，将其从 NFT 合约中删除。销毁前，必须清空所有流动性，并收集所有欠款。

#### 参数:

| 名称      | 类型    | 描述                              |
| :-------- | :------ | :--------------------------------------- |
| `tokenId` | uint256 | 需要被销毁的代币 ID |

### \_getAndIncrementNonce

```solidity
  function _getAndIncrementNonce(
  ) internal returns (uint256)
```

### getApproved

```solidity
  function getApproved(
  ) public view returns (address)
```

返回 tokenId 代币被批准的账户。
Requirements:

- `tokenId` 必须存在。

### \_approve

```solidity
  function _approve(
  ) internal
```

重写 _approve 方法，使用头寸中的操作员，该操作员与头寸许可随机数打包在一起。
