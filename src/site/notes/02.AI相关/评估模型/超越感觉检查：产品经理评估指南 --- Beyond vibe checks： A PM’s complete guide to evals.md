---
{"dg-publish":true,"permalink":"/02.AI相关/评估模型/超越感觉检查：产品经理评估指南 --- Beyond vibe checks： A PM’s complete guide to evals/","title":"超越感觉检查产品经理评估指南 --- Beyond vibe checks:A PM’s complete guide to evals"}
---


Writing evals is quickly becoming a core skill for anyone building AI products (which will soon be everyone). Yet there’s very little specific advice on how to get good at it. Below you’ll find everything you need to understand wtf evals are, why they are so important, and how to master this emerging skill.  
撰写评估报告正迅速成为任何构建 AI 产品（很快将涉及所有人）的核心技能。然而，关于如何擅长这项技能的具体建议却非常少。以下是你需要了解的一切，包括评估报告是什么，为什么它们如此重要，以及如何掌握这项新兴技能。

Aman Khan runs a popular [course on evals developed with Andrew Ng](https://www.deeplearning.ai/short-courses/evaluating-ai-agents/), is Director of Product at Arize AI (a leading AI company), and has been a product leader at Spotify, Cruise, Zipline, and Apple. He was also a [past podcast guest](https://www.youtube.com/watch?v=E_rNotqs--I) and is launching his first [Maven course on AI product management](https://maven.com/aman-khan/thriving-as-an-ai-pm) this spring. If you’re looking to get more hands-on, definitely check out Aman’s upcoming free 30-minute lightning lesson on April 18th: [Mastering Evals as an AI Product Manager](https://maven.com/p/e55ece/mastering-evals-as-an-ai-product-manager?utm_campaign=MzgyNTQ0&utm_medium=ll_share_link&utm_source=instructor). You can find Aman on [X](https://x.com/_amankhan), [LinkedIn](https://www.linkedin.com/in/amanberkeley/), and [Substack](http://aiproductplaybook.com/).  
阿曼·汗开设了一门与 Andrew Ng 共同开发的关于评估的流行课程，是 Arize AI（一家领先的 AI 公司）的产品总监，曾在 Spotify、Cruise、Zipline 和苹果公司担任产品领导。他还曾是播客的嘉宾，并将在今年春天推出他的第一门关于 AI 产品管理的 Maven 课程。如果你想要更深入地了解，绝对要看看阿曼即将在 4 月 18 日推出的免费 30 分钟闪电课程：作为 AI 产品经理掌握评估。你可以在 X、LinkedIn 和 Substack 上找到阿曼。

Now, on to the post. . .  
现在，让我们进入正文……



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164841060.jpeg?cd-oss-obs)





After years of building AI products, I’ve noticed something surprising: every PM building with generative AI obsesses over crafting better prompts and using the latest LLM, yet almost no one masters the hidden lever behind every exceptional AI product: evaluations. Evals are the only way you can break down each step in the system and measure _specifically_ what impact an individual change might have on a product, giving you the data and confidence to take the right next step. Prompts may make headlines, but evals quietly decide whether your product thrives or dies. In fact, I’d argue that the ability to write great evals isn’t just important—it’s rapidly becoming the defining skill for AI PMs in 2025 and beyond.  
经过多年构建 AI 产品，我发现了一个惊人的现象：每个使用生成式 AI 构建产品的产品经理都痴迷于制作更好的提示词和使用最新的LLM，然而，几乎没有人掌握每个卓越 AI 产品背后的隐藏杠杆：评估。评估是唯一能够分解系统每一步并具体衡量单个变化可能对产品产生的影响的方法，为你提供数据和信心，让你能够采取正确的下一步。提示词可能会成为头条新闻，但评估却默默地决定了你的产品是繁荣还是死亡。事实上，我认为编写出色评估的能力不仅很重要——它正在迅速成为 2025 年及以后 AI 产品经理的标志性技能。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164842818.jpeg?cd-oss-obs)



If you’re not actively building this muscle, you’re likely missing your biggest opportunity for impact-building AI products.  
如果你不积极锻炼这块肌肉，你可能会错过构建影响最大的 AI 产品的最大机会。

Let me show you why.  
让我来告诉你原因。

Let’s imagine you’re building a trip-planning AI agent for a travel-booking website. The idea: your users type in natural language requests like “_I want a relaxing weekend getaway near San Francisco for under $1,000_,” and the agent goes off to research the best flights, hotels, and local experiences tailored to their preferences.  
让我们想象你正在为一家旅行预订网站构建一个行程规划人工智能代理。想法是：你的用户输入自然语言请求，例如“我想在旧金山附近花费不到 1000 美元的放松周末度假”，然后代理开始研究最适合他们偏好的最佳航班、酒店和当地体验。

To build this agent, you’d typically start by selecting an LLM (e.g. GPT-4o, Claude, or Gemini) and then design prompts (specific instructions) that guide the LLM to interpret user requests and respond appropriately. Your first impulse might be to feed user questions into the LLM directly to get out responses one by one, as with a simple chatbot, before adding capabilities to turn it into a true “agent.” When you extend your LLM-plus-prompt by giving it access to external tools—like flight APIs, hotel databases, or mapping services—you allow it to execute tasks, retrieve information, and respond dynamically to user requests. At that point, your simple LLM-plus-prompt evolves into an AI agent, capable of handling complex, multi-step interactions with your users. For internal testing, you might experiment with common scenarios and manually verify that the outputs make sense.  
构建这个代理，你通常会先选择一个LLM（例如 GPT-4o、Claude 或 Gemini），然后设计提示（具体指令）来引导LLM解释用户请求并适当地响应。你的第一个冲动可能是直接将用户问题输入到LLM中，逐个获取响应，就像简单的聊天机器人一样，然后再添加功能将其变成真正的“代理”。当你通过提供对外部工具的访问——如航班 API、酒店数据库或地图服务——来扩展你的LLM-plus-prompt 时，你允许它执行任务、检索信息并动态响应用户请求。到那时，你的简单LLM-plus-prompt 就演变成了一个 AI 代理，能够处理与用户复杂、多步骤的交互。对于内部测试，你可能会对常见场景进行实验，并手动验证输出是否合理。

Everything seems great—until you launch. Suddenly, frustrated customers flood support because the agent booked them flights to San Diego instead of San Francisco. Yikes. How did this happen? And more importantly, how could you have caught and prevented this error earlier?  
一切看起来都很完美——直到你推出产品。突然，沮丧的客户涌入支持部门，因为代理商为他们预订了圣地亚哥的航班而不是旧金山。哎呀。这是怎么发生的？更重要的是，你如何能更早地捕捉并预防这个错误？

This is where evals come in.  
这是评估介入的地方。

Evals are how you measure the quality and effectiveness of your AI system. They act like regression tests or benchmarks, clearly defining what “good” actually looks like for your AI product beyond the kind of simple latency or pass/fail checks you’d usually use for software.  
评估是衡量您 AI 系统质量和效果的方法。它们类似于回归测试或基准测试，明确界定了您的 AI 产品“良好”的标准，而不仅仅是通常用于软件的简单延迟或通过/失败检查。

Evaluating AI systems is less like traditional software testing and more like giving someone a driving test:  
评估人工智能系统更像是给某人进行驾驶考试，而不是像传统的软件测试那样

*   **Awareness:** Can it correctly interpret signals and react appropriately to changing conditions?  
    意识：它能否正确解读信号并适当地对变化条件做出反应？
    
*   **Decision-making:** Does it reliably make the correct choices, even in unpredictable situations?  
    决策：它是否在不可预测的情况下也能可靠地做出正确的选择？
    
*   **Safety:** Can it consistently follow directions and arrive safely at the intended destination, without going off the rails?  
    安全：它能否始终如一地遵循指示，安全到达预定目的地，而不会出轨？
    

Just as you’d never let someone drive without passing their test, you shouldn’t let an AI product launch without passing thoughtful, intentional evals.  
就像你不会让一个没有通过考试的人开车一样，你不应该让一个 AI 产品在没有经过深思熟虑、有意的评估的情况下发布。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164844027.png?cd-oss-obs)


Evals are analogous to unit testing in some ways, with important differences. Traditional software unit testing is like checking if a train stays on its tracks: straightforward, deterministic, clear pass/fail scenarios. Evals for LLM-based systems, on the other hand, can feel more like driving a car through a busy city. The environment is variable, and the system is non-deterministic. Unlike in traditional software testing, when you give the same prompt to an LLM multiple times, you might see slightly different responses—just like how drivers can behave differently in city traffic. With evals, you’re often dealing with more qualitative or open-ended metrics—like the relevance or coherence of the output—that might not fit neatly into a strict pass/fail testing model.  
评估在某些方面类似于单元测试，但也有重要区别。传统的软件单元测试就像检查火车是否在轨道上行驶：简单直接、确定性强、有明确的通过/失败场景。而基于LLM的系统的评估，另一方面可能更像是在繁忙的城市中驾驶汽车。环境是变化的，系统是非确定性的。与传统的软件测试不同，当你多次给出相同的提示时，你可能会看到略有不同的响应——就像驾驶员在城市交通中可能会有不同的行为。在评估中，你通常要处理更多定性或开放式指标——如输出的相关性或连贯性——这些可能无法完美地适应严格的通过/失败测试模型。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164845422.jpeg?cd-oss-obs)



An example eval prompt to detect frustrated users  
一个用于检测沮丧用户的评估提示示例

1.  **Human evals:** These are human feedback loops you can design into your product (i.e. showing a thumbs-up/thumbs-down or a comment box next to an LLM response, for your user to provide feedback). You can also have human labelers (i.e. subject-matter experts) provide their labels and feedback, and use this for aligning the application with human preferences via prompt optimization or fine-tuning a model (aka [reinforcement learning from human feedback](https://en.wikipedia.org/wiki/Reinforcement_learning_from_human_feedback), or RLHF).  
    人工评估：这些是可以设计到您产品中的人为反馈循环（例如，在LLM回复旁边显示点赞/踩或评论框，以便用户提供反馈）。您还可以让人工标注员（即领域专家）提供他们的标签和反馈，并使用这些信息通过提示优化或微调模型（即从人为反馈中强化学习，或 RLHF）来使应用程序与人类偏好保持一致。
    
    *   **Pro:** Directly tied to the end user.  
        优点：直接与最终用户挂钩。
        
    *   **Cons:** Very sparse (most people don’t hit that thumbs-up/thumbs-down), not a strong signal (what does a thumbs-up or -down mean?), and costly (if you want to hire human labelers).  
        缺点：非常稀疏（大多数人不会点赞/点踩），不是一个强烈的信号（点赞或点踩意味着什么？），而且成本高昂（如果你想雇佣人工标注员）。
        
2.  **Code-based evals:** Utilizing checks on API calls or code generation (i.e. was the generated code “valid” and can it run?).  
    基于代码的评估：利用对 API 调用或代码生成的检查（例如，生成的代码“有效”且能否运行？）。
    
    *   **Pros:** Cheap and fast to write this eval.  
        优点：编写这份评估既便宜又快。
        
    *   **Cons:** Not a strong signal; great for code-based LLM generation but not for more nuanced responses or evaluations.  
        缺点：信号不强；非常适合基于代码的LLM生成，但不适用于更细腻的回应或评估。
        
3.  **LLM-based evals:** This technique utilizes an external LLM system (i.e. a “judge” LLM), with a prompt like the one above, to grade the output of the agent system. LLM-based evals allow you to generate classification labels in an automated way that resembles human-labeled data—without needing to have users or subject-matter experts label all of your data.  
    基于LLM的评估：这种技术利用外部LLM系统（即“评委”LLM），使用上述类似的提示，来评估代理系统的输出。基于LLM的评估允许您以类似于人工标注数据的方式自动生成分类标签——无需让用户或领域专家对您所有数据进行标注。
    
    *   **Pro:** Scalable (it’s like a human label but much cheaper) and natural language, so the PM can write prompts. You can also get the LLM to generate an explanation.  
        优点：可扩展（就像人工标签但成本更低）且支持自然语言，因此项目经理可以编写提示。您还可以使用LLM生成解释。
        
    *   **Con:** Need to create LLM-as-a-judge (with some small amount of data to start).  
        缺点：需要创建LLM-as-a-judge（初始时需要一些少量数据）。
        

Importantly, LLM-based evals are natural language prompts themselves. That means that just as building intuition for your AI agent or LLM-based system requires prompting, evaluating that same system also requires you to describe what you want to catch.  
重要的是，基于LLM的评估本身就是自然语言提示。这意味着，就像建立对您的 AI 代理或LLM-基于的系统进行直觉需要提示一样，评估该系统也需要您描述您想要捕捉的内容。

Let’s take the example from earlier: a trip-planning agent. In that system, there are a lot of things that can go wrong, and you can choose the right eval approach for each step in the system.  
让我们以前面的例子为例：一个行程规划代理。在该系统中，有很多事情可能会出错，并且你可以为系统中的每个步骤选择合适的评估方法。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164847027.jpeg?cd-oss-obs)


As a user, you want evals that are (1) specific, (2) battle-tested, and (3) test for specific areas of success. A few examples of common areas evals might look at are:  
作为用户，您希望评估结果是（1）具体的，（2）经过实战检验的，以及（3）针对特定成功领域的。评估可能关注的常见领域包括：

1.  **[Hallucination](https://docs.arize.com/phoenix/evaluation/how-to-evals/running-pre-tested-evals/hallucinations):** Is the agent accurately using the provided context, or is it making things up?  
    幻觉：代理是否准确使用提供的上下文，还是它在编造东西？
    
    1.  Useful for: When you are providing documents (e.g. PDFs) for the agent to perform reasoning on top of  
        适用于：当您为代理提供文档（例如 PDF 文件）以进行推理时
        

2.  **[Toxicity/tone](https://docs.arize.com/phoenix/evaluation/how-to-evals/running-pre-tested-evals/toxicity):** Is the agent outputting harmful or undesirable language?  
    毒性/语气：代理是否输出有害或不希望的语言？
    
    1.  Useful for: End-user applications, to determine if users may be trying to exploit the system or the LLM is responding inappropriately  
        适用于：终端用户应用，以确定用户是否试图利用系统或LLM是否响应不当
        

3.  **[Overall correctness](https://docs.arize.com/phoenix/evaluation/how-to-evals/running-pre-tested-evals/q-and-a-on-retrieved-data):** How well is the system performing at its primary goal?  
    总体正确性：系统在其主要目标上的表现如何？
    
    1.  Useful for: End-to-end effectiveness; for example, question-answering accuracy—how often is the agent actually correct at answering a question provided by a user?  
        适用于：端到端有效性；例如，问答准确性——代理人在回答用户提出的问题时实际上有多正确？
        

Other common areas for eval would be:  
其他常见的评估领域包括：

*   [Code generation 代码生成](https://docs.arize.com/phoenix/evaluation/how-to-evals/running-pre-tested-evals/code-generation-eval)
    
*   [Summarization quality 摘要质量](https://docs.arize.com/phoenix/evaluation/how-to-evals/running-pre-tested-evals/summarization-eval)
    
*   [Retrieval relevance 检索相关性](https://docs.arize.com/phoenix/evaluation/how-to-evals/running-pre-tested-evals/retrieval-rag-relevance)
    

Phoenix (open source) maintains a repository of off-the-shelf evaluators [here](https://docs.arize.com/phoenix/evaluation/how-to-evals/running-pre-tested-evals).* Ragas (open source) also maintains a repository of RAG-specific evaluators [here](https://docs.ragas.io/en/latest/concepts/metrics/available_metrics/).  
凤凰（开源）在此处维护了一个现成评估器的存储库。* 拉加（开源）也在此处维护了一个针对 RAG 的特定评估器的存储库。

_*Full disclosure: I’m a contributor to Phoenix, which is open source (there are other tools out there too for evals, like Ragas). I’d recommend people get started with something free/open source, which won’t hold their data hostage, to run evals! Many of the tools in the space are closed source. You never have to talk to Arize/our team to use Phoenix for evals.  
**完全披露：我是 Phoenix 的贡献者，它是开源的（还有其他用于评估的工具，如 Ragas）。我建议人们从免费/开源的软件开始，这样就不会让他们的数据成为人质，以便进行评估！该领域中的许多工具都是闭源的。您不必与 Arize/我们的团队交谈即可使用 Phoenix 进行评估。**_

Each great LLM eval contains four distinct parts:  
每个优秀的LLM评估包含四个不同的部分：

*   **Part 1:** **Setting the role.** You need to provide the judge-LLM a role (e.g. “you are examining written text”) so that the system is primed for the task.  
    第一部分：设定角色。您需要为法官LLM分配一个角色（例如：“你正在检查书面文本”），以便系统为任务做好准备。
    
*   **Part 2: Providing the context.** This is the data you will actually be sending to the LLM to grade. This will come from your application (i.e. the message chain, or the message generated from the agent LLM).  
    第二部分：提供背景信息。这是您将实际发送到LLM进行评分的数据。这些数据将来自您的应用（即消息链，或由代理LLM生成的消息）。
    
*   **Part 3: Providing the goal.** Clearly articulating what you want your judge-LLM to measure isn’t just a step in the process; it’s the difference between a mediocre AI and one that consistently delights users. Building these writing skills requires practice and attention. You need to clearly define what success and failure look like to the judge-LLM, translating nuanced user expectations into precise criteria your LLM judge can follow. What do you want the judge-LLM to measure? How would you articulate what a “good” or “bad” outcome is?  
    第三部分：设定目标。明确地阐述你希望你的评判者LLM要衡量的内容，这不仅是一个步骤，而且是平庸的人工智能和能够持续让用户感到愉悦的人工智能之间的区别。培养这些写作技能需要练习和关注。你需要清楚地定义对评判者LLM来说成功和失败是什么样子，将细微的用户期望转化为你的LLM评判者可以遵循的精确标准。你希望评判者LLM衡量什么？你将如何阐述“好”或“坏”的结果是什么？
    
*   **Part 4: Defining the terminology and label.** Toxicity, for example, can mean different things in different contexts. You want to be specific here so the judge-LLM is “grounded” in the terminology you care about.  
    第四部分：定义术语和标签。例如，“毒性”在不同的语境中可能有不同的含义。你在这里需要具体明确，以便使法官LLM对所关心的术语“扎根”。
    

Here’s a concrete example. Below is an example eval for toxicity/tone for your trip planner agent.  
这里有一个具体的例子。以下是为您的行程规划代理提供的关于毒性/语调的评估示例。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164848369.jpeg?cd-oss-obs)



Evals aren’t just a one-time check. Gathering data to evaluate, writing evals, analyzing the results, and integrating feedback from evals is an iterative workflow from initial development through continuous improvement after launch. Let’s use the trip planning agent example from earlier to illustrate the process for building an eval from scratch.  
评估不仅仅是单次检查。收集评估数据、撰写评估报告、分析结果以及整合评估反馈是一个从初始开发到发布后持续改进的迭代工作流程。让我们以前面提到的行程规划代理为例，来说明从头开始构建评估的过程。

Let’s say you’ve launched your trip planning agent and are getting feedback from users. Here’s how you can use that feedback to build out a dataset for evaluation:  
假设你已经发布了你的旅行规划代理，并从用户那里获得了反馈。以下是如何利用这些反馈来构建用于评估的数据集的方法：

1.  **Gather real user interactions:** [Capture real examples](https://hamel.dev/blog/posts/field-guide/index.html#measure-alignment-between-automated-evals-and-human-judgment) of how users engage with your app. You can do this via direct feedback, analytics, or manual inspection of interactions within your application.  
    收集真实用户互动：捕捉用户如何与您的应用互动的真实示例。您可以通过直接反馈、分析或手动检查应用内的互动来实现这一点。
    
    1.  For example: Capture human feedback (thumbs-up/down) from your users interacting with the agent. Try to build out a dataset representative of real-world examples that have human feedback.  
        例如：捕捉用户与代理互动时的人类反馈（点赞/踩）。尝试构建一个具有真实世界示例的人类反馈的数据集。
        
    2.  If you don’t collect feedback from your application, you can also take a sample of data and have subject-matter experts (or even PMs!) label the data.  
        如果您不收集应用程序的反馈，您也可以抽取数据样本，并让领域专家（甚至产品经理！）对数据进行标注。
        

2.  **Document edge cases:** Identify the unusual or unexpected ways users interact with your AI, as well as any atypical responses from the agent.  
    文档边缘情况：识别用户与您的 AI 互动的不寻常或意外方式，以及代理的任何非典型响应。
    
    1.  As you inspect specific examples, you might want a dataset that is balanced across topics. For example:  
        在检查具体示例时，您可能需要一个在各个主题上平衡的数据集。例如：
        
        *   Help booking a hotel 帮助预订酒店
            
        *   Help booking a flight 帮助预订航班
            
        *   Asking for support 请求支持
            
        *   Asking for trip planning advice  
            请求行程规划建议
            

3.  **Build a representative dataset:** Collect these interactions into a structured dataset, ideally annotated with “ground truth” (human labels) for accuracy. I’d recommend having between 10 and 100 examples with human labels to start with, as a rule of thumb, to use as ground truth for evaluation. Start simple—spreadsheets are great initially—but eventually consider open source tools like [Phoenix](https://phoenix.arize.com/) for logging and managing data efficiently. I’m biased—I helped build Phoenix, but only because I was struggling with this myself. My recommendation would be to use a tool that is open source and easy to use for logging your LLM application data and prompts when getting started.  
    构建代表性数据集：将这些交互收集到一个结构化数据集中，理想情况下用“真实标签”（人工标签）进行标注以提高准确性。我建议一开始使用 10 到 100 个带有真实标签的示例作为评估的真实标签，这是一个经验法则。从简单开始——电子表格最初很棒——但最终可以考虑使用像 Phoenix 这样的开源工具来高效地记录和管理数据。我有偏见——我帮助构建了 Phoenix，但这仅仅是因为我自己在处理这个问题。我的建议是使用一个开源且易于使用的工具来记录您的LLM应用程序数据，并在开始时提供提示。
    

Now that you have a dataset consisting of real-world examples, you can start writing an eval to measure a specific metric, and test the eval against the dataset.  
现在您已经拥有了一个包含真实世界示例的数据集，您可以开始编写一个评估来衡量特定指标，并将评估与数据集进行测试。

For example: You might be trying to see if your agent ever answers in a tone that reads as unfriendly to the end user. Even if a user of your platform gives negative feedback, you may want your agent to respond in a friendly tone.  
例如：你可能想看看你的代理是否曾以对用户不友好的语气回答。即使你的平台用户给出负面反馈，你可能也希望你的代理以友好的语气回应。

1.  **Write initial eval prompts:** Clearly specify the scenarios you’re testing for, following the four-part formula above.  
    编写初始评估提示：明确指定你正在测试的场景，遵循上述四部分公式。
    
    1.  For example, the initial eval might look something like:  
        例如，初步评估可能看起来像这样：
        
        *   **Setting the role:** “You are a judge, evaluating written text.”  
            设置角色：“你是一位评判员，正在评估书面文本。”
            
        *   **Providing the context:** “Here is the text : {text}” → In this case, {text} is a variable, where you will be providing the “LLM agent answer” in the [variable of the prompt](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/prompt-templates-and-variables).  
            提供上下文：“这里是对应的文本：{text}”→在这种情况下，{text}是一个变量，您将在提示的变量中提供“LLM 代理回答”。
            
        *   **Providing the goal:** “Determine whether the LLM agent response was friendly.”  
            提供目标：“确定LLM代理响应是否友好。”
            
        *   **Defining the terminology and label:** “‘Friendly’ would be defined as using an exclamation point in response and generally being helpful. The response should never have a negative tone.”  
            定义术语和标签：“‘友好’定义为在回复中使用感叹号，并且通常有帮助。回复不应带有负面语气。”
            

2.  **Run evals against your dataset:** You will run the eval by sending the eval prompt plus LLM agent answer variable to an LLM, and get back a label for each row in your dataset.  
    运行评估您的数据集：您将通过发送评估提示符加上LLM代理回答变量到LLM来运行评估，并为您的数据集中的每一行获取一个标签。
    
    1.  Aim for at least 90% accuracy compared with your human-labeled ground truth.  
        以至少 90%的准确率与您的人类标注的基准真值进行比较。
        

3.  **Identify patterns in failures:** Where does the eval fall short? Iterate on your prompt.  
    识别故障模式：评估哪里做得不够好？迭代你的提示。
    
    1.  In the example below: The eval disagrees with the human label in the last example. Our prompt above requires an exclamation point for an LLM agent response to be considered friendly. Maybe that requirement is too strict?  
        在下面的例子中：评估结果与最后一个例子中的人类标签不一致。我们上面的提示要求使用感叹号，以便将LLM代理的响应视为友好。也许这个要求太严格了？
        



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164850311.png?cd-oss-obs)



1.  **Refine eval prompts:** Continuously adjust your prompts based on results until performance meets your standards.  
    优化评估提示：根据结果持续调整您的提示，直到性能达到您的标准。
    
    1.  Tip: You can add a few examples to your prompt of “good” and “bad” evals to ground the LLM response, as a form of “[few-shot prompting](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/multishot-prompting).”  
        提示：您可以在“良好”和“不良”评估的提示中添加几个示例，以使LLM的回复更有依据，这可以视为一种“少量样本提示”。
        
2.  **Expand your dataset:** Regularly add new examples and edge cases to test whether your eval prompts can generalize effectively.  
    扩展您的数据集：定期添加新的示例和边缘情况，以测试您的评估提示是否能够有效泛化。
    
3.  **Iterate on your agent prompt:** Evals help you test your product when you make changes to the underlying AI system—in some ways, they are the final boss when A/B testing prompts for your AI system. For example, when you make a change to an agent (e.g. changing the model from GPT-4o to Claude 3.7 Sonnet), you can rerun the dataset of questions you collected _through your updated agent_ and evaluate the new output (i.e. Claude 3.7) with your eval agent. The goal would be to improve on your initial agent (GPT-4o) eval scores, giving you a benchmark you can use for continual improvement.  
    迭代您的代理提示：评估可以帮助您在更改底层 AI 系统时测试您的产品——在某些方面，它们是您 AI 系统 A/B 测试提示的最终大 Boss。例如，当您更改代理（例如，将模型从 GPT-4o 更改为 Claude 3.7 Sonnet）时，您可以重新运行您通过更新的代理收集的问题数据集，并使用您的评估代理评估新的输出（即 Claude 3.7）。目标将是提高您最初代理（GPT-4o）的评估分数，为您提供一个可以用于持续改进的基准。
    



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164852137.jpeg?cd-oss-obs)





1.  **Continuous evaluation:** Set up evals to run automatically on live user interactions.  
    持续评估：设置评估以自动运行在实时用户交互上。
    
    *   For example: You can continuously run the “friendly” eval on all your incoming requests and agent responses, to get a score over time. This can help you answer questions such as “Are your users getting more frustrated over time?” or “Are the changes we are making to our system impacting how friendly our LLM is?”  
        例如：您可以对所有传入请求和代理响应持续运行“友好”评估，以获取随时间变化的分数。这可以帮助您回答诸如“用户是否随着时间的推移而变得更加沮丧？”或“我们对系统所做的更改是否影响了我们的LLM的友好度？”等问题。
        
2.  **Compare eval results to actual user outcomes:** Look for discrepancies between eval results and real-world performance (i.e. human-labeled ground truth). Use these insights to enhance your eval framework and improve accuracy over time.  
    比较评估结果与实际用户结果：寻找评估结果与现实世界性能之间的差异（即人工标注的基准真实情况）。利用这些见解来完善您的评估框架并提高准确性。
    
3.  **Build actionable eval dashboards:** Evals can help communicate AI metrics to stakeholders across your team, and they can even be tied to business outcomes. They can serve as proxy leading metrics for changes you make to your system.  
    构建可操作的评估仪表板：评估可以帮助您向团队中的利益相关者传达 AI 指标，甚至可以将它们与业务成果联系起来。它们可以作为您对系统进行的更改的代理领先指标。
    



![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_lossy/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8ed7a15e-79ee-492e-a17e-7c1e8092a4d7_1232x720.gif)




_Running your evaluation continuously on production data  
持续在生产数据上运行评估_

1.  Making evals too complex too quickly can create “noisy” signals (and cause the team to lose trust in the approach). Focus on specific outputs rather than complex evaluations—you can always add sophistication later.  
    使评估过于复杂过快可能会产生“嘈杂”的信号（并导致团队对这种方法失去信任）。专注于具体的输出，而不是复杂的评估——你总是可以后来增加复杂性。
    
2.  Not testing for edge cases. Provide one or two specific examples of “good” and “bad” evals as part of your prompt—few-shot prompting—for increased eval performance. This helps ground the judge-LLM in what is considered good or bad.  
    不测试边缘情况。在提示中提供一到两个“好”和“坏”评估的具体例子——作为少样本提示，以提高评估性能。这有助于让评判者LLM了解何为好或坏。
    
3.  Forgetting to validate eval results against real user feedback. Remember that you’re not just testing code, you’re validating if your AI can truly solve user problems.  
    忘记将评估结果与真实用户反馈进行验证。记住，你不仅仅是测试代码，而是在验证你的 AI 是否真正能够解决用户问题。
    

Writing good evals forces you into the shoes of your user—they are how you catch “bad” scenarios and know what to improve on.  
撰写良好的评估迫使你站在用户的角度——它们是你捕捉“不良”场景并了解需要改进之处的方式。

Now that you understand the fundamentals, here’s exactly how to start with evals in your own product:  
现在你已经了解了基础知识，以下是如何在您的产品中开始进行评估的详细步骤：

1.  **Pick one critical feature** of your AI product to evaluate. A common starting point is “hallucination detection” for a chatbot or agent that relies on documents or context you provide it with to answer questions. Try to tackle evaluating a well-defined component in your system before evaluating deeply internal logic.  
    选择您 AI 产品的一个关键特性进行评估。一个常见的起点是为依赖于您提供的文档或上下文来回答问题的聊天机器人或代理进行“幻觉检测”。在评估深层内部逻辑之前，尽量先评估系统中定义良好的组件。
    
2.  **Write a simple eval** checking whether the LLM output correctly references provided content or if it invents (hallucinates) information.  
    编写一个简单的评估，检查LLM输出是否正确引用了提供的内容，或者是否发明（虚构）了信息。
    
3.  **Run your eval** on 5 to 10 representative examples from real interactions that you have collected or created.  
    运行您的评估，基于您收集或创建的 5 到 10 个具有代表性的真实互动示例。
    
4.  **Review the results and iterate**, refining the eval prompt until accuracy improves.  
    审查结果并迭代，直到准确性提高，不断优化评估提示。
    

For a detailed example of how to build a hallucination eval, check out our guide [here](https://arize.com/llm-evaluation), as well as our hands-on course [on Evaluating AI Agents](https://www.deeplearning.ai/short-courses/evaluating-ai-agents/).  
关于如何构建幻觉评估的详细示例，请参阅我们在此处的指南，以及我们关于评估 AI 代理的实操课程。

As AI products become more complex, the ability to write good evals will become increasingly crucial. Evals are not just about catching bugs; they help ensure that your AI system consistently delivers value and delights your users! Evals are a critical step in going from prototype to production with generative AI.  
随着人工智能产品变得越来越复杂，编写良好评估的能力将变得越来越关键。评估不仅仅是捕捉错误；它们有助于确保您的 AI 系统持续提供价值并让用户感到满意！评估是使用生成式 AI 从原型到生产的关键步骤。


![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250418164855179.png?cd-oss-obs)



I would love to hear from you: How are you currently evaluating your AI products? What challenges have you faced? Leave a comment👇  
我很乐意听听您的意见：您目前是如何评估您的 AI 产品的？您遇到了哪些挑战？留下评论👇

[Leave a comment 留下评论](https://www.lennysnewsletter.com/p/beyond-vibe-checks-a-pms-complete/comments)

1.  [A conversation with OpenAI’s CPO Kevin Weil, Anthropic’s CPO Mike Krieger, and Sarah Guo  
    与 OpenAI 首席产品官 Kevin Weil、Anthropic 首席产品官 Mike Krieger 和 Sarah Guo 的对话](https://www.youtube.com/watch?v=IxkvVZua28k&t=1s)
    
2.  Peter Yang + Aman: [The AI Skill That Will Define Your PM Career in 2025 | Aman Khan (Arize)](https://www.youtube.com/watch?v=u8lEDw7pOkE)  
    杨彼得 + Aman：定义您 2025 年产品经理生涯的 AI 技能 | Aman Khan（Arize）
    
3.  [DeepLearning.ai course on evals](http://deeplearning.ai/) with Andrew Ng  
    DeepLearning.ai 课程，由 Andrew Ng 教授的评估课程
    
4.  Prompt optimization guide: [https://arize.com/course/prompt-optimization/](https://arize.com/course/prompt-optimization/)  
    提示优化指南：https://arize.com/course/prompt-optimization/
    
5.  Arize eval hub (free!): [https://arize.com/llm-evaluation](https://arize.com/llm-evaluation)  
    Arize 评估中心（免费！）：https://arize.com/llm-evaluation
    
6.  Peter Yang + Scott White: [Exclusive: Inside the Best AI Model for Coding and Writing | Scott White (Anthropic)](https://www.youtube.com/watch?v=ynWgKSF0TZY)  
    杨彼得 + 斯科特·怀特：独家：揭秘最佳编码和写作 AI 模型 | 斯科特·怀特（Anthropic）
    

_Thank you, Aman! 谢谢，Aman！_

_Have a fulfilling and productive week 🙏  
祝您有一个充实而富有成效的一周 🙏_

**If you’re finding this newsletter valuable, share it with a friend, and consider subscribing if you haven’t already. There are [group discounts](https://www.lennysnewsletter.com/subscribe?group=true), [gift options](https://www.lennysnewsletter.com/subscribe?gift=true), and [referral bonuses](https://www.lennysnewsletter.com/leaderboard) available.  
如果您觉得这份通讯有价值，请与朋友分享，并考虑如果您还没有的话订阅。有团体折扣、礼品选项和推荐奖金可用。**

Sincerely, 诚挚地

Lenny 👋