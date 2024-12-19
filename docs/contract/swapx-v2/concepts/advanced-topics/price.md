# 价格是如何确定的?
正如我们在协议概述中了解到的，SwapX 上的每对实际上都由一个流动性池支撑。流动性池是智能合约，它持有两种不同代币的余额，并执行有关存入和提取它们的规则。主要规则是恒定乘积公式。当提取（购买）代币时，必须存入（出售）一定比例的金额以保持恒定。池中代币的比例与恒定乘积公式相结合，最终决定了掉期执行的价格。

# SwapX 如何处理价格
在 SwapX V1 中，交易总是以“最佳”价格执行，并在执行时计算。有些令人困惑的是，这个计算实际上是用两个不同的公式之一完成的，具体取决于交易是否指定了确切的输入或输出金额。从功能上讲，这两个函数之间的差异很小，但差异的存在本身就增加了概念的复杂性。最初在 V2 中支持这两个函数的尝试被证明是不雅的，因此决定不在核心中提供任何定价函数。相反，对在每次交易后直接检查不变量是否得到满足（考虑费用）。这意味着，V2 对不是依靠定价函数来强制执行不变量，而是简单透明地确保自己的安全，这是一个很好的关注点分离。一个下游好处是 V2 对将更自然地支持可能出现的其他交易类型（例如，在执行时以特定价格交易）。

从高层次来看，在 SwapX V2 中，交易必须在外围定价。好消息是，该库 提供了各种旨在使此过程变得非常简单的功能，并且路由器中的所有交换功能都是考虑到这一点而设计的。

# 交易定价
在 SwapX 上交换代币时，通常希望以精确的输入金额接收尽可能多的输出代币，或者以精确的输出金额支付尽可能少的输入代币。为了计算这些金额，合约必须查找一对的当前储备，以了解当前价格是多少。但是，如果无法访问外部价格 ，则执行此查找并依赖结果并不安全。

假设一个智能合约天真地想要向 DAI/WXOC 对发送 10 DAI，并在当前准备金率的情况下接收尽可能多的 WETH。如果在调用时，这个天真的智能合约只是查找当前价格并执行交易，那么它很容易受到抢先交易的攻击，并可能遭受经济损失。要了解原因，请考虑一个在交易确认之前看到此交易的恶意行为者。他们可以在天真的交换完成之前立即执行掉期，从而大幅改变 DAI/WXOC 的价格，等待天真的交换以不利的汇率执行，然后进行交换以将价格改回天真的交换之前的价格。这种攻击相当便宜且风险低，通常可以获利。

为了防止此类攻击，提交交换时必须能够了解其交换应以 执行的“公平”价格。换句话说，交换需要访问预言机，以确保他们从 SwapX 获得的最佳执行足够接近预言机认为的“真实”价格。虽然这听起来很复杂，但预言机可以简单到只是对一对当前市场价格的链下观察。由于套利，通常情况下，一对的区块内储备比率接近“真实”市场价格。因此，如果用户在考虑到这些知识的情况下提交交易，他们可以确保由于抢先交易造成的损失受到严格限制。例如，这就是 SwapX 前端确保交易安全的方式。它根据观察到的块内价格计算最佳输入/输出量，并使用路由器执行交换，这保证交换以不低于x观察到的块内汇率差 % 的汇率执行，其中x是用户指定的滑点容忍度（默认为 0.5%）。

# Exact Input
如果您希望发送精确数量的输入代币以换取尽可能多的输出代币，则需要使用getAmountsOut。等效的 SDK 函数是getOutputAmount，或用于滑点计算的minimumAmountOut。

# Exact Output
如果您希望以尽可能少的输入代币获得准确数量的输出代币，则需要使用getAmountsIn。等效的 SDK 函数是getInputAmount，或用于滑点计算的maximumAmountIn。