# SwapXV3Factory
### 部署 SwapX V3 池并管理池协议费用的所有权和控制权
```
  function createPool(
    address tokenA,
    address tokenB,
    uint24 fee
  ) external returns (address pool)
```
为给定的两个代币和费用创建一个池

tokenA 和 tokenB 可以按任意顺序传递：token0/token1 或 token1/token0。tickSpacing 是从费用中检索的。如果池已存在、费用无效或 token 参数无效，则调用将恢复。

#### 参数
|参数名|	类型|	描述|
|:-----:|:-----:|:-----:|
|tokenA|	地址	|所需池中的两个代币之一
|tokenB|    地址|	所需池中两个代币中的另一个
|fee|	uint24|	游泳池所需费用


#### 返回值

|参数名|	类型|	描述|
|:-----:|:-----:|:-----:|
|pool|	地址|	新创建矿池的地址
```
  function setOwner(
    address _owner
  ) external
```

### 更新工厂的所有者

必须由当前所有者调用

#### 参数
|参数名|	类型|	描述|
|:-----:|:-----:|:-----:|
|_owner|	地址|	工厂的新主人|
```
  function enableFeeAmount(
    uint24 fee,
    int24 tickSpacing
  ) public
```

### 使用给定的 tickSpacing 启用费用金额

一旦启用，费用金额将永远不会被删除

#### 参数
|参数名|	类型|	描述|
|:-----:|:-----:|:-----:|
|fee|	uint24|	启用的费用金额，以 bip 的百分之一计价（即 1e-6）|
|tickSpacing|	int24|	使用给定费用金额创建的所有池子强制执行的刻度之间的间隔|