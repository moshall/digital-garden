---
{"dg-publish":true,"permalink":"/01.工作/观点/产品设计/如何重燃 Duolingo 的用户增长 - 作者：Jorge Mazal/","title":"如何重燃 Duolingo 的用户增长 - 作者：Jorge Mazal --- How Duolingo reignited user growth - by Jorge Mazal如何重燃 Duolingo 的用户增长 - 作者：Jorge Mazal"}
---

_👋 Hey, [Lenny](https://twitter.com/lennysan) here! Welcome to this month’s ✨ **free edition** ✨ of Lenny’s Newsletter. Each week I humbly tackle reader questions about product, growth, working with humans, and anything else that’s stressing you out about work.  
👋 嗨，我是 Lenny！欢迎来到本月的✨免费版✨Lenny 通讯。每周我都会谦逊地回答读者关于产品、增长、与人类合作以及任何让你在工作中感到压力的问题。_


I was at a small event a few months back where [Jorge Mazal](https://www.linkedin.com/in/jorgemazal/) (former CPO of Duolingo) shared the story behind Duolingo’s growth reaccelerating. I was captivated. I’ve never seen a growth story like this before—4.5x growth for a mature product, driven by a small handful of product changes, rooted in an innovative growth model, and explained in such actionable detail. I asked Jorge if he’d be willing to share (and expand on) the story with a broader audience, and I’m so happy he agreed. Many products already look to Duolingo for inspiration, and I suspect this story will only increase that trend. Enjoy!  
几个月前，我在一个小型活动中，听到了 Jorge Mazal（Duolingo 前首席产品官）分享 Duolingo 增长加速背后的故事。我被深深吸引。我以前从未见过这样的增长故事——一个成熟产品的增长达到 4.5 倍，由少数几个产品变化驱动，根植于创新的增长模式，并以如此可操作的方式解释。我询问 Jorge 是否愿意与更广泛的受众分享（并扩展）这个故事，我很高兴他同意了。许多产品已经将 Duolingo 作为灵感的来源，我相信这个故事只会增加这一趋势。享受吧！

_Follow Jorge for more on [LinkedIn](https://www.linkedin.com/in/jorgemazal/) and [Twitter](https://twitter.com/jorgemazal).  
关注 Jorge 在领英和 Twitter 上获取更多信息。_


![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123226811.jpeg?cd-oss-obs)


I joined Duolingo as the Head of Product in late 2017. Duolingo was already the most downloaded education app in the world, with hundreds of millions of users, fulfilling its mission to “develop the best education in the world and make it universally available.” However, user growth was slowing down. By mid-2018, daily active users (DAU) were growing at a single-digit rate year-over-year, which was troubling, given the explosive growth the company had seen in the past. This was a problem for a startup with investors anxious to see fast monetization growth.  
我于 2017 年底加入 Duolingo，担任产品总监。当时 Duolingo 已经是全球下载量最大的教育应用，拥有数亿用户，致力于“开发世界上最好的教育，使其普遍可用”。然而，用户增长正在放缓。到 2018 年中，日活跃用户（DAU）的年增长率仅为个位数，这在公司过去爆炸性增长的情况下令人担忧。这对一个投资者渴望看到快速货币化增长的初创公司来说是个问题。

In this post I’ll cover some of our early failures and then our first big wins that helped us turn around growth, including launching leaderboards, refocusing on push notifications, and optimizing the “streak” feature. These, together with several other efforts across Product and Marketing, helped us grow DAU by 4.5x over four years. Robust organic user growth supercharged Duolingo toward its 2021 IPO.  
在这篇文章中，我将介绍我们早期的失败和一些帮助我们扭转增长的第一大胜利，包括推出排行榜、重新关注推送通知和优化“连赢”功能。这些，加上产品与营销方面的其他一些努力，帮助我们过去四年将日活跃用户数增长了 4.5 倍。稳健的有机用户增长为 Duolingo 的 2021 年 IPO 注入了动力。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123228549.png?cd-oss-obs)




This article is an in-depth look into that journey. It is my hope that sharing this work will help others find their own growth breakthroughs faster.  
这篇文章是对这段旅程的深入探讨。我希望分享这项工作能帮助他人更快地找到自己的成长突破。

Our first attempt at reigniting growth was focused on improving retention, i.e. fixing our “leaky bucket” problem. We prioritized working on retention over new-user acquisition because all of our new-user acquisition was organic, and, at the time, we didn’t have an obvious lever to pull to supercharge that. Also, some of us had a suspicion that we could improve retention through gamification. There were two main reasons why this felt like the right approach to me. First, Duolingo had already implemented several gamification mechanics successfully, such as the progression system on the home screen, streaks, and an achievements system. And second, top digital games at the time had much higher retention rates than our product, which I took as evidence that we hadn’t yet reached the ceiling for gamification’s impact.   
我们第一次尝试重燃增长动力是专注于提高用户留存率，即解决我们的“漏斗”问题。我们优先考虑提高用户留存率而非新用户获取，因为我们的新用户获取都是有机的，当时我们没有明显的杠杆来加速这一点。此外，我们中的一些人怀疑通过游戏化可以提高用户留存率。有两个主要原因让我觉得这是正确的做法。首先，Duolingo 已经成功实施了几个游戏化机制，如主页上的进度系统、连赢和成就系统。其次，当时的顶级数字游戏比我们的产品有更高的用户留存率，这让我认为我们还没有达到游戏化影响的极限。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123230144.jpeg?cd-oss-obs)



_Duolingo’s gamified Home and Achievements pages  
多邻国游戏化的首页和成就页面_

Armed with a short presentation I co-created with our chief designer, we were able to get just enough buy-in from the rest of the executive team to create a new team, the Gamification Team. The team consisted of an engineering manager, an engineer, a designer, an APM, and me.  
凭借我与首席设计师共同制作的简短演示，我们成功获得了其他高管团队足够的支持，组建了一个新的团队——游戏化团队。该团队由一位工程经理、一位工程师、一位设计师、一位 APM 和我组成。

But there was one small issue: we had no idea which incremental gamification mechanics would work for Duolingo.  
但是有一个小问题：我们不知道哪些增量游戏化机制会对 Duolingo 有效。

Our team at the time was hooked on a game called Gardenscapes_,_ a mobile, match-3 puzzle game similar to Candy Crush_._ This mobile game became our first inspiration.   
我们的团队当时沉迷于一款名为《花园迷宫》的游戏，这是一款类似于《糖果传奇》的移动匹配 3 游戏。这款移动游戏成为了我们的第一个灵感来源。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123231719.jpeg?cd-oss-obs)



_A Gardenscapes match-3 puzzle level  
花园迷宫匹配 3 关卡_

As we looked at the different game mechanics in Gardenscapes, we didn’t really know what we were looking for—we just knew that Gardenscapes seemed stickier than Duolingo, and we saw several parallels. A three-minute Duolingo lesson felt similar to a Gardenscapes match-3 level, and Duolingo and Gardenscapes both used progress bars to provide visual feedback on how close the user was to completing the session. Gardenscapes, however, paired its progress bar with a moves counter, which Duolingo didn’t do. The moves counter allowed users only a finite number of moves to complete a level, which added a sense of scarcity and urgency to the gameplay. We decided to incorporate the counter mechanic into our product. We gave our users a finite number of chances to answer questions correctly before they had to start the lesson over.  
当我们审视《花园之间》的不同游戏机制时，我们并不真正知道我们在寻找什么——我们只知道《花园之间》似乎比 Duolingo 更具粘性，并且我们看到了几个相似之处。三分钟的 Duolingo 课程感觉与《花园之间》的匹配 3 关卡相似，而 Duolingo 和《花园之间》都使用了进度条来提供视觉反馈，告诉用户他们离完成会话有多近。《花园之间》然而，却将进度条与移动计数器配对，而 Duolingo 没有这样做。移动计数器只允许用户有限次数的移动来完成一个关卡，这为游戏增加了稀缺感和紧迫感。我们决定将计数器机制纳入我们的产品。我们给用户有限的机会在开始课程之前回答问题正确，如果答错，他们就必须重新开始课程。


![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123233348.jpeg?cd-oss-obs)



It took our team a couple of months of work to add the counter. With the release of the update, I expectantly waited for an unmitigated success. Depressingly, the result of all that effort was completely neutral. No change to our retention. No increase in DAU. We hardly got any user feedback at all. I was deflated. The greatest effect the initiative had was on our team. After the results came out, we quickly fell into dissension. Some wanted to continue iterating on the idea, while others wanted to pivot. The team almost immediately (and dramatically) disbanded, and the idea was abandoned. It was pretty awful. The one silver lining of this failure was that I learned a lot about the company culture and about how to improve my personal leadership style—though that’s for a different article.  
我们的团队花了几个月的时间添加计数器。随着更新的发布，我满怀期待地等待着一个无与伦比的成功。令人沮丧的是，所有这些努力的结果是完全中立的。我们的留存率没有变化。日活跃用户数没有增加。我们几乎没有收到任何用户反馈。我感到非常沮丧。这个倡议对我们团队的最大影响是，结果出来后，我们很快陷入了分歧。一些人想要继续迭代这个想法，而另一些人则想要转型。团队几乎立即（并且戏剧性地）解散了，这个想法也被放弃了。这真是太糟糕了。这个失败的唯一一线希望是我对公司文化和如何改进我的个人领导风格学到了很多——但这将是另一篇文章的内容。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123234368.png?cd-oss-obs)




_The first attempt to reignite growth through more gamification resulted in a dumpster fire.  
第一次尝试通过更多游戏化手段来重燃增长，结果却是一场灾难。_

Feeling burned after our gamification effort, we completely pivoted away from improving retention and put together a new product team focused on acquiring new users, called the Acquisition Team. At the time, Uber was doing well with user acquisition and had reputedly grown largely because of its referral program. Inspired by this, we created a referral program similar to Uber’s. The reward was a free month of our premium subscription, Super Duolingo (at the time, it was called Duolingo Plus). Seemed like a pretty good offer to us!   
在游戏化努力受挫后，我们完全转变方向，不再专注于提高用户留存率，而是组建了一个专注于获取新用户的新产品团队，称为获取团队。当时，优步在用户获取方面做得很好，据称其增长很大程度上得益于其推荐计划。受此启发，我们创建了一个类似于优步的推荐计划。奖励是免费一个月的我们高级订阅服务，超级多邻国（当时称为多邻国加）。对我们来说，这似乎是一个相当不错的提议！


![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123235795.jpeg?cd-oss-obs)


We implemented the feature and hoped our second attempt would be more successful. Instead, new users increased by only 3%. It was positive, but not the type of breakthrough we needed. Still, the team doubled down and pushed through, shipping iterations to the referral program and making some other bets, but no avail.  
我们实现了这个功能，并希望我们的第二次尝试会更有成效。然而，新用户仅增加了 3%。这是积极的，但并非我们需要的突破性进展。尽管如此，团队加大了力度，继续推进，向推荐计划推出迭代，并做出了一些其他尝试，但都没有成功。

While the team continued to iterate, it became clear to me that we had to find a different approach to tackle our growth problem.     
虽然团队继续迭代，但我意识到我们必须找到不同的方法来解决我们的增长问题。

The aftermath of these back-to-back failures in only a few months was a period of reflection for me about making better product bets.   
几个月内连续失败的后遗症让我反思如何做出更好的产品决策。

In hindsight, it became clear why the Gardenscapes moves counter was not a good fit for our product. When you are playing Gardenscapes, each move feels like a strategic decision, because you have to outmaneuver dynamic obstacles to find a path to victory. But strategic decision-making isn’t required to complete a Duolingo lesson—you mostly either know the answer to a question or you don’t. Because there wasn’t any strategy to it, the Duolingo moves counter was simply a boring, tacked-on nuisance. It was the wrong gamification mechanic to adopt into Duolingo. I realized that I had been so focused on the similarities between Gardenscapes and Duolingo that I had failed to account for the importance of the underlying differences.   
回顾过去，很明显为什么 Gardenscapes 移动计数器不适合我们的产品。当你玩 Gardenscapes 时，每一次移动都感觉像是一个战略决策，因为你必须绕过动态障碍物找到通往胜利的道路。但在 Duolingo 课程中完成战略决策并不是必需的——你大多数时候要么知道问题的答案，要么不知道。因为没有涉及任何策略，所以 Duolingo 移动计数器只是一个无聊的、附加的麻烦。这是不适合引入 Duolingo 的错误游戏化机制。我意识到，我过于关注 Gardenscapes 和 Duolingo 之间的相似之处，而没有考虑到它们之间潜在的不同的重要性。

It also did not take long to understand why our referral program did not produce Uber-like success. Referrals work for Uber because riders are paying for rides on a never-ending pay-as-you-go system. A free ride is a constant incentive. For Duolingo, we were trying to incentivize users by offering a free month of Super Duolingo. However, our best and most active users already had Super Duolingo, and we couldn’t give them a free month when they were already in a plan. This meant that our strategy, which needed to rely on our best users, actually excluded them.  
它也没有花费很长时间就明白了为什么我们的推荐计划没有产生类似 Uber 的成功。推荐对 Uber 有效，因为乘客是在一个永无止境的按次付费系统中支付行程费用。免费行程是一个持续的激励。对于 Duolingo，我们试图通过提供一个月的免费 Super Duolingo 来激励用户。然而，我们最好和最活跃的用户已经拥有 Super Duolingo，而且我们无法在他们已经处于计划中时再给他们一个月的免费服务。这意味着我们的策略，本应依赖我们最好的用户，实际上却将他们排除在外。

In both of these situations, we had borrowed successful features from other products, but the wrong way. We had failed to account for how a change in context can impact the success of a feature. I came away from these attempts realizing that I needed a better understanding of how to borrow ideas from other products intelligently. Now when looking to adopt a feature, I ask myself:  
在这两种情况下，我们都从其他产品中借鉴了成功的功能，但方式不正确。我们没有考虑到环境变化如何影响功能的成功。我从这些尝试中意识到，我需要更好地理解如何智能地借鉴其他产品的想法。现在，当我考虑采用一个功能时，我会问自己：

*   Why is this feature working in that product?  
    为什么这个功能在那个产品中能起作用？
    
*   Why might this feature succeed or fail in our context, i.e. will it translate well?  
    为什么这个功能在我们这个环境下可能会成功或失败，也就是说，它是否能够很好地翻译？
    
*   What adaptations are necessary to make this feature succeed in our context?  
    需要做出哪些调整才能使这个功能在我们这个环境中取得成功？
    

In other words, we needed to use better judgment in adapting when adopting. Being more systematic in just this area would have made a big difference in what gamification mechanics we chose to pursue. And we would have probably been dissuaded from focusing on referrals altogether. I was committed to making sure our next attempts would be more methodical. We needed to be better at basing our decisions on data, insights, and foundational principles.   
换句话说，我们在采用时需要更好地运用判断力。仅仅在这个领域更加系统化，就会在我们选择追求的哪些游戏化机制上产生重大差异。我们可能也会被劝阻，不再专注于推荐。我致力于确保我们的下一次尝试更加有条理。我们需要在基于数据、洞察力和基础原则做出决策方面做得更好。

Duolingo has always excelled at collecting data, especially in support of A/B testing. But there hadn’t been much effort put into using the data for insights generation. Having seen from the inside how Zynga and MyFitnessPal used data, I felt we could use Duolingo’s data to find a North Star metric and get the breakthrough we needed.   
多邻国一直擅长收集数据，尤其是在支持 A/B 测试方面。但并没有投入太多精力来利用数据生成洞见。从内部看到 Zynga 和 MyFitnessPal 如何使用数据后，我觉得我们可以利用多邻国的数据找到一个北极星指标，并取得我们需要的突破。

My time at Zynga and MyFitnessPal gave us inspiration on how to segment and model our users by engagement level. Zynga separated their users and measured retention based on the following weekly retention metrics:  
我在 Zynga 和 MyFitnessPal 的时光给了我们灵感，了解如何根据用户参与度来细分和建模我们的用户。Zynga 根据以下每周留存率指标来分离用户并衡量留存率：

*   **Current users retention rate (CURR):** The chance a user comes back this week if they came to the product each of the past two weeks   
    当前用户留存率（CURR）：如果用户在过去两周的每一周都使用过产品，那么他们这周回来使用的概率
    
*   **New users retention rate (NURR):** The chance a user comes back this week if they were new to the product last week   
    新用户留存率（NURR）：如果用户上周是新用户，那么他们这周回来机会的大小
    
*   **Reactivated user retention rates (RURR):** The chance a user comes back this week if they reactivated last week  
    重新激活用户留存率（RURR）：如果用户在上周重新激活，本周他们回来的概率
    

Later, when I worked at MyFitnessPal, I found that they had adopted and expanded Zynga’s retention work. They not only used CURR, NURR, and RURR to measure growth but also to model future scenarios. They also added SURR:  
后来，我在 MyFitnessPal 工作时发现，他们采用了并扩展了 Zynga 的留存工作。他们不仅使用 CURR、NURR 和 RURR 来衡量增长，还用来模拟未来场景。他们还增加了 SURR：

*   **Resurrected user retention rate (SURR):** The chance a user comes back this week if they resurrected (from a longer absence) last week  
    复活用户留存率（SURR）：如果用户在上周复活（从较长时间的缺席中）的话，这周他们回来的概率
    

I hypothesized that we could use these metrics at Duolingo as a starting point to create a more sophisticated model, and use that model to identify a North Star metric. Working with the data scientist and the engineer manager in the Acquisition Team, we came up with the model below. We used the same retention rates as Zynga and MyFitnessPal, but we tweaked from a weekly view to a daily view and we added several more metrics.  
我假设我们可以将这些指标作为 Duolingo 的起点，创建一个更复杂的模型，并使用该模型来识别一个北极星指标。与获取团队的数据科学家和工程师经理合作，我们提出了以下模型。我们使用了 Zynga 和 MyFitnessPal 相同的留存率，但将视角从每周调整为每日，并添加了更多指标。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123237722.jpeg?cd-oss-obs)



The blocks, or _buckets_, represent different user segments with different levels of engagement. And every single user who has ever used the product is in one, and only one, bucket on any given day. That means the buckets in the model are MECE (mutually exclusive, collectively exhaustive) in representing the entire base of users who have ever used Duolingo. The _arrows_ measure the movement of users between the buckets (these include CURR, NURR, RURR, and SURR, but evolved into daily retention rates rather than weekly). Combining the buckets and the arrows, the model creates an almost closed-circuit system, with new users being the only break.   
块或桶代表不同参与程度的用户群体。每个曾经使用过产品的用户在任何给定的一天都只属于一个，且仅属于一个桶。这意味着模型中的桶在表示所有曾经使用过 Duolingo 的用户基础时是 MECE（相互独立，完全穷尽）的。箭头衡量用户在不同桶之间的流动（包括 CURR、NURR、RURR 和 SURR，但已演变为日留存率而不是周留存率）。结合桶和箭头，该模型创建了一个几乎封闭的回路系统，新用户是唯一的突破口。

Conveniently, the top four buckets of the model add up to DAU. Those buckets are defined as:   
方便的是，模型的前四个桶的总和等于日活跃用户数。这些桶被定义为：

*   **New users:** first day of engagement ever in the app  
    新用户：首次在应用中互动的日子
    
*   **Current users:** engaged today and at least one other time in the prior 6 days  
    当前用户：今天活跃，并在过去 6 天内至少活跃过一次
    
*   **Reactivated users:** first day of engagement after being away for 7-29 days  
    复活跃用户：离开 7-29 天后重新参与的第一天
    
*   **Resurrected users:** first day of engagement after being away for 30 days or longer  
    复活用户：离开 30 天或更长时间后的首次互动日
    

The remaining three buckets represent users who were not active today and have different degrees of inactivity.  
剩余三个类别代表今天未活跃的用户，他们具有不同程度的非活跃状态。

*   **At-risk WAU:** inactive today, but active in at least one of the prior 6 days   
    高危活跃用户：今天不活跃，但在过去 6 天中的至少一天活跃
    
    *   At-risk WAU + DAU = WAU   
        高危月活跃用户 + 日活跃用户 = 月活跃用户
        
*   **At-risk MAU:** inactive in the past seven days, but active in at least one of the prior 23 days   
    高危月活跃用户：过去七天不活跃，但在前 23 天中至少有一天活跃
    
    *   At-risk MAU + WAU = MAU  
        风险用户月活跃用户数 + 风险用户周活跃用户数 = 月活跃用户数
        
*   **Dormant users:** inactive in the past 31 days or longer   
    休眠用户：过去 31 天或更长时间未活跃
    
    *   MAU + dormant users =  Total user base  
        月活跃用户 + 睡眠用户 = 总用户群
        

The fact that DAU, WAU, and MAU can easily be calculated from these buckets made it easy to model them over time. This is a key feature of the model. Additionally, by manipulating the rates represented by the arrows, we can model the compounding and cumulative impact of moving these rates over time; in other words, the rates are the levers product teams can pull to grow DAU.  
DAU、WAU 和 MAU 可以从这些桶中轻松计算出来，这使得它们随时间建模变得容易。这是模型的关键特性。此外，通过操纵箭头所代表的比率，我们可以模拟这些比率随时间推移的复利和累积影响；换句话说，这些比率是产品团队能够拉动以增长 DAU 的杠杆。

With the model created, we started taking daily snapshots of data to create a history of how all of these user buckets and retention rates had evolved on a day-by-day basis over the past several years. With this data, we could create a forward-looking model and then perform a sensitivity analysis to predict which levers would have the biggest impact on DAU growth. We ran a simulation for each rate, where we moved a single rate 2% every quarter for three years, holding all the other rates constant.   
创建模型后，我们开始每天对数据进行快照，以创建过去几年中所有这些用户群体和留存率每日变化的记录。有了这些数据，我们可以创建一个前瞻性模型，然后进行敏感性分析，以预测哪些因素将对日活跃用户增长产生最大影响。我们对每个比率进行了模拟，其中每个季度将单个比率移动 2%，而将所有其他比率保持不变，持续三年。

Below are the results of our first simulation. It shows how those small 2% movements on each lever impacted forecasted MAU and DAU.  
以下是我们的第一次模拟结果。它显示了每个杠杆上那微小的 2%移动如何影响预测的 MAU 和 DAU。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123239245.jpeg?cd-oss-obs)



We immediately saw that CURR had a gigantic impact on DAU—5 times the impact of the second-best metric. In hindsight, the CURR finding made sense, because the Current User bucket has an interesting characteristic: current users who stay active return to the same bucket.  
我们立即看到 CURR 对日活跃用户数（DAU）产生了巨大影响——是第二好的指标的五倍。事后看来，CURR 的发现是有道理的，因为当前用户池具有一个有趣的特性：保持活跃的当前用户会回到同一个池子。



![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123240713.jpeg?cd-oss-obs)



This produces a compounding effect, which means that CURR is much harder to move, but when it does, it will have a greater impact. Based on this analysis, we knew that CURR was the metric we had to move in order to get that strategic breakthrough we wanted. We decided to create a new team, the Retention Team, with CURR as its North Star metric.  
这会产生一种复利效应，这意味着 CURR 更难移动，但一旦移动，它将产生更大的影响。基于这种分析，我们知道 CURR 是我们必须移动的指标，以便获得我们想要的战略突破。我们决定创建一个新的团队，即留存团队，以 CURR 作为其北极星指标。

One of the biggest benefits of focusing on CURR was deciding not to work on things that seemed paramount before, especially new-user retention. This was a huge mindset shift for a company that had tremendous success spending years running the bulk of its growth experiments on new users first.   
专注于 CURR 的最大好处之一是决定不再从事之前看似至关重要的事情，尤其是新用户留存。这对于一个多年来将大部分增长实验放在新用户身上的公司来说，是一个巨大的思维转变。

Another big lesson was seeing the massive gap between how a metric could impact DAU vs. MAU; for example, CURR’s impact on DAU was 6 times its impact on MAU. iWAURR (inactive WAU reactivation rate) was the second-best lever for moving DAU but a distant fourth for moving MAU, behind increasing new and resurrected users. This meant that, at some point, we would still need to figure out new growth vectors for new-user acquisition if we wanted to see substantial MAU improvements. But for the time being, our focus was only on moving DAU, so we prioritized CURR over all other growth levers. And it turned out to be the right choice.    
另一个重要教训是看到指标对日活跃用户（DAU）和月活跃用户（MAU）的影响之间存在巨大差距；例如，CURR 对 DAU 的影响是其对 MAU 影响的 6 倍。iWAURR（非活跃 WAU 激活率）是推动 DAU 的第二大杠杆，但在推动 MAU 方面却远远落后于增加新用户和复活用户，位居第四。这意味着，如果我们想看到 MAU 的实质性改善，我们最终仍需要找到新的用户获取增长向量。但在此期间，我们的重点仅在于推动 DAU，因此我们优先考虑 CURR，而其他所有增长杠杆都排在其次。结果证明这是一个正确的选择。

With this clear directive, we looked at our historical model data and at our A/B tests going back a few years to see if we had inadvertently done anything that had moved CURR in the past. Surprisingly, we hadn’t. In fact, CURR had not moved in years. We had to figure out our first steps to move CURR based on first principles.   
根据这个明确的指示，我们回顾了我们的历史模型数据和过去几年的 A/B 测试，看看我们是否无意中做了任何导致 CURR 过去发生变化的事情。令人惊讶的是，我们没有。事实上，CURR 多年来都没有变化。我们必须根据第一性原理来找出我们的第一步，以推动 CURR 的发展。

I still thought gamification was a good place to start when trying to improve retention. Our failure with the Gardenscapes-style moves counter hadn’t actually disproved any of the original reasons why we believed gamification still had upside for Duolingo—we had only learned that the moves counter was a clumsy attempt at it. This time, we would be more methodical and intelligent about features we added or borrowed. We made sure to apply the lessons from our prior efforts with gamification.  
我仍然认为，当试图提高用户留存率时，游戏化是一个不错的起点。我们尝试 Gardenscapes 风格的移动计数器失败，实际上并没有否定我们相信游戏化对 Duolingo 仍有上升空间的原有理由——我们只是了解到移动计数器是一个笨拙的游戏化尝试。这次，我们会更加有计划和智慧地添加或借鉴功能。我们确保将之前游戏化努力中的经验教训应用到这次中。

After some consideration, we decided to bet on leaderboards. Here’s why and how. Duolingo already had a leaderboard for users to compete with their friends and family, but it wasn’t particularly effective. Based on my experience at Zynga, I felt that there was a better way. When I started working on Zynga’s FarmVille 2 game, it included a leaderboard similar to Duolingo’s existing leaderboard, where users competed with their friends. I had hypothesized based on my personal experience as a player that the closeness of the competitor’s engagement would be more important than the closeness of personal relationships. I thought this would be especially true in a mature product where many users’ friends weren’t active anymore. From our testing at Zynga, that idea turned out to be true. Based on this, I felt a leaderboard system, similar to what I had helped design at Zynga, would succeed in the context of our product.  
经过一番考虑，我们决定押注排行榜。原因和做法如下。Duolingo 已经有一个排行榜，让用户可以与朋友和家人竞争，但效果并不理想。基于我在 Zynga 的经验，我认为有更好的方法。当我开始为 Zynga 的《农场小镇 2》游戏工作时，它包含了一个与 Duolingo 现有排行榜类似的排行榜，用户可以与朋友竞争。根据我作为玩家的个人经验，我假设竞争对手的参与度接近度比个人关系的接近度更重要。我认为这在成熟的产品中尤其如此，因为许多用户的亲朋好友可能已经不再活跃。根据我们在 Zynga 的测试，这个想法证明是正确的。基于这一点，我认为一个排行榜系统，类似于我在 Zynga 帮助设计的系统，在我们的产品环境中会取得成功。

FarmVille 2’s leaderboard also included a “league” system. Beyond getting to the top of a weekly leaderboard, users had the opportunity to move through a series of league levels (e.g. from the Bronze league to the Silver league to the Gold league). Leagues provided users with a greater sense of progress and reward, an integral element in game design. They also increased engagement over time, since engaged users move up to more competitive leagues week after week. We felt this feature would translate well to Duolingo’s existing product because it tapped directly into the common human motivators of competitiveness and progression.   
农场小镇 2 的排行榜还包括一个“联赛”系统。除了达到每周排行榜的顶端，用户还有机会通过一系列联赛等级（例如从青铜联赛到白银联赛再到黄金联赛）进行晋升。联赛为用户提供了更强的进步感和奖励感，这是游戏设计中的一个关键要素。它们还随着时间的推移增加了用户的参与度，因为积极参与的用户会每周晋升到更具竞争力的联赛。我们认为这个功能非常适合 Duolingo 现有的产品，因为它直接触动了人类共同的竞争和进步动机。

![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123242066.jpeg?cd-oss-obs)


_Users are matched with other users who had a similar level of engagement in the prior week. The top players at the end of this week move up to a higher league the following week.  
用户将与上周参与度相似的其他用户匹配。本周末排名靠前的玩家将在下周晋升到更高的联赛。_

Not all aspects of the FarmVille 2 leaderboards would translate well to Duolingo, though. We had to use our judgment to adapt this gaming mechanic to Duolingo’s context. In FarmVille 2, competing in the leaderboard required completing additional kinds of tasks on top of the core gameplay. That was something that we purposefully left out. In the Duolingo context, more tasks would only add unnecessary complexity to language learning. We deliberately made our leaderboard as casual and frictionless as possible; users were automatically opted in and could progress to the top of the first league by merely engaging consistently in their regular language study. By keeping the game mechanic exciting, but making it simpler than in FarmVille 2, we felt like we had struck the right balance of adopting and adapting.  
不是所有《农场小镇 2》排行榜的方面都能很好地转化为 Duolingo。我们不得不运用我们的判断来适应这种游戏机制到 Duolingo 的语境中。在《农场小镇 2》中，在排行榜上竞争需要在核心游戏玩法之外完成额外的任务。这是我们故意排除的。在 Duolingo 的语境中，更多的任务只会给语言学习增加不必要的复杂性。我们故意使我们的排行榜尽可能轻松和顺畅；用户默认加入，只需持续参与他们的常规语言学习，就可以进入第一联赛的顶端。通过保持游戏机制有趣，但比《农场小镇 2》更简单，我们感觉我们找到了采用和适应的正确平衡。

The leaderboards feature had a huge and almost immediate impact on our metrics. Overall learning time increased by 17%, and the number of highly engaged learners (users who spend at least 1 hour a day for 5 days a week) tripled. At this time, we hadn’t yet figured out how to calculate statistical significance for CURR, but we saw that our traditional retention metrics (D1, D7, etc.) improved materially and with statistical significance. Going forward, the leaderboards feature became a vector for improving metrics, and teams continue to optimize the feature to this day. Also importantly, the leaderboard was the Retention Team’s first breakthrough!   
排行榜功能对我们指标产生了巨大且几乎是立即的影响。总体学习时间增加了 17%，高度投入的学习者（每周至少投入 5 天，每天至少 1 小时）数量翻了两番。当时，我们还没有弄清楚如何计算 CURR 的统计显著性，但我们看到我们的传统留存率指标（D1、D7 等）在实质上和统计上都有所改善。展望未来，排行榜功能成为改善指标的一个因素，团队至今仍在优化该功能。同样重要的是，排行榜是留存团队的第一项突破！

The Retention Team was completely energized to find more mechanics to keep current users engaged and motivated to practice every day. One area they started to look into was push notifications. Based on substantial A/B testing in prior years, Duolingo had established that notifications can be a big vector for growth, but that impact had plateaued for us over the years. With a re-energized team full of new ideas, we felt it was the right time to revisit this vector.  
保留团队完全充满活力，寻找更多机制来保持现有用户的参与度和每天练习的动力。他们开始关注的一个领域是推送通知。基于前几年的大量 A/B 测试，Duolingo 已经确定通知可以成为增长的一个重要因素，但这种影响在我们这里已经多年停滞不前。随着一个充满新想法的重新振作的团队，我们觉得是时候重新审视这个因素了。

As we started diving into this, there was one principle that became paramount. It came from a cautionary tale from Groupon’s CEO. He explained to Luis von Ahn, our CEO, that for a long time, Groupon stuck to one email notification per day. But their team started wondering whether sending more emails would improve metrics. The CEO eventually gave in and allowed his team to test sending one more email to each user each day. This test resulted in a big increase to their target metrics. Encouraged, Groupon kept experimenting, sending more emails, even as many as five a day. Then, in what felt like a change from one day to the next, their email channel lost most of its effectiveness. Over time, the accumulation of Groupon’s aggressive email tests had basically destroyed their channel. One often underappreciated risk with aggressively A/B testing emails and push notifications is that it results in users opting out of the channel; and even if you kill the test, those users remain opted out forever. Do this many times, and you’ve destroyed your channel. This was the outcome to avoid. For our push notifications, we established one foundational rule: protect the channel.  
随着我们开始深入研究这个问题，有一个原则变得至关重要。这来自 Groupon 首席执行官的一个警示故事。他向我们的首席执行官 Luis von Ahn 解释说，长期以来，Groupon 每天只发送一封电子邮件通知。但他们的团队开始怀疑，发送更多电子邮件是否会改善指标。最终，首席执行官妥协了，允许他的团队每天向每个用户额外发送一封电子邮件进行测试。这个测试导致他们的目标指标大幅上升。受到鼓舞，Groupon 继续实验，发送更多电子邮件，甚至每天多达五封。然后，仿佛一夜之间发生了变化，他们的电子邮件渠道失去了大部分效果。随着时间的推移，Groupon 激进的电子邮件测试积累基本上摧毁了他们的渠道。在积极进行 A/B 测试电子邮件和推送通知时，一个常被低估的风险是会导致用户选择退出该渠道；即使你停止测试，这些用户也将永远退出。这样做很多次，你就已经摧毁了你的渠道。这是我们要避免的结果。对于我们的推送通知，我们确立了一个基本规则：保护渠道。

With this constraint in mind, we decided to give the team a lot of freedom to optimize on dimensions like timing, templates, images, copy, localization, etc., but they could not increase the quantity of notifications without strong justification and CEO approval. Over time, through countless iterations, A/B testing, and a bandit algorithm, the team was able to generate dozens of small- and medium-size wins that have amounted to substantial gains in DAU year after year.   
考虑到这个限制，我们决定给团队很大的自由度来优化时间、模板、图片、文案、本地化等维度，但他们不能在没有充分理由和 CEO 批准的情况下增加通知数量。随着时间的推移，通过无数次的迭代、A/B 测试和强盗算法，团队能够产生数十次小型和中型胜利，这些胜利累积起来每年都在 DAU 上带来了实质性的增长。


![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123243432.jpeg?cd-oss-obs)


_A meme about Duolingo’s “pushiness” that went viral in 2019  
关于 Duolingo“过于积极”的梗在 2019 年走红_

In the search for even more growth vectors, the APM on the Retention Team started exploring whether there was a strong correlation between retention and usage of particular Duolingo features. He discovered that if a user reached a 10-day streak, their chances of dropping off were reduced substantially. Clearly, a lot of this was simply correlation and selection bias, but we felt the insight was interesting enough to start investing in improving this feature again.   
在寻找更多增长动力的过程中，留存团队中的 APM 开始探索留存与特定 Duolingo 功能使用之间是否存在强烈的关联。他发现，如果用户达到 10 天连续学习，他们退出的可能性会大幅降低。显然，其中很多只是相关性以及选择偏差，但我们认为这个洞察足够有趣，足以开始再次投资改进这个功能。

The concept of a streak is really quite simple: show users the number of consecutive days they’ve done any activity on the app. But it turns out that there is a surprisingly large number of optimization opportunities around streaks.   
习惯概念其实非常简单：向用户展示他们在应用上连续进行任何活动的天数。但结果证明，围绕习惯有大量令人惊讶的优化机会。

We got our first big win with the streak-saver notification—a notification that alerts users with streaks if they are about to lose their streak. This late-night notification proved that indeed there was considerable upside to doubling down on streak optimizations. After this, several improvements followed: calendar views, animations, changes to streak freezes, and streak rewards, among others. Each helped improve upon the original streak idea and generated substantial improvements to retention.   
我们第一次取得重大胜利是通过连续挑战保存通知——一个提醒用户如果他们即将失去连续挑战的通知。这个深夜通知证明，确实在连续挑战优化上投入有相当大的回报。此后，还进行了几项改进：日历视图、动画、连续挑战冻结的更改以及连续挑战奖励等。每一项都帮助改进了原始的连续挑战想法，并产生了对用户留存率的显著提升。


![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123244551.png?cd-oss-obs)



To date, the streak feature is one of Duolingo’s most powerful engagement mechanics. When people talk about their Duolingo experience, they often bring up their streak. I recently met one user who told me, “I have a 1,435-day streak!” and added, “with no streak freezes!” His bragging rights were well-earned, as he had been studying his chosen language daily for almost four years.  
截至目前，连点功能是 Duolingo 最强大的参与机制之一。当人们谈论他们的 Duolingo 体验时，他们经常提到他们的连点。我最近遇到一位用户，他告诉我：“我有一个 1,435 天的连点！”并补充说，“没有连点冻结！”他的炫耀权是当之无愧的，因为他几乎每天都在学习他选择的语言，已经接近四年了。

Streaks work for a number of reasons. One of those is that a streak increases user motivation over time; the longer the streak is, the greater the impetus to keep the streak going. When it comes to user retention, this is the exact behavior we want in our users. Each day that a learner comes to Duolingo, they care a bit more about coming back the next day than they did the day before, hence increasing retention and DAU. As a meta-lesson, our success with the streak mechanic further showed us that we could squeeze major wins from existing features. We could see the value in both big breakthroughs and in fast optimizations. And an A+ team often has a mix of both.  
连赢机制之所以有效，有多个原因。其中之一是连赢会随着时间的推移增加用户的动机；连赢时间越长，保持连赢的动力就越大。在用户留存方面，这正是我们希望用户表现出的行为。每当学习者来到 Duolingo，他们比前一天更关心第二天再来，从而增加了留存率和日活跃用户数。作为一个元教训，我们在连赢机制上的成功进一步表明，我们可以从现有功能中挤出重大胜利。我们既能看到重大突破的价值，也能看到快速优化的价值。而一个 A+团队通常两者兼备。

We didn’t stop at CURR; there was a very healthy paranoia that at some point CURR would hit a ceiling, so sooner or later we would have to figure out growth vectors for new user acquisition. The Retention Team stayed focused on increasing CURR, but as a company, we consistently increased our investment in growth by creating more and more Product and Marketing teams to find new vectors (for both retention and acquisition). Luckily, several of these bets worked, including expanding internationally, building social features (this is what the Acquisition eventually team pivoted to, with great success), accelerating course content creation, working with influencers, increasing our presence in schools, investing (a little bit) in paid UA, and going crazy viral on TikTok. Each of these merits its own case study.   
我们没有止步于 CURR；我们有一种非常健康的偏执，认为 CURR 最终会触及天花板，所以迟早我们需要找出新的用户获取增长向量。留存团队专注于提高 CURR，但作为一家公司，我们通过创建更多产品和营销团队来不断增加我们对增长的投入，以寻找新的增长向量（既包括留存也包括获取）。幸运的是，其中一些赌注取得了成功，包括拓展国际市场，构建社交功能（这就是获取团队最终转向并获得巨大成功的方向），加速课程内容的创作，与影响者合作，增加我们在学校的影响力，在付费用户获取上（稍微）投资，以及在 TikTok 上疯狂病毒式传播。每个方面都值得进行单独的研究案例。

Through our efforts over four years, we were able to increase CURR by 21%, which represents a reduction in the daily churn of our best users by over 40% and, together with our other successful bets, led to an increase in our DAU of 4.5x. Last year was one of the fastest growth rates in Duolingo’s history. The quality of the user base also improved; the share of our DAU with a streak of 7 days or longer increased almost 3 times to more than half of our DAU. This means that not only does Duolingo have a much higher number of active users now, but also that those users are much more likely to keep coming back, refer their friends, and subscribe to Super Duolingo. This growth was key to Duolingo’s successful IPO.   
通过我们四年的努力，我们成功将 CURR 提高了 21%，这代表着我们最佳用户的日流失率降低了 40%以上，并且与其他成功的投资一起，导致了我们的日活跃用户数增长了 4.5 倍。去年是 Duolingo 历史上增长最快的年份之一。用户群体的质量也得到了提升；连续 7 天或更长时间活跃的日活跃用户比例几乎增加了 3 倍，达到了我们日活跃用户的一半以上。这意味着，现在 Duolingo 不仅拥有更多的活跃用户，而且这些用户更有可能持续回来，推荐给朋友，并订阅 Super Duolingo。这种增长是 Duolingo 成功 IPO 的关键。

I hope that this article gives you the inspiration you need to find new vectors of growth for your product. If you adopt anything from my experience at Duolingo, I hope you adapt it to your own context using your best judgment. Don’t blindly trust what Duolingo or any other company did. Certainly that didn’t work for me. Happy experimenting!  
我希望这篇文章能给你带来灵感，帮助你找到你产品的新的增长点。如果你从我在 Duolingo 的经验中采纳了任何东西，我希望你能根据自己的最佳判断将其适应到你的环境中。不要盲目相信 Duolingo 或其他公司所做的事情。当然，那对我并不奏效。祝实验愉快！

_Gamification Team: You know who you are. Thank you for teaching me so much!  
游戏化团队：你知道你是谁。感谢你教会我这么多！_

_Acquisition Team: Vanessa Jameson (Engineer Director), Cem Kansu and Liz Nagler (PMs on the team, now VP of Product and Product Area Lead for Growth, respectively), and the rest of the team, who worked super-hard and eventually made a smart and successful pivot to work on social features. Shoutout to Nico Sacheri (Principal PM) and Hideki Shima (Eng Director), who have been crushing it leading the Connections team for the past couple of years.  
收购团队：Vanessa Jameson（工程总监）、Cem Kansu 和 Liz Nagler（团队产品经理，现在分别是产品副总裁和增长产品领域负责人），以及其余团队成员，他们工作非常努力，最终成功转向开发社交功能。向 Nico Sacheri（高级产品经理）和 Hideki Shima（工程总监）致敬，他们在过去几年里领导连接团队表现出色。_

_Growth Model: Erin Gustafson (Staff Data Scientist) and Vanessa Jameson, who collaborated with me in the creation of the growth model. Learn more about how Erin is working to evolve the way Duolingo thinks about growth in her recent post: [https://blog.duolingo.com/growth-model-duolingo/](https://blog.duolingo.com/growth-model-duolingo/)  
增长模型：Erin Gustafson（员工数据科学家）和 Vanessa Jameson，他们与我合作创建了增长模型。了解更多关于 Erin 如何努力让 Duolingo 在增长方面有所转变的信息，请参阅她的最新文章：https://blog.duolingo.com/growth-model-duolingo/_

_Retention Team: Sean Colombo (OG Engineer Manager for the team, and now Eng Area Lead for Growth), Daniel Falabella (OG PM for the team, now GM for Duolingo ABC), John Trivelli (Designer on leaderboards), Anton Yu (PM who “re-discovered” streaks and so much more), Jackson Shuttleworth and Osman Mansur (Sr. PM and PM on the team today, still crushing it), Antonia Scheidel (Engineering Manager, also crushing it), and all the wonderful engineers and designers who have worked and continue to work on this team.  
保留团队：Sean Colombo（该团队的首席工程师经理，现在是增长领域的负责人），Daniel Falabella（该团队的首席产品经理，现在是 Duolingo ABC 的总经理），John Trivelli（排行榜设计师），Anton Yu（重新发现了连赢模式以及更多内容的产品经理），Jackson Shuttleworth 和 Osman Mansur（高级产品经理和团队当前的产品经理，依然表现出色），Antonia Scheidel（工程经理，同样表现出色），以及所有为这个团队工作过并继续工作的优秀工程师和设计师。_

_Gina Gotthilf, who was a total growth rock star in Duolingo’s early years.  
吉娜·戈特希尔夫，在 Duolingo 早期是全面增长领域的明星。_

_Luis von Ahn (CEO) and Tyler Murphy (Chief Designer), with whom I reviewed every single product change for almost five years.  
路易斯·冯·艾恩（CEO）和泰勒·墨菲（首席设计师），我与他们几乎审查了五年来每一个产品的每一项变更。_

Thank you, Jorge! You can follow Jorge for more on [LinkedIn](https://www.linkedin.com/in/jorgemazal/) and [Twitter](https://twitter.com/jorgemazal).  
感谢您，Jorge！您可以在领英和推特上关注 Jorge 了解更多信息。

Have a fulfilling and productive week 🙏  
祝您有一个充实而富有成效的一周 🙏

If you’re hiring, [join Lenny’s Talent Collective](https://www.lennysjobs.com/talent/welcome) to start getting bi-monthly drops of world-class hand-curated product and growth people who are open to new opportunities.  
如果您正在招聘，加入 Lenny 的人才集体，开始每月两次获得世界级精选的产品和增长人才，他们愿意接受新机会。


![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250416123246487.jpeg?cd-oss-obs)


If you’re looking for a new gig, join the collective to get personalized opportunities from hand-selected companies. You can join publicly or anonymously, and leave anytime.  
如果您正在寻找新的工作，加入这个集体，以获得精选公司的个性化机会。您可以公开或匿名加入，随时离开。

[Apply to join 申请加入](https://www.lennysjobs.com/talent)

1.  **Athena:** [Head of Growth](http://head%20of%20growth/) (Remote)  
    雅典娜：增长负责人（远程）
    
2.  **MetaMap:** [VP, Product](https://www.lennysjobs.com/jobs/74ca739b-4b51-4d55-8727-6606327fae58) (SF, Miami, Mexico City)  
    元数据地图：VP，产品（SF，迈阿密，墨西哥城）
    

**If you’re finding this newsletter valuable, share it with a friend, and consider subscribing if you haven’t already.  
如果您觉得这份通讯有价值，请与朋友分享，如果您还没有的话，请考虑订阅。**

Sincerely, 诚挚地

Lenny 👋