---
{"dg-publish":true,"permalink":"/05.技能库/Obsidian/内容分享/Obsidian Digital Garden 指南：从笔记到个人网站的完整实践/","tags":["gardenEntry"]}
---


Obsidian Digital Garden 项目为 Obsidian 用户提供了一个强大而灵活的工具，旨在将个人知识库中的笔记内容发布到互联网上，构建一个完全由用户掌控并可自由定制的个人在线空间，即“数字花园” 1。这个概念强调的不仅仅是静态的笔记展示，更是一个动态的、不断演进的知识网络，用户可以像培育真实花园一样，精心打理和扩展自己的在线知识体系。该项目通过与 GitHub 和 Vercel 等免费托管平台的集成，极大地降低了个人建立和维护在线知识分享平台的门槛，使得更多人能够自由地分享和展示自己的思考与发现 1。

## **1\. 理解 Obsidian Digital Garden**

### **1.1. Obsidian Digital Garden 项目的核心目的与概念**

Obsidian Digital Garden 的核心目标是让用户能够**将他们的笔记免费发布到网络上，构建属于自己的个人花园** 1。这一概念中的“数字花园”指的是一个个性化的在线空间，用于展示和分享源自 Obsidian 的笔记内容。它特别强调用户对内容的完全控制权和高度的可定制性，允许用户根据个人偏好调整数字花园的方方面面 1。

这种模式赋予了用户对其在线内容前所未有的所有权。与传统的、结构更为固化的发布系统不同，数字花园鼓励一种持续演进的知识管理方式。用户可以不断地添加、修改和连接笔记，使其在线空间如同一个真实的植物园一样，随着时间的推移而生长和繁茂。这种设计理念使得数字花园成为一个真正个性化、动态化的知识表达与分享平台。

此外，该项目通过利用免费的托管服务（如 Vercel、GitHub Pages 等），致力于普及个人在线知识库的建立 1。这使得任何拥有 Obsidian 笔记的用户，无论其技术背景如何，都能够以极低的成本（甚至免费）拥有一个属于自己的、可公开访问的知识网站。这不仅推动了知识分享的民主化，也为个体在数字时代建立和管理个人品牌提供了新的途径。

### **1.2. Obsidian 用户的主要功能与优势**

Obsidian Digital Garden 插件为 Obsidian 用户提供了丰富的功能，旨在确保从本地笔记到在线数字花园的转换尽可能无缝且功能完整。这些功能不仅支持基础的 Markdown 语法，还深度集成了 Obsidian 的许多核心特性和常用插件功能，从而在网页端最大程度地还原用户在 Obsidian 中的笔记体验。

主要功能包括 1：

* **基础 Markdown 语法**：支持所有标准的 Markdown 格式。  
* **笔记链接**：支持 Obsidian 的 \[\[双向链接\]\] 语法，方便在笔记间跳转。  
* **Dataview 查询**：支持以代码块、行内和 dataviewjs 形式嵌入动态查询结果。  
* **反向链接**：在发布的笔记页面显示指向当前笔记的其他笔记。  
* **Obsidian 主题**：允许用户在数字花园中使用其偏好的 Obsidian 主题。  
* **样式设置**：提供自定义样式的能力。  
* **本地关系图谱**：展示当前笔记相关的局部知识图谱。  
* **文件树导航**：提供类似 Obsidian 的文件浏览器，方便访客浏览。  
* **全局搜索**：允许访客在整个数字花园中搜索内容。  
* **Callouts/Admonitions**：支持 Obsidian 风格的提示框。  
* **嵌入 Excalidraw 绘图**：支持嵌入和转译 Excalidraw 绘图。  
* **嵌入图片**：支持嵌入和转译图片。  
* **嵌入笔记（Transclusion）**：支持将一个笔记的内容嵌入到另一个笔记中。  
* **代码块**：支持多种语言的代码块高亮。  
* **MathJax**：支持 LaTeX 数学公式渲染。  
* **高亮文本**：支持 \<mark\> 标签高亮。  
* **脚注**：支持 Markdown 脚注。  
* **Mermaid 图表**：支持使用 Mermaid 语法创建图表。  
* **PlantUML 图表**：支持使用 PlantUML 语法创建图表。

**表1：Obsidian Digital Garden 功能概览**

| 功能特性 | 描述 | 优势/使用说明 |
| :---- | :---- | :---- |
| Dataview 查询 | 支持嵌入动态的笔记查询结果 1 | 动态展示笔记集合，如项目列表、读书笔记等，无需手动更新。 |
| Obsidian 主题 | 可应用用户在 Obsidian 中使用的主题 1 | 保持本地与在线视觉体验的一致性，增强品牌感。 |
| 反向链接 | 显示链接到当前笔记的其他笔记 1 | 帮助访客发现相关内容，理解知识点之间的联系。 |
| 嵌入 Excalidraw/图片 | 支持直接嵌入 Excalidraw 绘图和各类图片 1 | 丰富内容表达形式，使数字花园更具视觉吸引力。 |
| Callouts/Admonitions | 支持 Obsidian 风格的提示框，如 \[\!info\], \[\!warning\] 1 | 突出重要信息，改善内容组织和可读性。 |
| 文件树导航与全局搜索 | 提供文件树导航和全局内容搜索功能 1 | 提升用户体验，方便访客快速定位和发现感兴趣的内容。 |
| 数学公式与图表支持 | 支持 MathJax, Mermaid, PlantUML 1 | 满足学术、技术类笔记的复杂排版需求。 |

这些特性的全面支持，意味着用户在 Obsidian 中精心构建的笔记结构、视觉样式和动态内容，都可以在其在线数字花园中得到高度保真的再现。这不仅仅是将 Markdown 文件转换为 HTML 页面，更是将 Obsidian 的核心体验延伸到了网络上，保留了笔记中丰富的上下文信息和交互性。对于希望其在线内容能真实反映其 Obsidian 工作流的用户而言，这是一个显著的优势。

### **1.3. 从 Obsidian 发布内容：此工具是否适合您？**

是的，Obsidian Digital Garden 工具明确支持从 Obsidian 发布和分享内容 1。其设计初衷便是为 Obsidian 用户提供一个便捷的途径，将他们的笔记转化为一个可公开访问的个人网站。

内容的分享是基于**单篇笔记**进行的 1。用户需要通过在特定笔记的元数据（frontmatter）中添加 dg-publish: true 标记来指定该笔记是否发布。没有此标记的笔记将不会出现在数字花园中。这种精细化的控制赋予了用户极大的灵活性，可以自主决定哪些内容公开，哪些内容保留私有。


然而，这种基于单篇笔记的发布机制也意味着用户需要承担相应的管理责任。当一篇笔记被标记为发布时，如果它链接到其他笔记，这些被链接的笔记并不会自动发布 1。用户必须手动为每一个希望公开的被链接笔记添加 dg-publish: true 标记。如果忽略了这一步骤，访客点击链接时将会看到一个提示页面，表明目标笔记不存在 1。因此，维护链接的完整性和内容的连贯性，需要用户在发布时保持细致和警惕。

## **2\. 初始设置与配置**

成功部署和使用 Obsidian Digital Garden 需要一些前期准备和细致的配置工作。本章节将指导您完成所有必要的步骤。

### **2.1. 前提条件：开始之前您需要准备什么**

在开始配置 Obsidian Digital Garden 之前，请确保您已具备以下条件：

1. **Obsidian**: 您需要在您的计算机上安装并运行 Obsidian 笔记软件。这是管理和编辑您数字花园内容的基础 1。  
2. **GitHub 账户**: 您需要一个 GitHub 账户。数字花园的内容将存储在您 GitHub 账户下的一个仓库中，并通过 GitHub 进行版本控制和同步 1。  
3. **Vercel 账户 (推荐)**: 虽然有其他托管选项，但 Vercel 是官方推荐且集成最为便捷的免费托管平台。您可以使用您的 GitHub 账户直接注册 Vercel 1。

这些前提条件表明，Obsidian Digital Garden 并非一个完全独立的系统，而是巧妙地构建并集成于现有且广受开发者欢迎的生态系统之上。通过利用 GitHub 的版本控制和代码托管能力，以及 Vercel 等平台的自动化部署和全球分发网络，该插件为用户提供了稳定、可扩展且易于维护的发布方案，同时将复杂的基础设施管理工作从最终用户和插件开发者那里剥离出去。

### **2.2. 在 Obsidian 中安装和配置 Digital Garden 插件**

安装和配置 Digital Garden 插件是连接您的 Obsidian 笔记库与在线数字花园的关键步骤。

1. **安装插件**:  
   * 打开 Obsidian。  
   * 进入“设置” \> “第三方插件”。  
   * 确保“安全模式”已关闭。  
   * 点击“社区插件”旁的“浏览”按钮。  
   * 在搜索框中输入 "Digital Garden"。  
   * 找到 Ole Eskild Steensen 开发的 "Digital Garden" 插件，点击“安装”，然后点击“启用” 3。  
2. **配置插件**:  
   * 插件启用后，在 Obsidian 设置的左侧面板中找到 "Digital Garden" 插件的设置项。  
   * 您需要填写以下三个**必填**设置项 1：  
     * **GitHub username**: 您的 GitHub 用户名。  
     * **Repository name**: 您将在下一步（通过 Vercel 部署或手动创建）用于存放数字花园内容的 GitHub 仓库名称（例如 my-digital-garden）。  
     * **GitHub token**: 您在后续步骤中生成的 GitHub 个人访问令牌。  
   * 其他选项为可选设置，您可以暂时保留默认值，待熟悉后再进行调整 1。

这种设计将核心功能所需的配置项减至最少，旨在帮助用户快速上手并成功发布第一篇笔记。通过简化初始设置流程，降低了新用户的入门门槛，同时为有经验的用户保留了通过可选设置进行深度定制的灵活性。

### **2.3. 生成并保护您的 GitHub 访问令牌**

GitHub 个人访问令牌 (Personal Access Token, PAT) 允许 Digital Garden 插件代表您向您的 GitHub 仓库推送更改（例如发布新的笔记或更新现有笔记）。为了安全起见，推荐使用具有精细化权限的令牌。

**创建步骤** 1：

1. 登录您的 GitHub 账户。  
2. 导航至令牌创建页面：通常在 Settings \> Developer settings \> Personal access tokens \> Fine-grained tokens。点击 "Generate new token"。  
3. **配置令牌**：  
   * **Token Name**: 给您的令牌起一个描述性的名称，例如 YYYY-Digital Garden (将 YYYY 替换为当前年份)。  
   * **Expiration**: 选择一个合适的过期时间，例如一年，或者根据您的安全策略选择。GitHub 也提供了“No expiration”选项，但定期更新令牌是更安全的做法。  
   * **Description**: 添加描述，如 "Publishing content to the digital garden"。  
   * **Resource owner**: 选择您自己。  
   * **Repository access**: 选择 "Only select repositories"，然后从下拉列表中选择您为数字花园创建的仓库。  
   * **Permissions**: 这是最关键的一步。您只需要授予以下两项权限：  
     * **Contents**: 访问权限设置为 Read and write。  
     * **Pull requests**: 访问权限设置为 Read and write。（某些较新的 GitHub Actions 工作流可能不需要此权限，但为了插件的通用性，建议添加）。  
4. 点击 "Generate token"。  
5. **复制令牌**: GitHub 将显示生成的令牌。**请立即复制此令牌并将其存放在安全的地方。一旦离开此页面，您将无法再次看到完整的令牌。**  
6. 将复制的令牌粘贴到 Obsidian Digital Garden 插件设置中的 "GitHub token" 字段。

**表2：GitHub 细粒度个人访问令牌 (PAT) 权限配置**

| 令牌设置 | 推荐值/设置 | 说明 |
| :---- | :---- | :---- |
| Token Name | YYYY-Digital Garden (或自定义) | 便于识别令牌用途。 |
| Expiration | 自定义 (例如 1 年) | 出于安全考虑，建议设置过期时间并定期更新。 |
| Resource owner | 您自己 | 令牌将关联到您的账户。 |
| Repository access | "Only select repositories" \-\> 选择您的数字花园仓库 | **核心安全设置**：将令牌权限严格限制在指定的仓库，遵循最小权限原则。 |
| **Permissions** |  |  |
| └─ Contents | Access: Read and write | 允许插件读取和写入（创建/更新）仓库中的笔记文件。 |
| └─ Pull requests | Access: Read and write | 允许插件创建拉取请求（例如，在更新站点模板时使用）。 |

采用细粒度个人访问令牌并严格限制其权限范围，是确保账户安全的重要措施 1。Digital Garden 插件的文档和设置流程引导用户采用这种更为安全的方式，体现了对用户数据安全的重视。虽然用户仍需正确配置令牌，但这种引导有助于最大限度地降低潜在风险。

## **3\. 发布您的内容：从 Obsidian 到网络**

完成初始设置后，您就可以开始将 Obsidian 中的笔记发布到您的数字花园了。核心机制是通过笔记的 frontmatter（元数据）进行控制。

### **3.1. 选择待发布的笔记：使用 Frontmatter (dg-publish, dg-home)**

要在您的数字花园中发布特定笔记，您需要在该笔记文件的顶部添加特定的 frontmatter 属性。Frontmatter 是位于文件最开始，由三条短横线 (---) 包裹的 YAML 格式文本块 1。

* 发布笔记 (dg-publish):  
  要发布一篇笔记，请在其 frontmatter 中添加 dg-publish: true。例如：  
  YAML  
  \---  
  dg-publish: true  
  \---

  只有包含此属性并设置为 true 的笔记才会被发布到您的数字花园中 1。如果笔记没有这个属性或设置为 false，它将保持私有，不会被发布。  
* 设置主页 (dg-home):  
  您可以指定一篇笔记作为数字花园的入口或主页。为此，请在该笔记的 frontmatter 中添加 dg-home: true。这篇笔记同时也需要 dg-publish: true 才能被发布。例如：  
  YAML  
  \---  
  dg-home: true  
  dg-publish: true  
  \---

  dg-home: true 属性只需要添加到**一篇**笔记中 1。  
* Obsidian 属性 (Properties):  
  从 Obsidian 1.4.x 版本开始，引入了“属性”功能，它提供了一个更用户友好的界面来管理 frontmatter。您可以通过命令面板（Ctrl/Cmd \+ ;）或笔记菜单中的“添加文件属性”选项来添加 dg-publish 和 dg-home 作为复选框类型的属性，并勾选它们 3。其效果与手动编辑 frontmatter 相同。  
* **Frontmatter 语法注意事项**:  
  * 确保 frontmatter 块以三个短横线 (---) 开始，并以三个短横线 (---) 结束 1。  
  * 如果在复制粘贴示例代码时，frontmatter 的开头和结尾出现了反引号 (\`\`\`)，请务必删除它们 1。

这种依赖 frontmatter 属性来控制发布状态的设计，使得 Obsidian 笔记本身成为了发布信息的唯一真实来源。这样做的好处是元数据与内容紧密结合，易于管理。然而，这也意味着 frontmatter 中的任何笔误或遗漏（例如，dg-publish: true 拼写错误，或忘记为链接到的笔记添加此属性）都会直接影响最终发布的网站。这种紧耦合机制功能强大，但要求用户在编辑 frontmatter 时务必准确。

### **3.2. 发布工作流：命令与流程**

一旦您通过 frontmatter 标记了希望发布的笔记，接下来的发布操作非常简单，直接在 Obsidian 内部即可完成：

1. **打开命令面板**: 在 Obsidian 中，按下 Ctrl+P (Windows/Linux) 或 Cmd+P (Mac) 打开命令面板 1。  
2. **执行发布命令**: 在命令面板中搜索并选择 "Digital Garden: Publish Single Note" 命令，然后按 Enter键执行 1。

插件会将当前打开的、且 frontmatter 中包含 dg-publish: true 的笔记（以及其依赖的本地图片等资源）处理并推送到您在插件设置中配置的 GitHub 仓库。随后，像 Vercel 这样的托管平台会自动检测到仓库的更新，并重新构建和部署您的数字花园网站。通常在一两分钟后，您就可以在您的网站 URL 上看到更新后的内容了 2。

这种“发布单篇笔记”的命令设计，鼓励用户采用增量和迭代的方式来构建其数字花园。用户可以专注于一篇笔记的创作和完善，然后立即发布并在线预览效果，再接着处理下一篇。这避免了一次性处理大量笔记的压力，使得内容发布流程更加灵活和高效。

### **3.3. 管理和更新您已发布的数字花园**

数字花园的内容和外观并非一成不变，您需要了解如何更新笔记、取消发布以及更新站点本身的模板。

* 更新已发布的笔记:  
  如果您修改了一篇已经发布的笔记，只需再次对该笔记执行 "Digital Garden: Publish Single Note" 命令即可。插件会将更新后的内容推送到 GitHub 仓库，进而触发网站的重新部署。  
* 取消发布笔记:  
  如果您希望从数字花园中移除某篇笔记（但仍在 Obsidian 笔记库中保留该笔记），操作如下 3：  
  1. 在该笔记的 frontmatter 中，将 dg-publish 的值改为 false，或者直接删除 dg-publish: true 这一行（或在 Obsidian 属性编辑器中取消勾选 dg-publish）。  
  2. 打开 Obsidian 命令面板，找到并执行 "Digital Garden: Publication Center" 命令（如果可用，具体命令可能因插件版本而异，或参考插件设置中的相关删除功能）。  
  3. 在 Publication Center 或相关界面中，通常会有删除已取消发布笔记的选项，例如 "Delete notes from garden" 按钮。点击此按钮，插件会处理从 GitHub 仓库中移除相应文件的操作。  
* 更新站点模板:  
  Digital Garden 插件的开发者会不时更新站点模板，以引入新功能、修复错误或改进设计。要将您的数字花园更新到最新的模板，请按以下步骤操作 1：  
  1. 在 Obsidian 的 Digital Garden 插件设置中，找到名为 "Site Template" 的部分。  
  2. 点击 "Manage site template" 按钮。  
  3. 在弹出的窗口中，您会看到 "Update site to latest template" 的选项和一个 "Create PR" (创建拉取请求) 按钮。  
  4. 点击 "Create PR"。插件会在您的 GitHub 仓库中创建一个新的分支，其中包含模板的更新，并自动向您的主分支发起一个拉取请求 (Pull Request)。  
  5. 插件通常会提供该拉取请求的 URL。打开此 URL，您可以在 GitHub 上审查更改。  
  6. Vercel (或您使用的类似平台) 通常会自动为这个拉取请求构建一个预览版本的站点。您可以在合并前访问此预览站点，检查更新是否会破坏您现有的内容或自定义样式 1。  
  7. 确认无误后，在 GitHub 的拉取请求页面上点击 "Merge pull request" 按钮，将更新合并到主分支。您的数字花园网站随后会自动使用新模板重新部署。

这种将内容更新（通过发布命令直接推送）与模板更新（通过拉取请求进行审查和合并）区分开来的机制，是一个优秀的设计。内容更新频繁且通常由用户直接驱动，而模板更新可能涉及更复杂的技术变更，甚至可能引入不兼容的改动。通过 PR 流程，用户可以在模板更新正式生效前进行预览和测试，有效避免了因模板升级导致网站意外损坏的风险，保障了数字花园的稳定运行。

## **4\. 部署深度解析：托管您的数字花园**

选择合适的托管平台是建立数字花园的关键一步。Obsidian Digital Garden 支持多种部署方案，从官方推荐的 Vercel 到 GitHub Pages、Netlify 以及完全自托管。

**表3：部署平台对比**

| 平台 | 主要设置方法 | 设置复杂度 | 主要优点 | 主要缺点/注意事项 | 推荐用户 |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Vercel | "Deploy to Vercel" 按钮，自动化部署 1 | 低 | 设置最简单，快速启动，官方推荐，优秀的性能和免费额度。 | 可能与 Vercel 平台绑定。 | 初学者，希望快速上线的用户。 |
| GitHub Pages | GitHub Actions 工作流 5 | 中 | 免费，与 GitHub 生态紧密集成，版本控制方便。 | **仓库命名有严格限制 (\<username\>.github.io)** 5，否则资源路径可能错误。 | 深度使用 GitHub 生态的用户，对仓库命名规范不敏感的用户。 |
| Netlify | "Deploy to Netlify" 按钮或手动配置 6 | 低至中 | 灵活的构建过程，丰富的功能（如重定向、表单处理），慷慨的免费额度。 | 曾是默认选项，现优先级低于 Vercel，部分旧资料可能过时 8。 | 熟悉 Netlify 平台的用户，或需要其特定高级功能的用户。 |
| 自托管 | Express.js, Docker 等 8 | 高 | 完全控制服务器环境、数据和自定义能力，不受第三方平台限制。 | 技术要求高，需自行处理服务器维护、安全、域名、SSL证书、自动更新部署等 8。 | 需要高度定制或对数据有完全控制需求的有经验的技术用户。 |

### **4.1. Vercel：推荐路径 (分步指南，配置)**

Vercel 是 Obsidian Digital Garden 官方推荐的托管平台，以其便捷的“一键部署”功能和优秀的性能著称 1。

**部署步骤**：

1. **确保前提条件满足**：您已拥有 GitHub 账户，并且 Digital Garden 插件已在 Obsidian 中基本配置（至少知道要使用的 GitHub 用户名和计划的仓库名）。  
2. **部署模板到 Vercel**:  
   * 访问 Digital Garden 的官方模板仓库（通常在项目文档中会提供链接，例如 https://github.com/oleeskild/digitalgarden）。  
   * 在该仓库的 README 文件中，找到并点击蓝色的 "Deploy to Vercel" 按钮 1。  
   * 这将引导您到 Vercel 平台。如果您尚未登录 Vercel，系统会提示您使用 GitHub 账户登录或注册。  
   * Vercel 会请求访问您的 GitHub 账户的权限，以便为您创建一个新的仓库（作为模板仓库的副本）并部署它。  
   * 在 Vercel 的界面中，为您的新 GitHub 仓库指定一个名称，例如 my-digital-garden。这个名称将用于您在 Obsidian 插件设置中的 "Repository name" 字段。  
   * 根据 Vercel 的屏幕指示完成后续步骤。Vercel 会自动从您的新 GitHub 仓库拉取代码，执行构建，并将您的数字花园部署到互联网上。部署完成后，Vercel 会提供一个默认的网址 (例如 your-project-name.vercel.app)。  
3. **创建 GitHub 访问令牌**：按照章节 2.3 中的指示，为您的新 GitHub 仓库创建一个具有适当权限的细粒度个人访问令牌。  
4. **配置 Obsidian 插件**:  
   * 返回 Obsidian，打开 Digital Garden 插件的设置。  
   * 填写您的 GitHub 用户名。  
   * 填写您在 Vercel 部署过程中创建的 GitHub 仓库的名称 (例如 my-digital-garden)。  
   * 粘贴您刚刚创建的 GitHub 访问令牌。  
5. **发布第一篇笔记**: 按照章节 3.1 和 3.2 的说明，选择一篇笔记，添加 dg-home: true 和 dg-publish: true 到其 frontmatter，然后使用 "Digital Garden: Publish Single Note" 命令发布。

Vercel 的“一键部署”理念极大地简化了传统网站部署的复杂性，使得非专业开发者也能轻松拥有自己的在线数字花园。这种用户友好的设计是 Vercel 成为推荐平台的主要原因之一。

### **4.2. GitHub Pages：利用 GitHub 的基础设施 (详细设置，工作流 YAML，仓库命名，变通方法)**

GitHub Pages 是 GitHub 提供的免费静态站点托管服务，也是一个流行的选择。但使用 GitHub Pages 部署 Digital Garden 时，有一些关键的配置细节需要特别注意。

**核心要求与配置**：

1. 仓库命名 (至关重要):  
   为了确保 CSS、JavaScript 等静态资源能够正确加载，您的 GitHub 仓库必须命名为 \<username\>.github.io，其中 \<username\> 是您的 GitHub 用户名 5。如果您的仓库使用其他名称（例如 my-digital-garden），那么最终的站点 URL 将是 \<username\>.github.io/my-digital-garden/。在这种情况下，模板中的资源链接（通常是绝对路径，如 /styles/style.css）会解析为 \<username\>.github.io/styles/style.css，导致资源加载失败，页面可能只显示纯文本内容 5。这是 GitHub Pages 处理项目站点（非用户/组织站点）路径的方式所致，并非插件本身的问题。  
2. GitHub Actions 工作流:  
   您需要设置一个 GitHub Actions 工作流来自动化构建和部署过程。以下是两个示例工作流配置 5：  
   * **较早版本的工作流 (可能需要 GH\_TOKEN)**:  
     YAML  
     name: GH Pages  
     on:  
       push:  
         branches: \[ "main" \] \# 或您的主分支名  
       pull\_request:  
         branches: \[ "main" \] \# 或您的主分支名  
     jobs:  
       build:  
         runs-on: ubuntu-22.04  
         strategy:  
           matrix:  
             node-version: \[20\.x\] \# 根据项目依赖选择合适的 Node 版本  
         steps:  
           \- uses: actions/checkout@v3  
           \- name: Use Node.js ${{ matrix.node-version }}  
             uses: actions/setup-node@v3  
             with:  
               node-version: ${{ matrix.node-version }}  
               cache: 'npm'  
           \- run: npm install  
           \- run: npm run build \--if-present  
           \- name: Deploy  
             uses: peaceiris/actions-gh-pages@v3  
             with:  
               publish\_dir:./dist \# 构建输出目录  
               github\_token: ${{ secrets.GH\_TOKEN }} \# 需要在仓库 Secrets 中配置 GH\_TOKEN

     此工作流需要在仓库的 Settings \> Secrets and variables \> Actions 中添加一个名为 GH\_TOKEN 的 Secret，其值为您按照章节 2.3 生成的个人访问令牌。  
   * **较新版本的工作流 (推荐，通常无需额外 GH\_TOKEN Secret)**:  
     YAML  
     name: GH Pages  
     on:  
       push:  
         branches:  
           \- main \# 或您的主分支名  
       workflow\_dispatch: \# 允许手动触发  
       pull\_request:  
     permissions:  
       contents: read  
       pages: write  
       id-token: write  
     concurrency:  
       group: "pages"  
       cancel-in-progress: false  
     jobs:  
       deploy:  
         environment:  
           name: github-pages  
           url: ${{ steps.deployment.outputs.page\_url }}  
         runs-on: ubuntu-latest  
         steps:  
           \- uses: actions/checkout@v4  
           \- name: Setup Node  
             uses: actions/setup-node@v4  
             with:  
               node-version: '20' \# 根据项目依赖选择合适的 Node 版本  
               cache: 'npm'  
           \- run: npm install  
           \- run: npm run build  
           \- name: Setup Pages  
             uses: actions/configure-pages@v5  
           \- name: Upload artifact  
             uses: actions/upload-pages-artifact@v3  
             with:  
               path: 'dist' \# 构建输出目录  
           \- name: Deploy to GitHub Pages  
             id: deployment  
             uses: actions/deploy-pages@v4

     这个更新的工作流使用了 GitHub 官方推荐的新版 Actions (actions/configure-pages@v5, actions/deploy-pages@v4)，并通过 permissions 块为 GITHUB\_TOKEN（由 GitHub Actions 自动提供，无需手动创建 Secret）授予了必要的权限。在某些情况下，您可能需要在仓库设置的 Pages 部分配置构建源为 "GitHub Actions"。

将上述 YAML 内容保存为 .github/workflows/gh-pages.yml (文件名可自定义) 在您的仓库中。

3. 自定义 404 页面:  
   为了确保在直接访问无效链接（例如 yourid.github.io/somegarbage/）时自定义的 404 页面能够正常工作，您需要在您的 src/site/404.njk 文件（或其他模板引擎对应的 404 文件）的顶部添加 permalink: 404.html 5。

仓库命名限制的变通方法 (有局限性) 5:  
如果无法使用 \<username\>.github.io 这样的仓库名，而必须使用如 my-digital-garden 这样的名称，可以尝试在 Digital Garden 插件的设置中配置“路径重写规则 (Manage Rewrite Rules)”。例如，添加一条规则 :my-digital-garden/，这会将 "my-digital-garden" 前缀添加到每个笔记的路径中。然而，这种方法存在一些缺点：

* 通常只有第一条适用的重写规则会生效，可能会干扰其他路径重写需求。  
* 这会在文件路径中引入额外的一层 (例如 mysite.com/my-digital-garden/note-slug 而不是 mysite.com/note-slug)，可能并非期望的效果。  
* 另一种方式是将所有要发布的笔记都放在 Obsidian 仓库的一个名为 my-digital-garden 的文件夹内。

尽管存在变通方法，但遵循 \<username\>.github.io 的仓库命名约定是确保 GitHub Pages 部署顺利的最佳实践。GitHub Pages 的路径处理机制是其部署时的一个关键点，如果未能正确理解和配置，很容易导致部署失败或显示异常。较新版本的 GitHub Actions 工作流简化了权限管理，是目前推荐的自动化部署方式。

### **4.3. Netlify：一个备选平台 (部署步骤，netlify.toml，构建设置)**

Netlify 是另一个功能强大的静态站点托管平台，也曾是 Obsidian Digital Garden 项目早期的默认推荐 8。尽管现在 Vercel 的优先级更高，但 Netlify 仍然是一个完全可行的部署选项，特别是对于已经熟悉其生态系统的用户。

**部署步骤与配置**：

1. **通过 "Deploy to Netlify" 按钮 (如果模板提供)**:  
   * Digital Garden 的官方文档或模板仓库有时会提供 "Deploy to Netlify" 按钮 6。点击此按钮将引导您完成类似 Vercel 的自动化部署流程：连接 GitHub 账户，创建新仓库副本，Netlify 自动构建和部署。  
2. **手动从 Git 仓库部署**:  
   * 如果您已经将 Digital Garden 模板（例如 oleeskild/digitalgarden）克隆或创建为自己的 GitHub 仓库，可以登录 Netlify，选择 "New site from Git" 9。  
   * 选择 GitHub作为 Git 提供商，授权 Netlify 访问您的仓库。  
   * 选择您的 Digital Garden 仓库。  
   * **构建设置**: Netlify 通常会自动检测项目类型。对于基于 Eleventy（Digital Garden 底层使用的静态站点生成器）的项目，Netlify 可能会建议构建命令 eleventy 和发布目录 \_site 10。然而，Obsidian Digital Garden 项目通常使用 npm run build 作为构建命令，其输出目录是 dist。您需要确保 Netlify 的构建设置与项目实际配置一致。  
     * **Build command**: npm run build  
     * **Publish directory**: dist (此设置可在项目的 netlify.toml 文件中指定，或者在 Netlify 的部署设置界面中手动配置)  
     * **Functions directory** (如果使用 Netlify Functions，本项目默认不直接依赖): 通常是 netlify/functions。  
   * 点击 "Deploy site"。Netlify 将拉取代码，执行构建命令，并将 dist 目录的内容部署到其 CDN。  
3. netlify.toml 文件:  
   Digital Garden 模板仓库 (oleeskild/digitalgarden) 通常包含一个 netlify.toml 文件 7。这是一个配置文件，允许您定义构建设置、重定向规则、插件等。如果您的仓库中有此文件，Netlify 会自动读取并应用其中的配置。例如，netlify.toml 中可以这样指定构建设置：  
   Ini, TOML  
   \[build\]  
     command \= "npm run build"  
     publish \= "dist"  
     \# functions \= "netlify/functions" \# 如果需要

   \# \[\[redirects\]\]  
   \#   from \= "/old-path"  
   \#   to \= "/new-path"  
   \#   status \= 301

由于项目的主要焦点已转向 Vercel，部分围绕 Netlify 的社区讨论或旧文档可能已过时 8。例如，早期版本可能依赖 Netlify Functions 进行搜索，而新版本则采用客户端搜索方案（如 FlexSearch），这可能导致在参照旧指南时出现 netlify/functions/search/search.js 模块找不到的错误 8。尽管如此，Netlify 凭借其强大的构建能力和丰富的功能集，对于有特定需求的用户来说，仍然是一个可靠的选择。

### **4.4. 自托管：完全掌控 (使用 Express/Docker 的选项，关键注意事项)**

对于希望对其数字花园拥有完全控制权、不受第三方平台限制的技术用户，自托管是一个可行的选择。这通常意味着您需要在自己的服务器上运行必要的软件来构建和提供站点服务。

**主要自托管方案**：

1. **使用 Node.js 和 Express.js 服务静态文件** 8:  
   * **基本思路**: 在服务器上克隆您的 Digital Garden GitHub 仓库，安装依赖，执行构建命令生成静态文件（通常在 dist 目录），然后使用一个简单的 Express.js (或其他 Node.js HTTP 服务器) 应用来提供这些静态文件。  
   * **步骤概要** 8:  
     1. 在服务器上安装 Node.js 和 npm。  
     2. 克隆您的 Digital Garden 仓库。  
     3. 在仓库根目录运行 npm install 安装项目依赖。  
     4. 运行 npm run build 生成静态站点到 dist 目录。  
     5. 创建一个简单的 app.js 文件（或类似名称）来启动 Express 服务器，配置其从 dist 目录提供服务。  
        JavaScript  
        // 示例 app.js (简化版)  
        const express \= require('express');  
        const path \= require('path');  
        const app \= express();  
        const port \= 8080; // 或您希望的端口

        // 提供 dist 目录下的静态文件  
        app.use(express.static(path.join(\_\_dirname, 'dist')));

        // 处理所有其他路由，可以重定向到首页或 404 页面  
        app.get('\*', (req, res) \=\> {  
          res.sendFile(path.join(\_\_dirname, 'dist', 'index.html')); // 或 404.html  
        });

        app.listen(port, () \=\> {  
          console.log(\`Digital garden running on port ${port}\`);  
        });

     6. 运行 node app.js 启动服务。  
   * **生产环境考虑**:  
     * 使用进程管理器如 pm2 来确保 Node.js 应用在后台持续运行并在崩溃时自动重启 8。  
     * 使用反向代理（如 Nginx 或 Apache）来处理外部请求，将其转发到 Node.js 应用，并配置 HTTPS (SSL/TLS 证书，例如使用 Let's Encrypt) 8。  
     * **关键挑战**: 实现自动化。当您在 Obsidian 中发布笔记并推送到 GitHub 后，服务器需要自动拉取最新更改并重新构建。这通常需要配置 Git Hooks (如 post-receive hook) 或设置 CI/CD 流水线（如使用 Jenkins、GitLab CI 或自定义脚本结合 cron jobs）。  
2. 使用 Docker 进行容器化部署 8:  
   Docker 可以简化部署和环境管理。社区成员提供了一些 Dockerfile 示例：  
   * **仅构建和导出 (Dockerfile.export)** 8: 这个 Dockerfile 用于在容器内完成构建过程 (npm install 和 npm run build)，然后将生成的 dist 目录导出到宿主机。宿主机上的 Web 服务器（如 Nginx）再负责提供这些静态文件。这种方式适合已有反向代理和 Web 服务器的场景。  
     Dockerfile  
     \# Dockerfile.export 示例 \[8\]  
     FROM node:18 as base \# 使用合适的 Node 版本  
     WORKDIR /usr/src/app  
     COPY package\*.json./  
     RUN npm install  
     COPY..

     FROM base as builder  
     WORKDIR /usr/src/app  
     RUN npm run build

     FROM scratch AS export  
     COPY \--from=builder /usr/src/app/dist /

     构建命令示例: podman build \-f Dockerfile.export \--output dist. (或 docker build...)  
   * **完整的生产环境 Dockerfile (包含 Express 服务器)** 8: 这种 Dockerfile 不仅构建应用，还会将 Express 服务器（如上述 app.js）打包到镜像中，并运行它。  
     Dockerfile  
     \# 生产环境 Dockerfile 示例 \[8\]  
     \# Build stage  
     FROM node:18 as build  
     WORKDIR /usr/src/app  
     COPY package\*.json./  
     RUN npm install  
     COPY..  
     RUN npm run build

     \# Production stage  
     FROM node:18\-alpine \# 使用更小的基础镜像  
     WORKDIR /usr/src/app  
     ENV NODE\_ENV=production  
     COPY \--from=build /usr/src/app/dist./dist  
     COPY \--from=build /usr/src/app/app.js./app.js \# 假设 app.js 在构建阶段也复制了  
     COPY \--from=build /usr/src/app/package.json./package.json \# 仅复制生产依赖所需的  
     COPY \--from=build /usr/src/app/package-lock.json./package-lock.json  
     RUN npm install \--only=production \# 仅安装生产依赖  
     EXPOSE 8080  
     CMD \["node", "app.js"\]

     然后可以使用 Docker Compose 或 Kubernetes 等工具来管理容器。

自托管的权衡：  
自托管提供了无与伦比的控制力和灵活性，但也带来了显著的复杂性。用户需要负责服务器的配置、维护、安全更新、备份、域名解析、SSL 证书管理以及部署自动化流程的建立和维护。这对于技术能力较强、有特定需求（如数据隐私、深度集成其他服务）的用户来说是一个好选择，但对于普通用户而言，其维护成本可能较高。社区中分享的 Dockerfile 和 Express 设置方案 8 表明，通过社区协作，可以为这些高级场景提供可行的解决方案，体现了开源项目的适应性和活力。

### **4.5. 其他静态托管提供商：通用指南**

Obsidian Digital Garden 的核心是生成一个静态网站，这意味着它可以托管在任何支持静态文件服务的平台上 6。除了 Vercel、GitHub Pages 和 Netlify，还有许多其他选择，例如 Cloudflare Pages、AWS S3 \+ CloudFront、Google Firebase Hosting、Deno Deploy 等。

**通用部署步骤** 6：

1. **创建代码仓库**:  
   * 访问 Digital Garden 的官方模板仓库 (例如 https://github.com/oleeskild/digitalgarden)。  
   * 点击 "Use This Template"（使用此模板）按钮，然后选择 "Create a new repository"（创建新仓库），在您自己的 GitHub 账户下创建一个副本。  
2. **选择并注册托管服务**:  
   * 选择一个您偏好的静态站点托管提供商，并根据其指引创建一个账户。  
3. **连接仓库到托管服务**:  
   * 大多数静态托管服务都提供从 GitHub (或其他 Git 提供商) 直接导入和部署的功能。在您的托管服务提供商的控制面板中，连接您的 GitHub 账户，并选择您在第一步中创建的 Digital Garden 仓库。  
4. **配置构建设置**:  
   * 在托管服务的部署设置中，您通常需要指定以下构建参数 6。这些参数告诉平台如何构建您的站点：  
     **表4：静态主机关键构建设置**

| 设置 | 默认值/推荐值 | 目的 |
| :---- | :---- | :---- |
| **Install Command** | npm install | 安装项目运行和构建所需的依赖包 (定义在 package.json 中)。 |
| **Build Command** | npm run build | 执行实际的构建过程，将 Markdown 文件和模板转换为静态 HTML、CSS、JS 文件。 |
| **Output Directory** | dist | 构建完成后，包含最终静态站点文件的目录。托管平台将从此目录提供文件服务。 |
| **Root Directory** | ./ (或留空，表示仓库根目录) | 指定构建命令在哪个目录下执行。对于标准 Digital Garden 设置，通常是仓库根目录。 |

    \*注意：关于“Output Directory”，虽然 \[6\] 建议为 \`build\`，但项目实际的 \`npm run build\` 脚本（通常由 Eleventy 配置驱动）以及 Vercel、Netlify 和 GitHub Actions 的配置更常指向 \`dist\`。建议优先使用 \`dist\`，除非您的特定构建脚本有不同输出。\*

5. **部署**:  
   * 保存构建设置后，托管平台通常会自动从您的仓库拉取代码，执行安装和构建命令，然后将输出目录中的文件部署到其全球 CDN 网络。

这种基于标准构建命令（npm install, npm run build）和明确输出目录的构建流程，是 Digital Garden 项目具有良好平台无关性的基础。只要托管平台能够执行 Node.js 构建步骤并提供静态文件服务，理论上都可以用于托管您的数字花园，这极大地增强了项目的通用性和用户的选择自由度。

## **5\. 自定义与高级用法**

一旦您的数字花园成功部署并运行，您可能希望对其外观和功能进行个性化调整，以更好地反映您的风格和需求。Obsidian Digital Garden 提供了多种自定义途径。

### **5.1. 定制外观：主题与自定义样式 (custom-style.scss)**

Digital Garden 支持多种方式来调整站点的视觉呈现：

* **Obsidian 主题**: 插件允许您在发布的数字花园中应用您在 Obsidian 本地使用的部分主题样式 1。这有助于保持视觉上的一致性。具体支持程度可能因主题而异。  
* **样式设置**: 插件本身可能提供一些内置的样式调整选项，允许您修改颜色、字体等基本元素 1。  
* **custom-style.scss**: 这是进行深度样式定制的关键文件。项目模板中通常包含一个 src/styles/custom-style.scss (或类似路径) 文件。强烈建议您将所有自定义 CSS 规则添加到此文件中，而不是直接修改核心模板的 CSS 文件 1。  
  * **原因**: 当您未来更新 Digital Garden 的站点模板时（通过章节 3.3 中描述的 PR 流程），核心模板文件可能会被覆盖。如果您的自定义样式写在 custom-style.scss 中，它们将得到保留，从而避免了在每次模板更新后重新应用自定义样式的麻烦，也减少了与模板更新产生冲突的风险。这是一种确保自定义内容可维护性和升级安全性的重要实践。  
  * 您可以在 custom-style.scss 中使用标准的 SCSS 或 CSS 语法来覆盖默认样式、添加新样式，从而实现对数字花园外观的精细控制。

通过这种分层样式管理，Digital Garden 在提供开箱即用美观主题的同时，也为用户保留了通过 custom-style.scss 实现个性化和品牌化视觉效果的灵活性，并且兼顾了后续模板升级的便利性。

### **5.2. 扩展功能：利用支持的特性 (Dataview, 嵌入等)**

Obsidian Digital Garden 的强大之处不仅在于发布笔记，更在于它能将 Obsidian 中许多丰富的功能和内容类型带到在线环境中。充分利用这些特性，可以让您的数字花园更具动态性、信息量和吸引力。

回顾一下支持的关键特性 1：

* **Dataview 查询**: 可以在页面上动态展示基于特定条件的笔记列表或数据聚合，例如项目追踪、阅读清单、相关概念图等。  
* **嵌入内容**:  
  * **Excalidraw 绘图**: 直接嵌入您在 Obsidian 中创建的 Excalidraw 白板和示意图。  
  * **图片**: 支持多种图片格式的嵌入和展示。  
  * **笔记嵌入 (Transclusion)**: 将一篇笔记的内容完整地或部分地嵌入到另一篇笔记中，实现内容复用和模块化。  
* **交互式元素**:  
  * **本地关系图谱**: 为访客提供一个可视化的方式来探索笔记之间的连接。  
  * **文件树导航和全局搜索**: 帮助访客在您的知识库中自由穿梭和查找信息。  
* **富文本格式**:  
  * **Callouts/Admonitions**: 使用醒目的提示框来强调重要信息、警告或引言。  
  * **代码块**: 以清晰、高亮的方式展示代码片段。  
  * **MathJax**: 精确渲染复杂的数学公式。  
  * **Mermaid 和 PlantUML 图表**: 通过文本描述生成流程图、序列图、状态图等多种图表。

这些功能共同将数字花园从一个简单的文本发布平台，提升为一个能够承载丰富媒体和复杂信息结构的知识展示系统。它允许用户以更接近其在 Obsidian 中组织和消费信息的方式来呈现内容，保留了笔记的视觉丰富性和上下文关联性，从而为访客提供了更深入、更具吸引力的浏览体验。

### **5.3. 开发者选项：修改站点模板 (Eleventy, userSetup.js)**

对于具备 Web 开发技能的用户，Digital Garden 提供了更深层次的自定义能力，允许直接修改构成站点的模板代码。

* Eleventy 模板引擎:  
  Digital Garden 的站点生成是基于 Eleventy (11ty) 这个灵活的静态站点生成器 1。项目仓库的根目录中通常有一个 .eleventy.js 文件，这是 Eleventy 的主配置文件，定义了输入目录、输出目录、模板语言、过滤器、短代码等。熟悉 Eleventy 的开发者可以修改此文件来调整站点的构建逻辑。模板文件（通常使用 Nunjucks、Liquid 或 Markdown 格式，位于 src/site 或类似目录下）也可以被修改，以改变页面的 HTML 结构和布局。  
* src/helpers/userSetup.js:  
  为了在不直接修改核心模板文件（从而简化未来模板更新）的前提下进行自定义，项目提供了一个推荐的扩展点：src/helpers/userSetup.js 文件 1。开发者可以在这个文件中编写 JavaScript 代码，通过 Eleventy 提供的 API 来添加自定义的过滤器 (filters)、短代码 (shortcodes)、集合 (collections)、插件 (plugins) 或其他 Eleventy 配置。这些通过 userSetup.js 添加的自定义项会与主模板的配置合并，并且在模板更新时通常不会被覆盖，从而实现了更具弹性和可维护性的高级定制。  
* 本地开发环境:  
  为了方便开发者进行模板修改和调试，项目支持本地开发 1：  
  1. 克隆 (Clone) 您的 Digital Garden GitHub 仓库到本地计算机。  
  2. (可选，但推荐) 使用 Node 版本管理器 (如 nvm) 安装并切换到项目推荐的 Node.js 版本 (通常在 .nvmrc 文件中指定)。  
  3. 在仓库根目录运行 npm install 安装所有依赖。  
  4. 运行 npm run dev (或类似的开发脚本，定义在 package.json 中)。这通常会启动一个本地开发服务器，并监视文件更改，实现实时重新构建和浏览器自动刷新。  
  5. 项目模板中可能包含一个测试用的 Obsidian 笔记库 (例如 src/dg-testVault 1)，您可以将其作为 Obsidian 的一个 vault 打开，用于测试插件与本地开发服务器的交互。  
  6. 如果需要在本地开发时测试与 GitHub 的集成（例如，插件的发布功能），可以在项目根目录创建一个 .env 文件，并配置 GITHUB\_REPO, GITHUB\_TOKEN, GITHUB\_USERNAME 等环境变量 2。

通过 userSetup.js 这样的结构化扩展机制和完善的本地开发支持，Digital Garden 为有技术能力的 高级用户提供了深度定制其在线空间的途径，同时努力平衡了自定义的灵活性与未来升级的便捷性。

## **6\. 重要注意事项与最佳实践**

在使用 Obsidian Digital Garden 的过程中，遵循一些最佳实践并注意某些关键点，可以帮助您更顺畅地管理和维护您的在线知识库，避免常见问题。

### **6.1. 管理笔记间的链接与依赖关系**

数字花园的魅力在于笔记之间的互联互通，形成知识网络。然而，这也需要用户细心管理。

* **链接语法**: Digital Garden 支持标准的 Obsidian \[\[Wiki链接\]\] 语法来创建内部链接 1。  
* **发布被链接的笔记**: 最重要的一点是，**仅仅链接到一篇笔记并不会使其自动发布** 1。您必须为每一篇希望在数字花园中可见的笔记（无论是直接访问还是通过链接访问）在其 frontmatter 中添加 dg-publish: true。  
* **断开的链接**: 如果您发布了一篇笔记 A，其中包含指向笔记 B 的链接，但笔记 B 没有被标记为发布，那么在数字花园中点击这个链接将会导向一个提示“笔记不存在”的页面 1。  
* **实践建议**:  
  * 在发布一篇包含许多内部链接的笔记之前，仔细检查所有被链接的笔记是否也已标记为发布。  
  * 可以考虑使用 Obsidian 的 Dataview 插件或搜索功能，定期查找那些已发布但链接到未发布笔记的情况，以保持链接的完整性。

这种对发布状态的精细控制虽然赋予了用户极大的自主权，但也要求用户承担起维护内容连贯性的责任。一个链接完整、导航顺畅的数字花园能极大地提升访客的阅读体验。

### **6.2. Frontmatter 的精确性与常见陷阱**

Frontmatter 是控制笔记发布行为和元数据的核心，其语法的精确性至关重要。

* **基本语法**: 确保每一篇笔记的 frontmatter 都以三个短横线 (---) 开始，并以三个短横线 (---) 结束 1。  
* **避免复制粘贴错误**: 从网络或文档中复制 frontmatter 示例时，要特别注意是否意外引入了额外的字符，尤其是反引号 (\`\`\`) 1。Frontmatter 是 YAML 格式，对缩进和特殊字符敏感。  
* **属性名称和值**: 确保 dg-publish 和 dg-home 等属性名称拼写正确，其值 (通常是 true 或 false) 也准确无误。  
* **Obsidian 属性编辑器的使用**: 对于不熟悉手动编辑 YAML 的用户，Obsidian 1.4.x 及更高版本提供的“属性”编辑器 3 是一个更安全、更直观的选择，它可以帮助避免一些常见的语法错误。

虽然 frontmatter 作为一种将元数据与内容紧密结合的方式非常优雅，但其纯文本的特性使其容易受到微小语法错误的影响。这些错误可能导致笔记无法正确发布、元数据解析失败，甚至构建过程出错。因此，在编辑 frontmatter 时保持细心和准确是必要的。未来，插件或许可以考虑在 Obsidian 内部增加对 Digital Garden 特定 frontmatter 属性的校验功能，以进一步帮助用户避免此类问题。

### **6.3. 理解特定平台的局限性**

您选择的托管平台可能会带来一些特定的限制或需要注意的事项。

* **GitHub Pages 的仓库命名**: 如前所述，使用 GitHub Pages 时，将仓库命名为 \<username\>.github.io 是确保资源正确加载的最可靠方法 5。其他命名方式可能需要复杂的变通配置，且效果不一定理想。  
* **自托管的自动更新**: 如果选择自托管，您需要自行实现当笔记在 Obsidian 中发布（即推送到 GitHub 仓库）后，服务器能够自动拉取最新更改并重新构建站点的机制 8。这通常比使用 Vercel 或 Netlify 等平台的自动化部署流程要复杂。  
* **构建时间和资源限制**: 免费托管平台通常对每月构建时间、带宽、存储空间等有一定限制 (例如，Netlify 曾有每月 300 构建分钟的免费额度 11)。对于非常大的数字花园或更新极其频繁的情况，可能需要关注这些限制。  
* **功能差异**: 不同平台对自定义域名、SSL 证书、重定向规则、边缘函数等的支持程度和配置方式可能不同。

在选择部署平台之前，了解其特性和潜在局限性，有助于您做出更符合长远需求的决策，并为可能遇到的问题做好准备。

## **7\. 结论：培育您的数字空间**

Obsidian Digital Garden 项目为知识工作者和学习者提供了一个独特的机会，将他们精心构建的 Obsidian 笔记库转化为一个生动、个性化且可公开分享的在线空间。它不仅仅是一个笔记发布工具，更是一种促进思考、连接想法并与世界分享见解的媒介。

### **7.1. Obsidian Digital Garden 的价值回顾**

该项目的核心价值在于其赋予用户的**控制权、灵活性和可访问性**：

* **所有权与个性化**: 用户对其数字花园拥有完全的控制权，可以根据自己的喜好定制外观、结构和内容呈现方式，真正打造一个属于自己的在线知识品牌 1。  
* **与 Obsidian 无缝集成**: 通过深度支持 Obsidian 的核心功能（如链接、标签、Dataview、嵌入等）和流行插件（如 Excalidraw），确保了从本地笔记到在线内容的高度保真转换，保留了知识的丰富上下文 1。  
* **免费和开源**: 项目本身开源，并推荐使用免费的托管方案（如 Vercel、GitHub Pages），极大地降低了个人建立和维护在线知识库的经济门槛 1。  
* **促进知识连接与发现**: “数字花园”的概念鼓励非线性的、网络化的知识组织，通过链接和反向链接，帮助用户和访客发现思想之间的深层联系。  
* **迭代与演进**: 支持增量发布和模板更新机制，鼓励用户持续培育和发展其数字花园，使其成为一个不断成长的知识体系 1。

### **7.2. 进一步探索的指引**

要更深入地了解和使用 Obsidian Digital Garden，以下资源将非常有帮助：

* **官方文档**: 项目的官方文档网站 (例如 dg-docs.ole.dev 3) 是获取最新信息、详细指南和故障排除技巧的首选之地。  
* **GitHub 仓库与讨论区**:  
  * 插件仓库 (https://github.com/oleeskild/Obsidian-Digital-Garden): 可以在此提交问题 (Issues)、查看源代码、了解最新开发动态。  
  * 模板仓库 (https://github.com/oleeskild/digitalgarden): 站点模板的源代码所在地。  
  * GitHub Discussions 12: 这是一个活跃的社区论坛，用户可以在这里提问、分享经验、展示自己的数字花园、讨论新功能想法，并从其他用户和开发者那里获得帮助 5。许多高级用法和针对特定问题的解决方案（如自托管方案、特定平台部署技巧）都可以在讨论区中找到。

积极的社区支持和不断完善的文档是开源项目成功的关键因素。Obsidian Digital Garden 拥有这两方面的宝贵资产，为用户提供了一个持续学习和成长的良好生态系统。通过探索这些资源，您可以不断提升自己构建和维护数字花园的能力，使其真正成为您知识旅程中的一个璀璨亮点。

#### **引用的著作**

1. oleeskild/obsidian-digital-garden \- GitHub, 访问时间为 五月 29, 2025， [https://github.com/oleeskild/Obsidian-Digital-Garden](https://github.com/oleeskild/Obsidian-Digital-Garden)  
2. oleeskild/obsidian-digital-garden \- GitHub, 访问时间为 五月 29, 2025， [https://github.com/oleeskild/obsidian-digital-garden](https://github.com/oleeskild/obsidian-digital-garden)  
3. 01 Getting started \- Obsidian Digital Garden, 访问时间为 五月 29, 2025， [https://dg-docs.ole.dev/getting-started/01-getting-started/](https://dg-docs.ole.dev/getting-started/01-getting-started/)  
4. Best Plugins for Publishing Your Obsidian Notes Online, 访问时间为 五月 29, 2025， [https://www.obsidianstats.com/posts/2025-04-16-publish-plugins](https://www.obsidianstats.com/posts/2025-04-16-publish-plugins)  
5. How to deploy to GitHub Pages · oleeskild obsidian-digital-garden ..., 访问时间为 五月 29, 2025， [https://github.com/oleeskild/obsidian-digital-garden/discussions/389](https://github.com/oleeskild/obsidian-digital-garden/discussions/389)  
6. Hosting alternatives \- Obsidian Digital Garden, 访问时间为 五月 29, 2025， [https://dg-docs.ole.dev/advanced/hosting-alternatives/](https://dg-docs.ole.dev/advanced/hosting-alternatives/)  
7. oleeskild/digitalgarden \- GitHub, 访问时间为 五月 29, 2025， [https://github.com/oleeskild/digitalgarden](https://github.com/oleeskild/digitalgarden)  
8. Local deployment · oleeskild obsidian-digital-garden · Discussion ..., 访问时间为 五月 29, 2025， [https://github.com/oleeskild/obsidian-digital-garden/discussions/160](https://github.com/oleeskild/obsidian-digital-garden/discussions/160)  
9. Deploy an Eleventy site to Netlify \- 11ty Recipes, 访问时间为 五月 29, 2025， [https://11ty.recipes/recipes/deploy-an-eleventy-site-to-netlify/](https://11ty.recipes/recipes/deploy-an-eleventy-site-to-netlify/)  
10. Eleventy on Netlify, 访问时间为 五月 29, 2025， [https://docs.netlify.com/frameworks/eleventy/](https://docs.netlify.com/frameworks/eleventy/)  
11. Open-source / free resources on self-hosting markdown / Obsidian vaults \*dynamically\*? : r/DigitalGardens \- Reddit, 访问时间为 五月 29, 2025， [https://www.reddit.com/r/DigitalGardens/comments/1jni0gh/opensource\_free\_resources\_on\_selfhosting\_markdown/](https://www.reddit.com/r/DigitalGardens/comments/1jni0gh/opensource_free_resources_on_selfhosting_markdown/)  
12. oleeskild obsidian-digital-garden · Discussions \- GitHub, 访问时间为 五月 29, 2025， [https://github.com/oleeskild/obsidian-digital-garden/discussions](https://github.com/oleeskild/obsidian-digital-garden/discussions)