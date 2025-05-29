---
{"dg-publish":true,"permalink":"/02.AI相关/运作原理/强迫模型自我争论，递归思考版 CoT 热度飙升！网友：这不就是大多数推理模型的套路吗？/","title":"强迫模型自我争论，递归思考版 CoT 热度飙升！网友：这不就是大多数推理模型的套路吗？"}
---

2025年05月12日 12:32@机器之心 2025年05月12日 12:32

机器之心报道

**编辑：杜伟**

> 递归思考 + 自我批判，CoRT 能带来 LLM 推理力的飞跃吗？

  

CoT（Chain-of-thought）大家都很熟悉了，通过模仿「人类解题思路」，进而大幅提升语言模型的推理能力。

  

这几天，一个名为 CoRT（Chain-of-Recursive-Thoughts）的概念火了！从名称上来看，它在 CoT 中加入了「递归思考」这一步骤。

  

具体来讲，CoRT 能让 AI 模型递归地思考它们的响应，生成替代性方案，并从中选择最佳的一个。

  

这就像赋予了 AI 自我质疑或反驳的能力，并一遍一遍地尝试。

  

通过将「结构化自我批判」和「递归思考模式」结合起来，提升语言模型的推理能力。

  

![图片编辑助手\SCR-20250512-jzan.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113053545.png?cd-oss-obs)

  

短短两周时间，CoRT 在 GitHub 的星标数已经快突破 2k 了。

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113054248.png?cd-oss-obs)

  

GitHub 地址：https://github.com/PhialsBasement/Chain-of-Recursive-Thoughts

  

从技术原理来讲，相较于传统的 CoT，CoRT 让语言模型不仅能分步骤思考，还能在思考过程中反复回头检查、修正，形成类似于人类的「反思性思维」或「内省」的推理路径。

  

然而，很多网友对 CoRT 的出现并没有感到太激动。CoRT 是让 LLM 更努力思考的不错技巧，但称不上什么新颖的 idea。它的工作原理就像一个加入了递归组件的元提示（meta-prompt）。

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113055010.png?cd-oss-obs)

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113055605.png?cd-oss-obs)

  

还有网友指出，这种方法在 2023 年的论文中《Improving Factuality and Reasoning in Language Models through Multiagent Debate》就出现了。

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113056051.png?cd-oss-obs)

  

有网友发出疑问：CoRT 不就是现在大多数 LLM 的思考模式吗？

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113056571.png?cd-oss-obs)

  

比如在 Cursor 中配置的 Gemini 2.5 Pro，它的 CoT 就是这样做的。模型会思考一分钟，并反驳自己的答案，直到找到最无力反驳的答案。

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113057034.png?cd-oss-obs)

  

再比如，CoRT 不就是 Qwen 和 R1 中的「but wait」模式吗？模型一直思考，并自我反驳，两者似乎没有什么不同。

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113057586.png?cd-oss-obs)

  

大家觉得，CoRT 是不是「新瓶装旧酒」呢？请在评论区留言。

  

项目介绍

  

根据项目介绍，CoRT 的诀窍在于以下四个方面：

  

*   自我评估；
    
*   有竞争力的替代生成方案；
    
*   迭代优化；
    
*   动态思维深度。
    

  

工作流程包括了以下四个步骤：

  

首先，AI 生成初始响应。

  

其次，AI 决定它需要多少轮「思考」。

  

接着，对于每一轮思考：

  

*   生成 3 个替代性响应；
    
*   评估所有响应；
    
*   选择最佳响应。
    

  

最后，最终响应就是这场 AI 大混战的幸存者。

  

Web 界面使用方式（仍处于早期开发阶段）

  

一，打开 start_recthink.bat

  

二，等待一会，让它安装依赖项

  

三，配置成功

  

如果你是运行在 linux 系统上，则依如下：

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113058010.png?cd-oss-obs)

  

打开一个新的壳层（shell）:

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113058419.png?cd-oss-obs)

  

效果怎么样呢？

  

作者使用 Mistral 3.1 24B 进行了测试，根据他的说法，CoRT 在编程任务中的表现从「meh」（一般般）升到了「holy crap」（碉堡了）。

  

我们来看一下示例，下图为 Mistral 3.1 24B+CoRT：

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113058862.png?cd-oss-obs)

  

下图为 Mistral 3.1 24B 无 CoRT：

  

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527113059257.png?cd-oss-obs)

  

从结果来看，使用 CoRT 前后，Tic-tac-toe（井字棋）游戏从基础的 CLI（命令行界面）变成了完全的 OOP（面向对象编程）。

  

参考链接：https://x.com/omarsar0/status/1917401353061818478

  

© THE END 

转载请联系本公众号获得授权

投稿或寻求报道：liyazhou@jiqizhixin.com