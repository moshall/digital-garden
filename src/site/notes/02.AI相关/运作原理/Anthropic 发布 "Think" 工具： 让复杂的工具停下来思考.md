---
{"dg-publish":true,"permalink":"/02.AI相关/运作原理/Anthropic 发布 \"Think\" 工具： 让复杂的工具停下来思考/"}
---


AI加速器@AI行业圈子 2025年03月23日 20:54

[[99.附件/Img/81d69d0c0af83fc448f27bcf8bf982a3_MD5.gif\|Open: 9db2dfa665c3598b2755d02255aeb62d_MD5.gif]]
![81d69d0c0af83fc448f27bcf8bf982a3_MD5](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/81d69d0c0af83fc448f27bcf8bf982a3_MD5.gif?cd-oss-obs)

Anthropic 的迷人新提示工程技巧。他们使用标准工具调用机制来定义一个名为“思考”的工具，如下所示：

```
`{` `"name": "think",` `"description": "Use the tool to think about something. It will not obtain new information or change the database, but just append the thought to the log. Use it when complex reasoning or some cache memory is needed.",` `"input_schema": {` `"type": "object",` `"properties": {` `"thought": {` `"type": "string",` `"description": "A thought to think about."` `}` `},` `"required": ["thought"]` `}``}`
```

  

## 这个工具什么也不做

LLM 工具（如web_search）通常涉及某种实现 - 模型请求工具执行，然后外部请求消失并执行指定的工具并将结果反馈到对话中。

“思考”工具是无操作的 - 没有实现，它只是允许模型使用其现有的训练来判断何时使用工具来停止并将一些额外的想法转储到上下文中。

这完全独立于Claude 3.7 Sonnet 中引入的新“思考”机制。

[[99.附件/Img/80f98ae5dc670437b0f455f3ad5106e3_MD5.jpg\|Open: 45a96e1a7f8dff980ccd35db120b72e6_MD5.jpg]]
![80f98ae5dc670437b0f455f3ad5106e3_MD5](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/80f98ae5dc670437b0f455f3ad5106e3_MD5.jpg?cd-oss-obs)

  

Anthropic 的基准测试显示，启用此工具后，性能得到了显著提升。我完全相信其他供应商的模型也能从同样的技巧中受益。

[[99.附件/Img/5861ba8522a051f06d468d660c4171f5_MD5.jpg\|Open: 5552f58874cb19a09b5567891d11c343_MD5.jpg]]
![5861ba8522a051f06d468d660c4171f5_MD5](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/5861ba8522a051f06d468d660c4171f5_MD5.jpg?cd-oss-obs)

  

## 何时使用“思考”工具

  

根据这些评估结果，我们确定了 Claude 从“思考”工具中受益最多的特定场景：

*   **工具输出分析。Claude**在采取行动之前需要仔细处理先前工具调用的输出，并且可能需要在其方法中回溯；
    
*    **策略密集型环境**。当 Claude 需要遵循详细的指导方针并验证合规性时；

*   **顺序决策**。当每个动作都建立在前一个动作的基础上时，错误的代价是昂贵的（通常在多步骤领域中发现）。

## 实施最佳实践

为了充分利用 Claude 的“思考”工具，我们根据 τ-bench 实验推荐以下实施实践。

### 1. 使用特定领域的例子进行策略性提示

最有效的方法是提供关于何时以及如何使用“思考”工具的明确说明，例如用于 τ-bench 航空公司领域的工具。提供针对您的特定用例量身定制的示例可显著提高模型使用“思考”工具的效率：

*   推理过程中预期的详细程度；
*   如何将复杂的指令分解为可操作的步骤；
*   用于处理常见场景的决策树；以及
*   如何检查是否已收集所有必要的信息。

###   

### 2. 在系统提示中放置复杂的引导

我们发现，当它们很长或很复杂时，在系统提示中包含有关“思考”工具的说明比将它们放在工具描述本身中更有效。这种方法提供了更广泛的背景，并有助于模型更好地将思考过程整合到其整体行为中。

  

## 何时不使用“思考”工具

尽管“思考”工具可以提供实质性的改进，但它并不适用于所有工具使用案例，并且确实会增加提示长度和输出标记。具体来说，我们发现“思考”工具在以下用例中没有提供任何改进：

*   **非连续的工具调用**。如果 Claude 只需要进行一次工具调用或多次并行调用即可完成一项任务，那么添加“思考”不太可能带来任何改进。
*   **简单的指令遵循**。当 Claude 需要遵守的约束并不多，并且其默认行为足够好时，额外的“思考”不太可能带来好处。

  

## 入门

“思考”工具是 Claude 实现的一个直接补充，只需几个步骤即可带来有意义的改进：

*   **使用代理工具使用场景进行测试。**从具有挑战性的用例开始，这些用例是 Claude 目前在长工具调用链中努力应对策略合规性或复杂推理的用例。
*   **添加工具定义**。实现针对您的领域定制的“思考”工具。它需要最少的代码，但可以实现更结构化的推理。还可以考虑在系统提示中包含有关何时以及如何使用该工具的说明，以及与您的领域相关的示例。
*   **监控和改进**。观察 Claude 在实践中如何使用该工具，并调整提示以鼓励更有效的思维模式。

  

最好的部分是，添加此工具对性能结果的影响很小。除非 Claude 决定使用它，否则它不会改变外部行为，也不会干扰您现有的工具或工作流程。

## 结论

  

我们的研究表明，“思考”工具可以显著提高 Claude 3.7 Sonnet 在执行需要在长链工具调用中遵守政策和推理的复杂任务时的性能。 “思考”并不是一个万能的解决方案，但它为正确的用例提供了实质性的好处，而且实现复杂性极低。

我们期待看到您如何使用“思考”工具与 Claude 一起构建更强大、更可靠、更透明的 AI 系统。

  

 [[99.附件/Img/8d71932c871afd9472cf2409e4d1a1e2_MD5.webp\|Open: 99a62ee457a6229cb447cac785d461e7_MD5.webp]]
![8d71932c871afd9472cf2409e4d1a1e2_MD5](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/8d71932c871afd9472cf2409e4d1a1e2_MD5.webp?cd-oss-obs)

  

参考链接：https://www.anthropic.com/engineering/claude-think-tool

  
 

  
 

 [[99.附件/Img/a5d1496a6a4e9c3da7dd4522783088d9_MD5.webp\|Open: 80209accda856a6189d7582ff3b6e36b_MD5.webp]]
![a5d1496a6a4e9c3da7dd4522783088d9_MD5](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/a5d1496a6a4e9c3da7dd4522783088d9_MD5.webp?cd-oss-obs)

  

[[99.附件/Img/7b3ba5f0b036165a87904fd6c34493bc_MD5.gif\|Open: 73dea04ce34be473cb5254ccceac6572_MD5.gif]]
![7b3ba5f0b036165a87904fd6c34493bc_MD5](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/7b3ba5f0b036165a87904fd6c34493bc_MD5.gif?cd-oss-obs)

*   [分析DeepSeek推理模型的方法和策略](https://mp.weixin.qq.com/s?__biz= март
    
*   [DeepSeek R1 和 R1-Zero 训练步骤详解](https://mp.weixin.qq.com/s?__biz= март
    
*   [从Deepseek R1看推理模型Scaling Law的未来](https://mp.weixin.qq.com/s?__biz= март
    
*   [OpenAI O3论文“涌现”出自验证、自适应推理能力，竟获国际奥林匹克金牌](https://mp.weixin.qq.com/s?__biz= март
    
*   [Docker 的竞争飞跃：通过Container本地化一键运行LLM大模型](https://mp.weixin.qq.com/s?__biz= март
    
*   [如果模型即产品，那么很多AI公司都注定要失败](https://mp.weixin.qq.com/s?__biz= март
    
*   [AI Agent智能体自主性的摩尔定律，每7个月翻一番](https://mp.weixin.qq.com/s?__biz= март
    
*   [OpenAI被曝博士级AI智能体2万美元/月，有望取代大学教授](https://mp.weixin.qq.com/s?__biz= март
    
*   [Google发布Co-scientist：多智能体 AI系统，加速科学突破](https://mp.weixin.qq.com/s?__biz= март
    

[[99.附件/Img/d92e7c6684ec810f316ddb39ae1ab822_MD5.gif\|Open: d1e8c91d4405f78a1ba26eacec8154a2_MD5.gif]]
![d92e7c6684ec810f316ddb39ae1ab822_MD5](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/d92e7c6684ec810f316ddb39ae1ab822_MD5.gif?cd-oss-obs)

---
tag: AI决策,Anthropic,工具开发
---