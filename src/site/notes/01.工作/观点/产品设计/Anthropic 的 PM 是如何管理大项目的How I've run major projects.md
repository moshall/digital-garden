---
{"dg-publish":true,"permalink":"/01.工作/观点/产品设计/Anthropic 的 PM 是如何管理大项目的How I've run major projects/","title":"How I've run major projects","tags":["clippings"]}
---

My few most productive individual weeks at Anthropic have all been “crisis project management:” coordinating major, time-sensitive implementation or debugging efforts.  
我在人类人道上最有生产力的几个星期都是“危机项目管理：协调主要，时间敏感的实施或调试工作。

In a company like Anthropic, excellent project management is an extremely high-leverage skill, and not just during crises: our work has tons of moving parts with complex, non-obvious interdependencies and hard schedule constraints, which means organizing them is a huge job, and can save weeks of delays if done right. Although a lot of the examples here come from crisis projects, most of the principles here are also the way I try to run any project, just more-so.  
在诸如Anthropic的公司中，出色的项目管理是一项非常高杠杆的技能，而不仅仅是在危机期间：我们的工作具有大量的活动部件，具有复杂，非显而易见的相互依存关系和艰难的时间表约束，这意味着组织它们是一项巨大的工作，并且可以节省数周的延误。尽管这里的许多例子都来自危机项目，但这里的大多数原则也是我尝试运行任何项目的方式。

I think excellent project management is also *rarer than it needs to be*. During the crisis projects I didn’t feel like I was doing anything particularly impressive; mostly it felt like I was putting in a lot of work but doing things that felt relatively straightforward. On the other hand, I often see other people miss chances to do those things, maybe for lack of having seen a good playbook.  
我认为出色的项目管理也 *比需要的要少* 。在危机项目中，我没有觉得自己做的事情特别令人印象深刻。大多数情况下，感觉就像我在做很多工作，但是做的事情感觉相对简单。另一方面，我经常看到其他人错过了做这些事情的机会，也许是因为缺少看过一本好的剧本。

So here’s an attempt to describe my playbook for when I’m being intense about project management.  
因此，这是为了描述我对项目管理的强烈态度的尝试。

(I’ve described what I did as “coordinating” above, but that’s underselling it a bit; it mattered a lot for this playbook that I had enough technical context, and organizational trust, to autonomously make most prioritization decisions about the project. Sometimes we instead try to have the trusted decisionmakers not be highly involved in managing execution, and instead farm that out to a lower-context or less-trusted project manager to save the trusted decisionmaker time, but IMO this is usually a false economy for projects where it’s critical that they be executed well.)  
（我已经将我所做的工作描述为上面的“协调”，但这是有点说明的；对于本剧本而言，我拥有足够的技术背景和组织信任，可以自主做出有关该项目的最优先决定的最优先决定。有时我们会试图使可信赖的决策者高度参与较低的计划，而不是在管理执行过程中，而不是在努力管理的努力，而不是稳定的，而不是稳定的，则可以遵守该项目的范围。通常，对于要执行良好的项目至关重要的项目，经济通常是错误的。）

## Focus 重点

For each of the crisis management projects I completely cleared my schedule to focus on them, and ended up spending 6+ hours a day organizing them.  
对于每个危机管理项目，我完全清除了我的时间表，以专注于它们，最终每天花6个小时以上的时间组织它们。

This is a bit unintuitive because I’m used to thinking of information processing as basically a free action. After all, you’re “just” moving info from place to place, not doing real work like coding, right? But if you add it all up—running meetings, pinging for updates, digesting Slack threads, pinging for updates again, thinking about what’s next, pinging for updates a third time, etc.—it’s surprisingly time-intensive.  
这有点不直觉，因为我习惯于将信息处理视为基本上的免费动作。毕竟，您“只是”将信息从到处移动，而不是做真正的编码，对吗？但是，如果您将所有内容添加 - 进行了会议，更新，消化休闲线程，再次进行更新，思考下一步，第三次更新等等，等等。

Even more importantly than freeing up time, clearing my schedule made sure the project was the [top idea in my mind](https://paulgraham.com/top.html). If I don’t do that, it’s easy for me to let projects “go on autopilot,” where I keep them running but don’t proactively make time to think through things like whether we should change goals, add or drop priorities, or do other “non-obvious” things.  
甚至比释放时间更重要的是，清除我的日程安排，确保该项目是 [我脑海中的佼佼者](https://paulgraham.com/top.html) 。如果我不这样做，那么我很容易让项目“继续自动驾驶”，在这里我保持它们的运行，但不要主动抽出时间思考诸如我们应该更改目标，添加或删除优先级或做其他“非明显”的事情之类的事情。

For non-crisis projects, it’s often not tenable (or the right prioritization) to spend 6+ hours a day project-managing; but it’s still the case that you can improve execution a lot if you focus and make them a top priority, e.g. by carving out dedicated time every day to check statuses, contemplate priorities, broadcast updates, and so on.  
对于非危机项目，每天花费6个小时以上的项目管理通常不可用（或正确的优先级）；但是，如果您专注并将其作为首要任务，例如，每天都要划出专门的时间来检查状态，考虑优先级，广播更新等，那么您仍然可以经常提高执行力。

## Maintain a detailed plan for victory维持胜利的详细计划

A specific tool that I’ve found critical for staying oriented and updating quickly is a *detailed plan for victory*, i.e., a list of steps, as concrete as possible, that end with the goal being achieved.  
我发现，我发现对保持面向和更新至关重要的特定工具是 *胜利的详细计划* ，即尽可能具体的步骤清单，最终达到了目标。

The plan is important because whether or not we’re achieving the plan is the best way to figure out how well or badly things are going. Knowing how well or badly things are going is important because it tells me when to start asking for more support, cutting scope, escalating problems, and otherwise sounding more alarms. One of the most common megaproject failure modes is to *not freak out soon enough*, and having a concrete plan is the best antidote.  
该计划很重要，因为我们是否正在实现计划是弄清楚事情进展顺利的最佳方法。知道事情的进展程度很重要，因为它告诉我何时开始寻求更多支持，削减范围，升级问题以及否则会发出更多警报。最常见的大型注射故障模式之一是 *不要尽快吓坏* ，而制定具体计划是最好的解毒剂。

As a both positive and negative example of this, during a recent sprint to release a new implementation of a model, we took a detailed accounting of all the work we thought we had to do to launch.  
作为一个正面和负面的例子，在最近发布新的模型实施的冲刺期间，我们详细介绍了我们认为我们必须做的所有工作。

- On the plus side, this made it clear three months before launch that things were going to be *very* tight, and this enabled us to ask for help from another team, who loaned us someone who sped up the project a fair amount.  
	从好的方面来说，这在发射前三个月清楚地表明，事情将 *非常* 紧张，这使我们能够向另一个团队寻求帮助，他们借给我们一个加速该项目的人大量贷款。
- On the minus side, we also massively underestimated a few components of the project, and because of this, we still ended up very crunched at the end.  
	在负方面，我们还大量低估了该项目的一些组成部分，因此，最后我们仍然非常紧缩。

As the above example shows, having a plan can’t completely save you if you underestimate how long all the steps in the plan will take. But it certainly helps! My sense is that the main things that would have helped even more in the above case were:  
如上面的示例所示，如果您低估了计划中的所有步骤需要多长时间，就无法完全保存您。但这肯定有帮助！我的感觉是，在上述情况下，主要有所帮助的主要因素是：

- We were inexperienced at estimating tasks, especially tasks related to new model implementations (which most people on the team were too new to have done before), and we were too cowardly to add the requisite amount of “slop” to our plan.  
	我们没有经验来估算任务，尤其是与新模型实施相关的任务（团队中的大多数人都太新而无法做到这一点），我们太胆怯了，无法在我们的计划中添加必要的“斜率”。
- We didn’t check in frequently enough against the plan once we made it, or sound the alarm early enough when we went off-plan.  
	一旦我们制定计划，我们对计划的频率不够频繁，或者在脱机计划时会尽早发出警报。

## Run a fast OODA loop运行快速的Ooda循环

OODA stands for “observe, orient, decide, act”—in other words, the process by which you *update your plans and behavior based on new information*.  
Ooda代表“观察，东方决定，行动” - 换句话说，您 *根据新信息更新计划和行为的* 过程。

Most of the large projects I’ve worked on have been characterized by incomplete information:  
我从事的大多数大型项目都以不完整的信息为特征：

- Our cluster’s networking is bad, but we don’t understand why.  
	我们的集群的网络不好，但我们不明白为什么。
- We have a correctness bug but we don’t know where it is.  
	我们有一个正确的错误，但我们不知道它在哪里。
- We need to rewrite the system but we’re not totally sure what the rewrite should look like.  
	我们需要重写系统，但是我们不确定重写应该是什么样的。

In fact, I’d make a stronger claim: usually getting complete information *was the hard part of the project*, and took up a substantial fraction of the overall critical-path timeline.  
实际上，我会提出更强有力的声明：通常，获取完整的信息 *是该项目的困难部分* ，并且占了整体关键路径时间表的很大一部分。

For example, let’s take a recent project to kick off a training run. The critical path probably looked something like:  
例如，让我们采取一个最近的项目开始训练。关键的道路可能看起来像：

1. Chips for the training run are delivered  
	培训运行的筹码已交付
2. We run some tests 我们进行了一些测试
3. We discover one aspect of performance is unexpectedly poor  
	我们发现表演的一个方面出乎意料地糟糕
4. We escalate the problem with our compute partner  
	我们通过计算合作伙伴升级了问题
5. Compute partner staffs a large debugging effort  
	计算合作伙伴员工大量的调试工作
6. We realize we had given our compute partner an outdated benchmark that is causing them to target the wrong improvements  
	我们意识到我们已经为我们的计算合作伙伴提供了过时的基准，这导致他们针对错误的改进
7. Compute partner switches benchmark and prioritizes different improvements  
	计算合作伙伴切换基准并优先考虑不同的改进
8. We share our benchmarks with compute partner so they can run the exact same code as us  
	我们与计算合作伙伴共享基准，以便他们可以运行与我们完全相同的代码
9. Compute partner rolls out improvements  
	计算合作伙伴进行改进
10. We test the improvements 我们测试改进
11. Performance is still poor and we tell them that  
	表现仍然很差，我们告诉他们
12. Repeat steps 8-10 until eventually it’s good enough  
	重复步骤8-10，直到最终足够好

Practically all of these steps are about information-processing, not writing code! Even the step where the compute partner debugged the problems on their side was itself constrained by information processing speed, since there were tens of people working on the debugging effort and coordinating / sharing info between them was difficult. Overall, the project timeline was strongly constrained by how quickly information could round-trip from our compute partner’s large-scale debugging effort, through their tech lead, me, and Anthropic’s large-scale debugging effort.  
实际上，所有这些步骤都是关于信息处理的，而不是编写代码！即使是计算合作伙伴在他们身边进行调试的步骤本身也受到信息处理速度的限制，因为很难进行调试工作和协调 /共享信息，因此很难。总体而言，该项目时间表受到了如何通过我们的Compute合作伙伴的大规模调试工作来往返的信息，通过他们的技术负责人，我和Anthropic的大规模调试工作。

This pattern generalizes to most projects I’ve been a part of, and as a result, one of my most productive project management habits is to try to run the fastest OODA loop that I can.  
这种模式概括了我参与的大多数项目，结果，我最有效的项目管理习惯之一就是尝试运行我可以使用的最快的OODA环路。

A few specific things that I’ve found help:  
我发现的一些具体事项：

- **Spend time on it:** running OODA loops takes time, and is one of the primary reasons that, as mentioned above, I usually spend 6+ hours a day on running a megaproject if it’s in crisis mode.  
	**花点时间：** 运行Ooda循环需要时间，这是上述我通常每天花6个小时以上的主要原因之一，如果它处于危机模式，则在运行大型项目上。
- **Communicate uncomfortably much:** For the training run debugging, to reduce the round-trip time between orgs as much as possible, I had multiple daily calls with my counterpart at our compute partner (9am and 6pm). For the model implementation effort, I was basically constantly bouncing between different groups of debuggers, asking for updates and processing them.  
	**非常不舒服地交流：** 对于训练运行调试，为了尽可能减少组织之间的往返时间，我在计算合作伙伴（上午9点和下午6点）与同行每天都有多次电话。对于模型实施工作，我基本上不断在不同的辩论者组之间弹跳，要求更新和处理它们。
- **Track and prioritize the biggest open questions:** For most big projects I’ve maintained a living doc with a ranked list of all my *biggest open questions* about the project. Resolving or de-risking these uncertainties basically turns into the project’s priority list.  
	**跟踪和优先考虑最大的开放问题：** 对于大多数大型项目，我维持了一个活着的文档，其中包括我有关该项目的所有 *最大开放问题* 的排名列表。解决这些不确定性基本上变成了项目的优先级列表。  
	Ideally, there are enough people working on the project that we can work on resolving multiple of the uncertainties in parallel, since that’s one of the best ways to speed things up. (And for a project in “crisis mode,” if we have more top priorities than we can parallel-path with the current set of people working on the problem, that’s also a good test for whether it’s time to pull in more folks.)  
	理想情况下，有足够多的人可以并行解决多个不确定性，因为这是加快事物的最佳方法之一。 （对于“危机模式”的项目，如果我们比当前处理该问题的人的首要任务要比我们可以并行的高度更高，那么这也是一个很好的测试，对于是否是时候吸引更多人。）
- **Step back and reorient frequently:** Other than asking for updates, the main thing I spend time on was *reorienting* —looking at our list of priorities, asking myself whether they should still be the top priorities, then looking at what people were working on, and making sure those things were attacking the top priorities. I probably reviewed the project’s priorities multiple times a day as well, although I often didn’t make changes as a result.  
	**退后一步，经常进行重新定向：** 除了要求更新之外，我花时间的主要时间是 *重新定位* - 看我们的优先级列表，问自己是否应该仍然是首要任务，然后查看人们正在从事的工作，并确保这些事情在攻击首要任务。我可能每天也多次审查该项目的优先级，尽管结果我经常没有进行更改。
	- (Note that it is possible to change what people are working on too often, since switching tasks is costly. Parallelizing work on the top few priorities, as mentioned above, helps with this, since if you decide that priority #3 is now #1, but there are 2 people working on each, then nobody has to switch tasks. The thing that kills you is when *no one* is working on the new priority #1.)  
		（请注意，可以更改人们的工作频率，因为切换任务是昂贵的。如上所述，在最重要的优先级上并行工作会有所帮助，因为如果您决定现在的优先级＃3现在是＃1，但是每个人都有2个人在处理每个人，那么没有人必须切换您的任务。没有人会杀死您的工作，而 *没有人* 在处理新的优先级优先级。）。

## Overcommunicate 过度通信

It’s not just enough for me personally to be running a fast OODA loop—in a large group, *everyone* needs to be autonomously making frequent, high-quality, *local* prioritization decisions, without needing a round-trip through me. To get there, they need to be ambiently aware of:  
对于我个人而言，运行快速的Ooda循环不足以让 *我* 自主做出频繁，高质量的 *本地* 优先级决策，而无需通过我进行往返。要到达那里，他们需要周围意识到：

1. what else is going on around them, so they can coordinate and update on new info quickly (“oh, we’re planning to kick off the next derisking run in three days, so I have to have my new RL environment ready and tested by then”)  
	周围还有什么事，因此他们可以快速协调和更新新信息（“哦，我们打算在三天内开始下一个derisking跑，所以我必须准备好新的RL环境并进行测试”））
2. how their goal fits into the overall project, so they can make correct decisions about the details of their approach (“we’re trying to scale up as much as possible right now, so this direction isn’t valuable to pursue since it could never provide the scale of data we need”)  
	他们的目标如何适合整个项目，以便他们可以正确决定其方法的细节（“我们正在尝试尽可能多地扩展扩展，因此该方向不可能追求，因为它永远无法提供我们需要的数据规模”）））

I’ve usually found that to create the right level of ambient awareness, I have to repeat the same things way more often than I intuitively expect. This is roughly the same “communicate uncomfortably much” principle above, but applied to broadcasts and not just 1:1 conversations with people.  
我通常发现，要创造正确的环境意识，我必须比直觉上预期的要经常重复相同的方式。上面的原则大致相同，“传达不舒服的原则”，但适用于广播，而不仅仅是与人的1：1对话。

For example, although the first team I managed at Anthropic started with a daily asynchronous standup, we found that synchronous meetings were much more effective for creating common knowledge and reorienting, so we moved to a twice-weekly synchronous standup, which probably qualified as “uncomfortably much” synchronous communication for Anthropic at the time.  
例如，尽管我在众人界的一线队始于每日异步的站立式站立，但我们发现同步会议对于建立常识和重新定位的同步会议更为有效，因此我们每周两次搬到了两次同步的站立式站立上，这可能是“不舒服地相同”的同步交流，以期与人类的同步交流。

## Break off subprojects 打破子标题

Once a project gets over maybe 10 people, I can’t track everything myself in enough detail to project-manage the entire thing myself. At this point, it becomes critical to delegate.  
一旦一个项目越过了10人，我就无法详细地跟踪一切，无法自己计划整个过程。在这一点上，委派变得至关重要。

Here I mean delegating the *project management*, not just the execution (that’s what I’d be delegating to the first 10 people). This is the point where I need other people to help split up the work, monitor and communicate progress, escalate blockers, etc.  
在这里，我的意思是委派 *项目管理* ，而不仅仅是执行（这就是我将要委派给前十个人的内容）。这是我需要其他人来帮助分开工作，监视和交流进度，升级阻滞剂等的地步。

A few things I try to keep in mind when delegating project management:  
在委派项目管理时，我试图牢记的一些事情：

- The ideal unit of delegation is a crisp, *simple*, high-level goal, with limited overlap with other workstreams. (This is as opposed to, e.g., a list of tasks like “see if X helps.“) Good examples: “get X training technique working over Y networking protocol at Z throughput,” “get identical evals between model implementations A and B.” Bad examples: “follow this 10-step checklist that we hope results in training working,” “try these 3 techniques for debugging the loss eval.”  
	委派的理想单位是一个清晰， *简单* ，高级的目标，与其他工作流的重叠有限。 （这是与“查看X是否有帮助”之类的任务列表相对的，例如：“获取X培训技术在z吞吐量处使用y网络协议，”“在模型实现A和B之间获得相同的EVALS。”不好的例子：“遵循这份10步清单，我们希望能够导致培训工作，”“尝试这三种技术来调试损失评估。”
- The best project-managers are often *not* the strongest technical ICs. Instead the most important traits are that they’re highly organized and great at staying laser focused on end goals, perhaps to the point of being annoying about it. IC depth helps and I’ll never say no to it, but it’s not what I’d optimize for.  
	最好的项目经理通常 *不是* 最强大的技术IC。取而代之的是，最重要的特征是它们高度井井有条，并且擅长保持激光专注于最终目标，也许是为此而烦恼。 IC深度会有所帮助，我永远不会对此拒绝，但这不是我优化的。
- People running subprojects are probably also doing a lot of the same stuff I do, in particular e.g. spending a lot of time on it. That means they’ll take a substantial hit to their IC productivity. This is expected, and is often worth it. “Direction is more important than magnitude”—it’s usually better to have a lower-velocity project that works on the right things, than a higher-velocity one that’s pointed at the wrong goal.  
	运行副标题的人可能也在做很多我所做的事情，特别是在上面花费大量时间。这意味着他们将对他们的IC生产力进行重大打击。这是可以预期的，而且通常值得。 “方向比大小更重要” - 通常，要在正确的事物上使用的低速项目比一个指向错误的目标的高速项目更好。

One of my favorite things to make delegation easier is to *keep goals simple* —if they can fit in a Slack message while still crisply describing a path to the desired end state, then the people working on the goal will be much more able to prioritize autonomously, and point their work at the real end goal rather than doing something that turns out to be useless for some reason they didn’t think about.  
我最喜欢使委派更容易的事情之一是使 *目标保持简单* - 如果它们可以适应松弛的信息，同时仍然清楚地描述了通往所需的最终状态的道路，那么实现目标的人们将更有能力自主的优先级，并将他们的工作定位为真实的最终目标，而不是为了某种原因而没有想到的原因。

“Keep goals simple” doesn’t have to mean “do less”—the best way to keep goals simple is to *find the latent structure that enables a clean recursive decomposition into subgoals*. This often requires a deceptive amount of work—both cognitive and hands-on-keyboard—to identify the right intermediate goals, but I’ve found that it pays off immensely by clarifying what’s important to work on.  
“保持目标简单”并不一定意味着“少做” - 保持目标简单的最佳方法是 *找到可以将干净的递归分解为子目标的潜在结构* 。这通常需要欺骗性的工作（包括认知和动手键盘）来确定正确的中间目标，但是我发现它通过澄清工作重要的事情而获得了极大的回报。

## Have fun 玩得开心

Some of my favorite memories of Anthropic are of helping out with these big projects. While they can be intense, it’s also really inspiring to see how our team comes together, and the feeling of being part of a big team of truly excellent people cooking something ambitious together can be really magical! So I try to enjoy the chaos:)  
我最喜欢的众人记忆是为这些大型项目提供帮助。尽管他们可能会很激烈，但看到我们的团队如何融合在一起也确实令人鼓舞，并且成为一个真正优秀的人组成的大型团队的一部分，这确实是神奇的！所以我试图享受混乱:)

---

*Here’s the internal doc I share with folks on my team who are getting into being responsible for large projects.  
这是我与团队中的人们分享的内部文档，他们正在对大型项目负责。*

So you’re the DRI of a project (or part of one). Concretely, what do you do to “be DRI”?  
因此，您是一个项目（或一个项目的一部分）的DRI。具体而言，您如何做什么？

This doc is my suggested “starter kit” answer to that question. The habits and rituals described here aren’t perfect for every situation, but they’re lightweight and broadly helpful. I suggest you use them as a starting point for iteration: try them out, then adjust as necessary. This is an SL init; the RL is your job:)  
该文档是我建议的“入门套件”的答案。这里描述的习惯和仪式并不适合每种情况，但是它们轻巧且广泛帮助。我建议您将它们用作迭代的起点：尝试一下，然后根据需要进行调整。这是一个初始化； RL是您的工作:)

### Goals of this playbook 本剧本的目标

The goal is to help you do your job as DRI—  
目的是帮助您作为DRI工作 -

- Make your project go quickly:  
	使您的项目快速发展：
	- Participants deeply understand the root goal and can autonomously choose the most important next things to work on  
		参与者深入了解根目标，并可以自主选择最重要的下一步工作
	- People have “situational awareness” of what other people are working on, learn about relevant updates quickly, and coordinate quickly when needed  
		人们对其他人的工作有“情境意识”，快速学习相关更新，并在需要时迅速协调
	- People get quick feedback on their work  
		人们快速就他们的工作反馈
	- If things aren’t going fast enough, you (the DRI) can notice and course-correct quickly  
		如果事情进展不够快，您（DRI）会注意到并迅速正确
- “Play well with others:” “和别人一起玩：”
	- Observers can figure out where to go to follow along  
		观察者可以弄清楚去哪里跟随
	- Adjacent or intersecting people/projects don’t miss important updates or get caught by surprise  
		邻近或与人相交的人/项目不会错过重要的更新或惊讶
	- People notice quickly if the project is behind or off-track, and can identify opportunities to help  
		人们很快注意到该项目在落后还是偏离轨道，并可以确定机会来帮助

—without adding too much overhead:  
\- 没有添加太多的开销：

- <1 hour of setup to make a working doc, schedule a weekly meeting, etc.  
	％3C1小时的设置以制作工作文件，安排每周会议等等。
- 30 min/week of meetings 30分钟/周的会议
- 15-30 min/week to write an update  
	15-30分钟/周写更新

(Note: *being DRI* will still unavoidably add some overhead—e.g. you’ll have to track what other people are doing, delegate work, unblock people, set and communicate goals, etc. The goal is specifically for the *process/paperwork* to be minimal.)  
（注意： *DRI* 仍然不可避免地会添加一些开销 - EG您必须跟踪其他人在做什么，委派工作，解冻人员，设定和传达目标等。目标是专门用于最小化的 *过程/文书工作* 。）

### Weekly meeting 每周会议

You should schedule at least one 30-minute weekly meeting with everyone working on the project.  
您应该至少安排一次每周30分钟的会议，与该项目的每个人进行。

The goal of this meeting is to (1) be a backstop for any coordination that needs to happen and didn’t happen asynchronously; (2) be an efficient way to create [common knowledge](https://en.wikipedia.org/wiki/Common_knowledge_%28logic%29) of goals, updates, etc.; (3) help you track whether things are going well.  
这次会议的目的是（1）成为任何需要进行且没有异步发生的协调的后备； （2）是创建目标，更新等 [共同知识](https://en.wikipedia.org/wiki/Common_knowledge_%28logic%29) 的有效方法； （3）帮助您跟踪情况是否顺利。

- Starter-kit agenda:首发-Kit议程：
	- \[5m\] DRI reviews major updates from last week and sets goals for next week  
		\[5m\] DRI评论上周的重大更新，并设定下周的目标
	- \[10m\] Silent write and comment on discussion topics  
		\[10m\]无声写和评论讨论主题
	- \[10m\] Synchronous discussion of most important things not addressed during silent write  
		\[10m\]在静音写作过程中对最重要的事情的同步讨论
- Signs that more meetings might help (e.g. a second weekly standup):  
	迹象表明更多的会议可能会有所帮助（例如，第二个每周一次站立）：
	- you have a very tight deadline and can’t afford to lose time  
		您的截止日期非常紧，无法浪费时间
	- people aren’t working on the most important thing  
		人们不是在做最重要的事情
	- people need feedback frequently  
		人们经常需要反馈
	- people step on each others’ toes or miss opportunities to help each other out  
		人们踏上彼此的脚趾或错过机会互相帮助
	- if you just like hanging out with each other:)  
		如果您只是喜欢互相闲逛:)

### Landing page / working doc着陆页 /工作文档

It’s really helpful for discoverability and wayfinding to have a single “master doc” with all the most important info about a project. As you loop more people in, they can read the doc to get up to speed. And anyone who thinks “I wonder how X is going” can stop by there to find out.  
对于可发现性和寻路的人确实有帮助，拥有一个“主文档”，其中包含有关项目的所有最重要信息。当您循环更多的人时，他们可以阅读DOC以迅速发展。任何认为“我想知道X的情况”的人都可以在那里停下来找出答案。

Create a doc for your workstream with:  
为您的工作流创建一个文档：

- A [go/ link](https://www.golinks.io/) in the name (if a subproject, maybe use go/project/subproject)  
	名称中的 [GO/链接](https://www.golinks.io/) （如果子标记，则可以使用GO/Project/subproject）
	- → This makes it easier to find quickly (search is kinda rough)  
		→这使得更容易找到快速（搜索有点粗糙）
- A clear description of a **concrete top level goal** and how it fits into broader goals  
	清晰地描述 **具体的顶级目标** 以及如何适应更广泛的目标
	- → This is critical info for participants, so they can autonomously prioritize the most important things; and for observers, so that they know what outcome to expect.  
		→对于参与者来说，这是关键信息，因此他们可以自主优先考虑最重要的事情；对于观察者而言，他们知道会有什么结果。
- **Staffing:** A list of people working on the project, your name as the DRI, and a link to the slack channel that’s being used for discussion  
	**人员配备：** 从事该项目的人列表，您的名字为DRI，以及用于讨论的Slack频道的链接
- **Links:** A short list of relevant links at the top (work trackers, the project’s Slack channel, major design docs, etc.). If needed, a longer “docs / see also” section later links to relevant docs.  
	**链接：** 顶部的相关链接的简短列表（工作跟踪器，项目的松弛频道，主要设计文档等）。如果需要，则更长的“文档 /参见”部分后来链接到相关文档。
	- → It’s really easy to lose track of relevant docs otherwise!  
		→否则，丢失相关文档真的很容易！
- A **roadmap** section with intermediate goals and target dates  
	具有中间目标和目标日期的 **路线图** 部分
	- → See the [section on plans](https://www.benkuhn.net/pjm/#plan--roadmap--milestones); these will help people understand what the overall shape of the project is expected to be.  
		→请参阅 [计划部分](https://www.benkuhn.net/pjm/#plan--roadmap--milestones) ；这些将帮助人们了解该项目的整体形状。
- A section for “running notes” containing meeting notes from your weekly meetings (and any other ad-hoc meetings) and [broadcast updates](https://www.benkuhn.net/pjm/#weekly-broadcast-updates)  
	“运行笔记”部分，其中包含您每周会议（以及任何其他临时会议）和广播更新中的会议笔记
	- → This really helps observers and new-joiners get up to speed!  
		→这确实有助于观察者和新访问者提高速度！
- I like maintaining a list of **important open questions / uncertainties/ risks** and updating it over time. This helps me stay focused on removing risk from the project as quickly as possible.  
	我喜欢保留 **重要的开放问题 /不确定性 /风险** 列表，并随着时间的推移对其进行更新。这可以帮助我专注于尽快消除项目的风险。

If it’s part of a larger project, your doc should be nested within the larger project’s working doc.  
如果它是一个较大项目的一部分，则应将您的文档嵌套在大型项目的工作文档中。

If this ends up being too much for one doc, you can fork these out into sub-docs (esp. running notes and updates).  
如果最终对于一个文档来说太多了，则可以将其分配到子销售中（尤其是运行的笔记和更新）。

### Plan / roadmap / milestones计划 /路线图 /里程碑

- In your working doc, include a section with some intermediate goals and dates by which you hope to accomplish them.  
	在您的工作文档中，包括一个带有一些中间目标和日期的部分，您希望通过这些目标和日期完成。
	- → This is helpful mostly for noticing you’re off track or behind without getting frog-boiled.  
		→这主要有助于注意到您偏离轨道或落后，而不会被青蛙沸腾。
	- → Or noticing when you need to make a direction change because the intermediate goals don’t seem good anymore.  
		→或者在需要改变方向时注意到，因为中间目标看起来不再好。
- You might feel some pressure to add false certainty or precision, but avoid this and be honest about your uncertainty instead. For a lot of research projects it’s hard to plan more than a couple weeks ahead. You can make the milestones fuzzier / more aspirational beyond that, or just drop them.  
	您可能会感到增加错误的确定性或精确度的压力，但要避免这种压力，并对您的不确定性诚实。对于许多研究项目，很难计划多个星期。除此之外，您可以使里程碑更加绒毛 /更具志向意义，或者只是将它们放下。
	- I often find it helpful to phrase milestones in probabilitis and distributions (e.g. “my 90% confidence interval for this date is X-Y” or “I think there’s a 75% chance this technique works”)  
		我经常发现对概率和分布中的里程碑这是有帮助的（例如，“我的90％置信区间是XY”或“我认为此技术有75％的机会有效”））

### Who’s working on what 谁在研究什么

- You should have something somewhere that describes what people are working on.  
	您应该在某个地方描述人们正在从事的工作。
- The minimum viable version of this is a list of what people are working on in your working doc.  
	最低版本的最低版本是人们在工作文档中正在从事的工作的列表。
	- If you end up with a large set of tasks and a big backlog, maybe use a checklist and/or move to a subdoc.  
		如果您最终完成了大量的任务和大型积压，则可以使用清单和/或移至案例。
- **Stack rank your work list.** It’s really important for people to understand priorities!  
	**堆栈排名您的工作清单。** 对于人们来说，了解优先事项非常重要！
- If there’s more different people/TODOs, I suggest using some app to make a kanban board with “backlog” / “up next” / “in progress” / “done” columns.  
	如果有更多不同的人 /待办事项，我建议使用一些应用程序制作具有“积压” /“下一步” /“正在进行的” /“完成” /“ DONE”列的看板板。
	- This is probably most helpful for more deterministic/plannable projects where there’s a clear backlog + set of future tasks, and a lot of things you need to remember to do.  
		这可能最有用，对于更确定性/可计划的项目，那里有明确的积压 +将来的任务集，以及您需要记住的许多事情。
- If you have an external task tracker, link it in the wiki section of the working doc.  
	如果您有外部任务跟踪器，请在工作文档的Wiki部分链接它。

### Slack norms 松懈的规范

- Have conversations about the project in a Slack channel (not DMs).  
	在Slack频道（而不是DMS）中就项目进行对话。
	- Reference the channel in your working doc.  
		在您的工作文档中引用频道。
	- Link the working doc in the Slack channel bookmarks.  
		在Slack Channel书签中链接工作文档。
- Cross-post notebook posts and experiment write-ups into the channel so observers don’t have to follow tons of notebook channels.  
	跨媒体笔记本电脑帖子和实验文章中的介绍，因此观察者不必跟随大量的笔记本频道。
- **Do not use DMs.** These make it hard to make info discoverable or share it further.  
	**请勿使用DMS。** 这些使信息难以发现或进一步共享。
	- If people send you important stuff in a DM, ask them to put it in the project channel.  
		如果人们将重要的东西发送到DM中，请他们将其放入项目渠道。
	- If you need confidentiality, make a private channel.  
		如果您需要机密性，请进行私人渠道。
- **Avoid centithreads.** Most ≥10-message Slack threads would be better as a ~5-minute Tuple.  
	**避免使用centithreads。** 大多数≥10个序列的松弛线将更好地作为一个约5分钟的元组。
	- (This is hard to do with people who are in tons and tons of meetings like execs. But you should try to do it for others.)  
		（这很难与像执行者这样的大量会议和大量会议的人进行。但是您应该尝试为他人做。）
	- If you end up with a centithread, assume nobody will read it; post a summary back to the channel afterwards.  
		如果您最终获得了centithread，则假设没有人会读它。之后将摘要回到频道。
- Bias towards fewer, larger, noisier channels. The right time to create a channel is when discussion is either not happening, or getting lost.  
	偏向较少，更大，更嘈杂的渠道。创建渠道的合适时机是讨论不进行或迷失时。
	- → Too many slack channels makes it harder to manage membership, decide where to put things, or find where discussion is happening.  
		→太多的松弛渠道使管理会员资格，决定将事物放在哪里或找到讨论的发生更加困难。
- Channel organization and membership matters. Invest in routing conversations to the right place and curating the channel “architecture.”  
	渠道组织和会员事务。投资将对话路由到正确的位置，并策划“建筑”频道。

### Weekly broadcast updates 每周广播更新

- Once a week, probably either just before or just after your weekly meeting, write up a **brief** update for a broader audience with:  
	每周一次，大概是在您每周会议之前或之后，请为更广泛的受众写下一个 **简短的** 更新：
	- The overall vibe 整体氛围
	- What’s changed since last update  
		自上次更新以来发生了什么变化
	- What’s coming up next 接下来会发生什么
- When writing these updates, optimize for **signal to noise ratio**.  
	编写这些更新时，请优化 **信号与噪声比** 。
	- Err towards concision 犯错
	- No “we worked on X”—tell me “we accomplished Y” or “we learned Z”  
		没有“我们在X上工作” - 告诉我“我们成就Y”或“我们学习Z”
	- Remember your audience (= people not familiar with the project)  
		记住您的听众（=不熟悉该项目的人）
	- State things crisply and concretely (“X improves eval Y by Z points,” not “we got X working”)  
		陈述事物清晰而具体（“ x通过z点提高评估”，而不是“我们让X起作用”）
	- Leave out anything that’s not actionable—you don’t need to be exhaustive  
		遗漏任何不可行的东西 - 您不需要详尽
- Post the update in your project Slack channel, and cross-post it to other relevant channels (e.g. a larger “megaproject” channel) if necessary.  
	在您的项目Slack频道中发布该更新，然后将其交叉到其他相关频道（例如，如有必要）。
	- If your project is part of a larger megaproject, these updates might feed into something broader like a weekly meeting of DRIs or an aggregated status update.  
		如果您的项目是较大的大型项目的一部分，那么这些更新可能会带入更广泛的内容，例如每周的DRI或总体状态更新。

### Retrospectives 回顾

- Every so often, step back and ask “how could the last X weeks have gone better?”  
	每隔一段时间，退后一步，问：“最近的X周怎么会更好？”
	- Frequency depends on how much there is going on—every 2 weeks is good if there’s a lot, maybe every 4-8 weeks for smaller projects  
		频率取决于发生了多少频率 - 如果有很多，每2周都很好，也许每4-8周一次较小的项目
- Suggested meeting format 建议的会议格式
	- Friday afternoon 星期五下午
	- \[13 min\] Async brainstorm 2 lists of items: “what went well” / “what we could improve”  
		\[13分钟\]异步集思广益2个项目列表：“一切顺利” /“我们可以改进的东西”
	- \[2 min\] Dedupe topics and emoji vote by putting:heavy\_plus\_sign: next to ones you agree with  
		\[2分钟\] dedupe主题和表情符号投票：
	- Sort “what we could improve” by highest votes  
		按最高选票对“我们可以改进的东西”进行排序
	- \[10 min\] Synchronous discussion of top points (either highest voted or flagged by DRI); figure out action items  
		\[10分钟\]对高点的同步讨论（DRI的投票最高或标记）；找出动作项目

*Thanks to Kelley Rivoire for many thoughtful comments on a draft!  
感谢Kelley Rivoire对选秀的许多深思熟虑的评论！*