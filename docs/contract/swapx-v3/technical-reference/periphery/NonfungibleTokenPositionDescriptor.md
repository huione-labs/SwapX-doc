## 生成包含 JSON 元数据字符串的 Data URI

## Functions

### constructor

```solidity
  function constructor(
  ) public
```

### tokenURI

```solidity
  function tokenURI(
    contract INonfungiblePositionManager positionManager,
    uint256 tokenId
  ) external returns (string)
```

生成描述特定位置管理器中 tokenId 的 URI。

注意：该 URI 可能是一个 data: URI，JSON 内容会直接内嵌其中

#### 参数:

| Name              | Type                                 | Description                                                                    |
| :---------------- | :----------------------------------- | :----------------------------------------------------------------------------- |
| `positionManager` | contract INonfungiblePositionManager |需要描述代币的头寸管理器                         |
| `tokenId`         | uint256                              | 需要生成描述的代币 ID，该 ID 可能无效 |

#### 返回值:

| Name  | Type                                 | Description                          |
| :---- | :----------------------------------- | :----------------------------------- |
| `The` | contract INonfungiblePositionManager | ERC721 元数据的 URI |

### flipRatio

```solidity
  function flipRatio(
  ) public returns (bool)
```

### tokenRatioPriority

```solidity
  function tokenRatioPriority(
  ) public returns (int256)
```
