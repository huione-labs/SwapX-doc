# SwapXV3Pool

## 区块时间戳
```
  function _blockTimestamp(
  ) internal view virtual returns (uint32)
```
返回截断为 32 位的区块时间戳，即 mod 2 * * 32。此方法在测试中被重写。

### 返回累计的tick快照、每流动性秒数和tick范围内的秒数
```
  function snapshotCumulativesInside(
    int24 tickLower,
    int24 tickUpper
  ) external view override noDelegateCall returns (int56 tickCumulativeInside, uint160 secondsPerLiquidityInsideX128, uint32 secondsInside)
```
快照只能与在某个头寸存在期间拍摄的其他快照进行比较。也就是说，如果某个头寸没有在拍摄第一个快照和拍摄第二个快照之间的整个时间段内保持，则无法比较快照。

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|tickLower|	int24|	范围的下限|
|tickUpper|	int24|	范围的上限|

#### 返回值
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|tickCumulativeInside|	int56|	该范围的刻度累加器的快照|
|secondsPerLiquidityInsideX128|	uint160|	范围内每个流动性的秒数快照|
|secondsInside|	uint32|	范围内每个流动性的秒数快照|


### secondsAgo返回从当前区块时间戳开始的每个时间戳的累积刻度和流动性
```
  function observe(
    uint32[] secondsAgos
  ) external view override noDelegateCall returns (int56[] tickCumulatives, uint160[] secondsPerLiquidityCumulativeX128s)
```
要获取时间加权平均刻度或流动性范围，您必须使用两个值调用此函数，一个值代表期间的开始，另一个值代表期间的结束。例如，要获取最后一小时的时间加权平均刻度，您必须使用 secondsAgos = [3600, 0]调用它。时间加权平均刻度表示池的几何时间加权平均价格，以 token1 / token0 的对数底 sqrt(1.0001) 为单位。TickMath 库可用于将刻度值转换为比率。

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|secondsAgos|	uint32[]|	应返回多久以前的每个累计报价和流动性值|

#### 返回值
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|tickCumulatives|	int56[]|	secondsAgos从当前区块时间戳开始的累计刻度值|
|secondsPerLiquidityCumulativeX128s|	uint160[]	|secondsAgos从当前区块开始，每个流动性范围内值的累计秒数|

#### 时间戳
```
  function increaseObservationCardinalityNext(
    uint16 observationCardinalityNext
  ) external override lock noDelegateCall
```
增加该池将存储的最大价格和流动性观察数量

如果池中已经有一个大于或等于输入的observationCardinalityNext的observationCardinalityNext，则此方法是无操作的。

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|observationCardinalityNext|	uint16|	池需要存储的最小观测数|

### 设置矿池的初始价格
```
  function initialize(
    uint160 sqrtPriceX96
  ) external override
```

未锁定，因为它初始化为未锁定

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|sqrtPriceX96|	uint160|	该池的初始平方价格为 Q64.96|



### 为给定的接收者/tickLower/tickUpper 位置增加流动性
```
  function mint(
    address recipient,
    int24 tickLower,
    int24 tickUpper,
    uint128 amount,
    bytes data
  ) external override lock returns (uint256 amount0, uint256 amount1)
```

noDelegateCall通过_modifyPosition间接应用

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|recipient|	地址|	将创建流动性的地址|
|tickLower|	int24|	需要增加流动性的头寸的最低价格|
|tickUpper|	int24|	添加流动性的头寸的上限|
|amount|	uint128|	流动性的产生量|
|data|	字节|	任何应传递给回调的数据|

#### 返回值
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|amount0|	uint256|	为铸造给定数量的流动性而支付的 token0 数量。与回调中的值匹配|
|amount1|	uint256|	为铸造给定数量的流动性而支付的 token1 数量。与回调中的值匹配|


### 收集代币
```
 function collect(
    address recipient,
    int24 tickLower,
    int24 tickUpper,
    uint128 amount0Requested,
    uint128 amount1Requested
  ) external override lock returns (uint128 amount0, uint128 amount1)
```

不重新计算已赚取的费用，这必须通过铸造或销毁任何数量的流动性来完成。收集必须由仓位所有者调用。要仅提取 token0 或 token1，amount0Requested 或 amount1Requested 可以设置为零。要提取代币，调用者可以传递任何大于实际代币的值，例如 type(uint128).max。代币可能来自累积的交换费或销毁的流动性。

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|recipient|	地址|	收取费用的地址|
|tickLower|	int24	|收取费用的仓位最低价格|
|tickUpper|	int24|	收取费用的头寸的上限|
|amount0Requested|	uint128|	应提取多少 token0|
|amount1Requested|	uint128| 应提取多少 token1|

#### 返回值
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|amount0|	uint128|	token0 收取的费用金额|
|amount1|	uint128|	token1 收取的费用金额|




### 销毁发送方的流动性以及为头寸注入流动性的账户代币
```
  function burn(
    int24 tickLower,
    int24 tickUpper,
    uint128 amount
  ) external override lock returns (uint256 amount0, uint256 amount1)
```

noDelegateCall通过_modifyPosition间接应用

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|tickLower|	int24|	消耗流动性的头寸的最低价格|
|tickUpper|	int24|	消耗流动性的头寸的上限|
|amount|	uint128|	要消耗多少流动性|

#### 返回值
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|amount0|	uint256|	发送给接收者的 token0 数量|
|amount1|	uint256	|发送给接收者的 token1 数量|



### 将 token0 交换为 token1，或将 token1 交换为 token0
```
  function swap(
    address recipient,
    bool zeroForOne,
    int256 amountSpecified,
    uint160 sqrtPriceLimitX96,
    bytes data
  ) external override noDelegateCall returns (int256 amount0, int256 amount1)
```
该方法的调用者会收到 ISwapXV3SwapCallback#SwapXV3SwapCallback 形式的回调

#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|recipient|	地址|	接收交换输出的地址|
|zeroForOne|	布尔值|	交换的方向，true 表示 token0 到 token1，false 表示 token1 到 token0|
|amountSpecified|	int256|	交换的金额，隐式地将交换配置为精确输入（正）或精确输出（负）|
|sqrtPriceLimitX96|	uint160|	Q64.96 平方根价格限制。如果为零，则交换后价格不能低于此值。如果为一，则交换后价格不能高于此值|
|data|	字节|	任何要传递给回调的数据|

#### 返回值
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|amount0|	int256|	池中 token0 余额的 delta，负数时精确，正数时最小|
|amount1|	int256|	池中 token1 余额的 delta，负数时精确，正数时最小|



### 收取池中累积的协议费用
```
  function collectProtocol(
    address recipient,
    uint128 amount0Requested,
    uint128 amount1Requested
  ) external override lock onlyFactoryOwner returns (uint128 amount0, uint128 amount1)
```


#### 参数
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|recipient|	地址|	收取的协议费用应发送到的地址|
|amount0Requested|	uint128|	token0 的最大发送数量，可以为 0，表示只对 token1 收取费用|
|amount1Requested|	uint128|	发送 token1 的最大数量，可以为 0，表示只对 token0 收取费用|

#### 返回值
|参数名|	类型|	描述|
|:----:|:----:|:----:|
|amount0|	uint128|	token0 中收取的协议费用|
|amount1|	uint128|	以 token1 形式收取的协议费用|