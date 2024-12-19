# SwapXV3PoolDeployer
```
  function deploy(
    address factory,
    address token0,
    address token1,
    uint24 fee,
    int24 tickSpacing
  ) internal returns (address pool)
```

通过暂时设置参数存储槽，然后在部署池后清除它，来部署具有给定参数的池。

#### 参数
|参数名|	类型|	描述|
|:-----:|:-----:|:-----:|
|factory|	地址|	SwapX V3工厂的合约地址|
|token0|	地址|	按照地址排序的池中第一个代币|
|token1|	地址|	按照地址排序的池中的第二个代币|
|fee|	uint24|	每次在池中交换时收取的费用，以百分之一的 bip 计价|
|tickSpacing|	int24|	可用刻度之间的间距|