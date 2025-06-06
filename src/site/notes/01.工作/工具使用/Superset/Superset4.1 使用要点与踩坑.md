---
{"dg-publish":true,"permalink":"/01.工作/工具使用/Superset/Superset4.1 使用要点与踩坑/","title":"Superset4.1 使用要点与踩坑"}
---


## 1.数据集

#####  数据集命名

Superset4.1<u>不支持中文命名的数据集</u>，一旦数据集命名为中文，就再也打开不开，也无法编辑和管理了，只能删除。
如果数据集名称包含英文大写，也有可能会有保存不了的问题。
但是可以在数据集的设置中，描述栏编写这个数据集的用途，这个地方可以用中文

#####  数据集保存

在1.5版本superset中，无论任何格式的SQL只要能查出数据，均可保存为数据集
在4.1版本中，需要先将数据集进行格式化处理，再保存为数据集，否则会出现报错

操作步骤：
第一步，执行查询
![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250514131849437.png?cd-oss-obs)

第二步，FormatSQL
![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250514131934290.png?cd-oss-obs)

第三步，保存数据集
![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250514132007136.png?cd-oss-obs)


## 2.图表 - 时间序列功能简述


Apache Superset 4.1 把“时间序列”做成了一个完整的分析链条：在可视化层面新增 **Big Number with Time Period Comparison** 与 **Table with Time Comparison** 两个新图表；在查询层面补足“当前周/月/年”快捷时间过滤器和 `{{ get_time_filter() }}` Jinja 宏；在体验层面还修复了 Time Comparison 查询的若干 bug，并允许为 Dashboards 配置自定义刷新频率。([Preset][1], [Fossies][2], [Fossies][3])
下面通过一个“最近 30 天销售额 VS 去年同期”的完整示例，把 4.1 里的时间序列能力串起来演示。

---

#### 常见时间序列图表及其定位

| 图表                                         | 典型用途       | 4.1 补强点                                  |
| ------------------------------------------ | ---------- | ---------------------------------------- |
| **Time-series Line / Area / Bar**          | 通用趋势、分组对比  | 支持“当前”日期快捷过滤；Time Comparison 修复          |
| **Big Number with Time Period Comparison** | KPI + 同/环比 | 新增图表（需打开试验性插件）([Preset][1], [GitHub][4]) |
| **Table with Time Comparison**             | 明细表 + 对比列  | 新增图表（同上）([Fossies][2], [GitHub][4])      |
| **Mixed Time-series**                      | 多度量 / 双轴   | 延续 4.0 版能力                               |

Superset 还保留了 Horizon、Calendar Heatmap 等高级时序可视化，全部列在官方文档中([Preset][5])。

---

#### 示例：对比最近 30 天与去年同期的销售额

> **数据假设**：表 `ecommerce_sales`，字段
> `order_date TIMESTAMP`、`revenue DECIMAL`。

##### 1 准备数据集

1. 在 **Data → Datasets** 选择或创建 `ecommerce_sales`。
2. 确认 `order_date` 列被标记为 *temporal* 类型；只有这样它才能出现在 *Time column* 下拉框里([Preset][5])。

---

##### 2 绘制 Time-series Line Chart（去年同期对比）

1. **Charts → + Create Chart**，选数据集 → 选 *Time-series Line Chart*。
2. **Time** 面板

   * Time range：*Last 30 days*
   * Time grain：*day*
3. **Query** 面板

   * Metrics： `SUM(revenue)`
   * **Time Comparison**：`1 year ago` → Superset 会生成一条虚线表示去年同期([Preset][5])。
4. **Advanced Analytics**（可选）

   * Rolling window：7 → 平滑短期波动，做 7 日移动平均([Preset][5])。
5. 点击 **Run** → **Save**，即可在仪表盘里看到两条时间序列。

---

##### 3 绘制 Big Number with Time Period Comparison

> 该图表在 4.1 处于试验阶段，先在 `superset_config.py` 打开
>
> ```python
> FEATURE_FLAGS = {"CHART_PLUGINS_EXPERIMENTAL": True}
> ```
>
> 也可用环境变量 `SUPERSET_FEATURE_CHART_PLUGINS_EXPERIMENTAL=True`([GitHub][4])

1. 新建图表 → 选 *Big Number with Time Period Comparison*。
2. Settings

   * Metric：`SUM(revenue)`
   * Time range：*Last 30 days*
   * **Comparison period**：*Previous period*（同上一段 30 天）。
3. 运行后，卡片会显示：

   * 主指标（最近 30 天销售总额）；
   * 对比值（前 30 天）；
   * 绝对增减 & 百分比增减([Preset][1], [Preset 文档][6])。

> 想看“去年同期”就把 Comparison period 改成 *1 year ago*。

---

##### 4 使用 Table with Time Comparison

1. 新建图表 → 选 *Table with Time Comparison*。
2. Columns 里放 `order_date`（按日粒度）和 `SUM(revenue)`。
3. Comparison period 同样选 *1 year ago*。
4. 运行后，表格会自动添加三列：对比值、差值、百分比差值([Fossies][2])。

---

##### 5 善用时间过滤与 Jinja 宏

* “当前周/月/年”快捷项可一键查看滚动窗口数据([Preset][1])。
* 对复杂 SQL，可在查询里写 `WHERE {{ get_time_filter('order_date') }}`，让 Dashboard 的时间筛选自动注入([Preset][1])。

---

#### 常见问题与技巧

| 场景      | 解决方案                                                                           |
| ------- | ------------------------------------------------------------------------------ |
| 比较列不显示  | 确认 **CHART\_PLUGINS\_EXPERIMENTAL** 已开启，并在 *Query → Time Comparison* 选中周期。     |
| 数据点太多   | 调低 *Time grain*（如 day → week）或启用 7/30 日 rolling 平滑。                            |
| 多系列颜色混乱 | 在 *Customize → Color Scheme* 里选择调色板，或给关键系列固定颜色。                                |
| 需要置信区间  | 在 Line Chart 中准备 `metric__yhat_lower/upper` 列，Superset 会自动画出带状区间([GitHub][7])。 |

---

#### 小结

Superset 4.1 的“时间序列”不仅新增了 **Big Number** 与 **Table** 两款对比型图表，还把时间比较、快捷时间过滤、Jinja 宏等底层能力补齐；配合现有的 Line/Area/Bar 图与高级分析，可覆盖从 KPI 卡片到多维趋势、环比同比、滚动平均乃至置信区间的整套需求。掌握上述步骤，就能在几分钟内搭建出专业的时序分析仪表盘。

[1]: https://preset.io/blog/apache-superset-4-1-release-notes/ "Apache Superset 4.1 Release Notes | Preset"
[2]: https://fossies.org/linux/apache-superset/RELEASING/release-notes-4-1/README.md "Superset: RELEASING/release-notes-4-1/README.md | Fossies"
[3]: https://fossies.org/linux/apache-superset/CHANGELOG/4.1.0.md "Superset: CHANGELOG/4.1.0.md | Fossies"
[4]: https://github.com/apache/superset/discussions/31426 "Big Number with Time Period Comparison Chart · apache superset · Discussion #31426 · GitHub"
[5]: https://preset.io/blog/2020-06-26-timeseries-chart/ "How to Use a Time Series Chart - Getting Started | Preset"
[6]: https://docs.preset.io/docs/big-number-chart "Big Number Chart in Preset"
[7]: https://github.com/apache/superset/discussions/19145 "Add confidence interval capability to time series line charts · apache superset · Discussion #19145 · GitHub"



### 3.图表 - 时间序列配置使用说明

![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250514132841407.png?cd-oss-obs)


下面这几个输入框分别控制什么、应该怎么填，取决于**你打算在这列里展示「流水」的哪种对比方式**。先把含义快速说清楚，再给两个常见场景的“可直接照抄”示例。

| 控件                            | 作用                                                                                                                                                                                                    | 常见填法                                                              |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **类型（上面的下拉）**                 | 选 “时间比较”（Time comparison）后，Superset 才会给这列做对比运算。                                                                                                                                                       | 请选择 **时间比较**                                                      |
| **Time lag**                  | 要“向前/向后”偏移多少个 *Time grain*（时间粒度）再做对比。值是整数：<br>  • 1 = 上一粒度<br>  • 7 = 前七天（当粒度=day）<br>  • 12 = 去年同月（当粒度=month）<br>如果你已经在 *Time Comparison* 里写了 “1 year ago”“previous period”等 **查询级别** 的时间位移，这里就保持 0。 | 0 或 1 / 7 / 12 / 365 等                                            |
| **类型（下方下拉，Calculation type）** | 选择要显示的计算结果：<br>  • **Actual values** (也叫 Value) → 去年/上期的原值<br>  • **Difference** → 绝对差值 = 当前−对比期<br>  • **Percentage change** → 百分比差值 = (当前−对比期)/对比期                                                  | Difference 或 Percentage change                                    |
| **Color bounds**              | 设置正负阈值，让差值颜色渐变。为空则不做颜色映射。                                                                                                                                                                             | 例：-0.2 和 0.2                                                      |
| **数字格式化**                     | 自定义数值格式。常用：<br>  • `,.0f` 千位分隔整数<br>  • `,.1%` 百分比保留 1 位小数                                                                                                                                            | 根据上面类型选：<br>  Difference → `,.0f`<br>  Percentage change → `,.1%` |

> Superset 4.1 的 Table with Time Comparison 正是依赖这一套配置来同时给出“当前值 / 对比值 / Δ / %”四列的。([Preset][1])

---

##### 场景 1：最近 30 天流水 vs **上一段 30 天**（环比 % 变化）

1. **Data → Time range** 选 *Last 30 days*
2. **Query → Time Comparison** 下拉里选 *previous period*
3. 进入“流水”列的 **Column Configuration**：

   * 类型（上面）：时间比较
   * **Time lag**：`0` （因为查询层面已经指定“上一期”）
   * 类型（下面）：`Percentage change`
   * 数字格式化：`,.1%`
   * 如需配色，Color bounds 可填 -0.2 到 0.2

效果：表格会出现四列——`流水`（当前值）、`流水_previous`（上一段值）、`Δ`、`%`，最后一列就是环比百分比。计算逻辑来自 Superset 的“Percentage Change”算法。([Preset 文档][2])

---

##### 场景 2：每日流水 vs **前一日**（绝对差值）

1. **Time grain** 设为 `day`，**Time range** 选你关心的日期段。
2. *Query → Time Comparison* **不填**（留空）。
3. 在“流水”列配置里：

   * 类型（上面）：时间比较
   * **Time lag**：`1`（往前 1 天）
   * 类型（下面）：`Difference`
   * 数字格式化：`,.0f`

当粒度是天，Time lag = 1 就是“昨天”。差值列能直观反映今日流水比昨天多/少多少。

---

##### 常见踩坑 & 提示

| 症状                 | 排查要点                                                                                          |
| ------------------ | --------------------------------------------------------------------------------------------- |
| Δ 和 % 都是 0         | 对比期没有数据；或 Time range 没有覆盖到位；或 Time lag / Time Comparison 写错导致实际比较的是同一行                        |
| 列没出来               | 确认 **类型** 已改成“时间比较”，否则 Superset 只展示原始数字                                                       |
| 百分比显示成 0.25 而非 25% | 数字格式化没填 `,.1%`（或者选择了 Difference）                                                              |
| 想对比去年同月            | Time grain = month，Time lag = 12；或在 Query → Time Comparison 里直接写 “1 year ago”，然后 Time lag = 0 |

用好这几个字段，你就能把 **Table with Time Comparison** 或 **Big Number with Time Period Comparison** 这些 4.1 新增图表的对比能力发挥到极致。

[1]: https://preset.io/blog/apache-superset-4-1-release-notes/ "Apache Superset 4.1 Release Notes | Preset"
[2]: https://docs.preset.io/docs/time-comparison "Time Comparison Advanced Feature in Preset"







![image.png](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250514132956945.png?cd-oss-obs)

**「周期平均值 (Period average)」是什么？**
在 *Table with Time Comparison* / *Time-series Table* 里，把某一列的 **类型** 设成 “周期平均值” 后，Superset 会在\*\*后端（Pandas Post-processing）\*\*中为你做一次 **滚动平均（rolling mean）**：

> 以当前行为结束点，向前拿 *N* 个时间粒度（Periods）里的度量值，求平均并作为这一行的显示结果。
> 这样可以把日度、周度等高波动的序列快速平滑成 7 日均线、30 日均线、12 月均线等。([腾讯云][1])

---

#### 操作面板每个字段的含义

| 控件               | 作用                                                                                                                                                      | 典型填法                |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| **类型**           | 选 “周期平均值” 后才会出现下面两个输入框 *Periods* / *Min periods*                                                                                                        | —                   |
| **Periods**      | **窗口长度**：滚动平均要回看多少个时间粒度<br>• `7` = 7 天（当 Time grain=day）<br>• `12` = 12 月（当 Time grain=month）<br>必须是正整数，否则报 “Periods must be a whole number”([邮件归档][2]) | 7 / 30 / 12 …       |
| **Min periods**  | **最小可用期数**：窗口里至少要有多少个点才显示值。<br>如果也填 `7`，就能把前 6 天的“预热期”隐藏掉，避免开头那段逐渐爬升的假象。                                                                                | 通常和 *Periods* 写同一个数 |
| **Time lag**     | （可选）窗口整体再向前/向后偏移多少个粒度。<br>• `0` = 以当前行结尾<br>• `1` = 只看当前行之前的完整 N 期平均（排除当日）                                                                              | 0 或 1               |
| **Color bounds** | 给滚动平均做区间着色；留空表示不配色                                                                                                                                      | 例：0～500             |
| **数字格式化**        | d3 格式串。均线通常保留 1–2 位小数或用千分位：<br>`,.1f` / `,.2f`                                                                                                          | 根据需求                |

> ⚠️ 在选择 “周期平均值” 后，只有 *Periods* 填了合法数字、并且整体查询结果 ≥ Periods 行，Superset 才会把这个列渲染出来。

---

#### 两个“照抄即可”的示例

##### 1️⃣ 显示**7 日滚动均线**（含当天）

| 位置                | 设置             |
| ----------------- | -------------- |
| **Time grain**    | `day`          |
| **Time range**    | `Last 60 days` |
| **列类型**           | 周期平均值          |
| **Periods**       | `7`            |
| **Min periods**   | `7`            |
| **Time lag**      | `0`            |
| **Number format** | `,.0f`         |

> 表格会在度量列右侧生成一列 “xxxx\_rolling\_avg\_7d”，其数值等于当天及往前 6 天的平均。

---

##### 2️⃣ 显示**月度 3 期均线**（排除当月，观察落后 1 期）

| 位置                | 设置               |
| ----------------- | ---------------- |
| **Time grain**    | `month`          |
| **Time range**    | `Last 24 months` |
| **Periods**       | `3`              |
| **Min periods**   | `3`              |
| **Time lag**      | `1`              |
| **Number format** | `,.1f`           |

> 结果列是「上月 + 再往前两个月」的 3 个月平均，用来对比当月实际值时就没有“把当月自己也算进去”的偏差。

---

#### 常见问题 & 调优

| 现象            | 诊断 & 解决                                                                            |
| ------------- | ---------------------------------------------------------------------------------- |
| 列不显示 / 全是 NaN | *Periods* 填了 0 或非整数；或 Time range 行数 < *Periods*；或某维度在窗口内全 NULL。                    |
| 前几行斜着往上爬      | 典型“预热期”——把 **Min periods** 填成和 *Periods* 相同即可隐藏。                                   |
| 想让均线和原值都出现    | 在 **Time series columns** 里加两行：一行选 *Actual Value*，一行选 *Period average*，都指向同一个度量就行。 |
| 表太大跑不动        | 均线是在 Superset 后端滚动计算的，对超大结果集开销较高。可先在 **Query → Row limit** 控制行数，或把 Time grain 调粗。  |

---

#### 一句话总结

> **周期平均值 = 滚动均线。** 选好窗口长度 (*Periods*)、最小期数 (*Min periods*)，再决定是否排除当前行 (*Time lag*)，就能把原始指标平滑成日均 / 周均 / 月均，用于趋势洞察或 KPI 对比，无需在 SQL 里手动写窗口函数。

[1]: https://cloud.tencent.com/developer/article/1876864 "（二）Superset 1.3图表篇——Time-series Table-腾讯云开发者社区-腾讯云"
[2]: https://www.mail-archive.com/commits%40superset.incubator.apache.org/msg01950.html?utm_source=chatgpt.com "[incubator-superset] branch master updated: Fix bug: some word not ..."



#### sparkline又是什么意思，如何使用呢

##### 1. 什么是 **Sparkline** ?

> **Sparkline = 迷你趋势线**
> 它是一条只有几十个像素高的小折线/小柱状，被直接渲染在表格单元格里，用来“一眼”呈现该行指标在一段时间内的走势，而不用再切换到单独的大图。
> 在 Superset 4.x 里，Sparkline 只能出现在 **Time-series Table** / **Table with Time Comparison** 这两种表格型图表的列上。

常见用途 ✅

| 业务场景           | 解读示例                           |
| -------------- | ------------------------------ |
| 每个主播近 30 天收入趋势 | 一行一个主播，右侧 Sparkline 高低起伏显示收入波动 |
| 每个渠道每日 DAU 走势  | 行头是渠道名，Sparkline 一眼看出哪条增长、哪条下滑 |
| KPI 看板中的“体温计”列 | 把绝对值隐藏，只用线条长短高低提示趋势            |

---

##### 2. 如何配置 Sparkline（5 步走）

> **前提**：你已经选好 **Time-series Table**（或 *Table with Time Comparison*）并让查询至少返回【时间列 + 指标列】。

| 步骤                            | 操作                                                                                                                      | 关键点                              |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
| **① 设时间范围 & 粒度**              | *Time* 面板 → Time range: *Last 30 days*（举例）<br>Time grain: *day*                                                         | Sparkline 的 X 轴就是这里确定的 30 个“时间桶” |
| **② 选分组字段**                   | *Query* 面板 → Group by 里放 “guild\_name” 或任何维度                                                                            | 每个维度值会占表格一行                      |
| **③ 添加第二列指标**                 | 在 *Metrics* → *Time series columns* 把同一指标 **再拖一次**，让表格里出现两个同名度量                                                         | 第一个保留数值，第二个用于画线                  |
| **④ 打开 Column Configuration** | 对第二个度量点击 ✏️                                                                                                             |                                  |
| **⑤ 调整三项设置**                  | - **类型(Type)** → `Sparkline`<br>- **Periods** → *留空*（= 用查询返回的所有点）或填 `7` 取最近 7 天<br>- **Number format** → `,.0f`（或不显示数值） | 这时表格预览就会把该列渲染为细小折线 / 小柱          |

> **保存** 并 **Run**，Dashboard 中就能看到每行右侧跟着一条“小心电图”式的趋势线。

---

##### 3. 进阶可调选项

| 配置项                                | 作用                   | 建议值                       |
| ---------------------------------- | -------------------- | ------------------------- |
| **Sparkline type**<br>(Line / Bar) | 折线或柱状                | 折线更直观，柱状适合离散数据            |
| **Rolling window**                 | 对 Sparkline 数据再做滚动平均 | 日数据常填 `7` 把高频噪声平滑         |
| **Width / Height**                 | 单元格中线条的宽高像素          | 默认即可；表格太窄时可减小             |
| **Color bounds**                   | 给 Sparkline 线填充渐变色   | 业务常留空；要强调高低可填 0, 500 这类阈值 |
| **Show tooltip**                   | 悬停显示具体值              | 默认开启即可                    |
|                                    |                      |                           |

*不同 Superset 版本/主题，选项名字可能略有差异，但都在「Column Configuration → Sparkline」块里。*

---

##### 4. 使用小贴士 & 常见问题

| 问题 / 目标              | 解决方案                                                                                                                                                     |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **只想看最后 7 天走势**      | 在 Column Configuration 里把 **Periods** 填 `7`                                                                                                              |
| **表格卡顿**（行数 × 时间点太多） | - Row limit 控制行，或把 Time grain 调粗（day→week）                                                                                                               |
| **想同时显示数值+线**        | *Column A* 保留数值，*Column A (copy)* 设 Sparkline                                                                                                            |
| **Sparkline 颜色太浅**   | 在 Dashboard -> Color scheme 选择深色调，或在列配置里改线/柱颜色                                                                                                           |
| **要做同比/环比+趋势线**      | 用 *Table with Time Comparison*：<br>1️⃣ Metrics 列 ×2 (原值 + Sparkline)<br>2️⃣ Query → Time comparison 写 `1 year ago`<br>3️⃣ Sparkline 那列 Time lag 设 `0` 即可 |

---

##### 5. 一句话总结

> **Sparkline = 把时间序列迷你化放进表格单元格**。
> 在 Time-series Table 中复制出一列指标 → Column Configuration 里把 **类型**选为 *Sparkline*，再按需设 Periods / 颜色 / 滚动窗口，就能让每行维度带着自己的“小趋势”，让你的 Superset 4.1 仪表盘既节省空间又信息丰富。



### Time lag 在 Superset 里的 3 种典型“设法”


#### Time lag 在 Superset 里的 3 种典型“设法”

| 场景                                                                                             | **在哪儿设置**                                                                                  | 可以填什么                              | 常见用途                                        |
| ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ---------------------------------- | ------------------------------------------- |
| **① 列级 Time lag**<br>(Table with Time Comparison / Time-series Table → *Column Configuration*) | 对应度量那一行的 **Time lag** 输入框                                                                  | 纯整数 ≥ 0<br>0 = 本期<br>1 = 上一粒度<br>… | 给单个度量做 *n* 期对比<br>（昨天、上周、去年同月…）             |
| **② 查询级 Time Comparison**<br>(Charts → *Query* 面板 → **Time Comparison**)                       | 自然语言时间偏移串：<br> `1 day ago` `4 weeks ago`<br> `previous period`<br> `2 years ago` …         | 一次对整张图/表加 1\~10 条对比线或对比列           | KPI 卡片/折线趋势一次看多条“对齐”序列([docs.preset.io][1]) |
| **③ SQL / Jinja 级位移**<br>(自写 SQL、Jinja 宏)                                                      | `WHERE {{ get_time_filter('ts') }}`<br>`SELECT date_trunc('day', ts) - INTERVAL '7 day'` … | 高级定制：错位 JOIN、同环比+滑窗                | 复杂报表或需要多列不同位移时                              |

---

##### 1️⃣ 列级 **Time lag** ——“向前 *n* 格”

> *所在位置：Table with Time Comparison → 度量列 → Column Configuration。*

* **数值 = 回看几个 *Time grain***

  * `Time grain = day` → **1** = 昨天，**7** = 上周同日
  * `Time grain = month` → **12** = 去年同月
  * `Time grain = quarter` → **4** = 去年同季
* **0 表示** “和本期对比”——通常与 **Query→Time Comparison** 合用，先在查询层做 1 year ago，然后列里 Time lag 设 0，仅用来挑选“绝对差值 / 百分比差值”等计算类型。
* **不可写负数**（想看未来请到查询层用 `1 day later` 这类语法）。

> **示例：**
>
> * 「日粒度，想看日环比差值」→ Time lag = **1**，Calculation type 选 *Difference*
> * 「月粒度，想看去年同月同比%」→ Time lag = **12**，Calculation type 选 *Percentage change*，Number format `,.1%`

---

##### 2️⃣ 查询级 **Time Comparison / Time Shift** ——“一次性多条对比”

*在所有时间序列图表的 **Query** 面板都能看到。*

* 直接写偏移串（不区分大小写）：
  `1 week ago` / `4 weeks ago` / `1 year ago` / `previous period` …
* Superset 会帮你生成多条序列或多列（Actual / Δ / %）。
* 你仍可在列级 **Time lag=0** 来决定显示哪种计算列（差值、比例等）。

📌 **注意**：Time Comparison 需要一个“封闭的时间范围”，否则 Superset 会报错 ❝An enclosed time range must be specified❞。([docs.preset.io][1])

---

##### 3️⃣ SQL / Jinja 级位移 ——“我全都要”

当一个报表里既要 **日环比**、又要 **周环比**，或者要把「去年同月 + 上一期 + 滚动均线」一次塞进同一张表时，仅靠 UI 输入框会很局促，可以：

```sql
SELECT
  date,
  revenue,
  LAG(revenue, 1)  OVER (ORDER BY date)          AS rev_d1,
  LAG(revenue, 7)  OVER (ORDER BY date)          AS rev_d7,
  LAG(revenue, 30) OVER (ORDER BY date)          AS rev_d30
FROM sales
WHERE {{ get_time_filter('date') }}
```

然后在 **Dataset → Calculated columns** 把 `revenue - rev_d1` / `(revenue - rev_d365)/NULLIF(rev_d365,0)` 再包装成度量即可。

---

#### 快速对照：**用哪个 Time lag？**

| 需求            | 建议做法                                                      |
| ------------- | --------------------------------------------------------- |
| 单列对比、窗口短      | **列级 Time lag**（最直观，少写一次查询）                               |
| 同一图/表一次看多条对比线 | **查询级 Time Comparison**，写多条 `x weeks ago`；列级 Time lag 设 0 |
| 多种错位混杂、逻辑复杂   | 直接 SQL 窗口函数或 Jinja 宏，搞定后作为普通度量使用                          |

---

#### 常见疑问

| 问题                                | 解释                                                                    |
| --------------------------------- | --------------------------------------------------------------------- |
| **可以写负数吗？**                       | 列级 Time lag 目前只接受 ≥ 0；要看未来，改用 Query→Time Comparison 写 `1 week later`。 |
| **列级和查询级冲突怎么办？**                  | 二者会“叠加”。通常 **二选一**：<br>• 需要多对比→用查询级；<br>• 只看环比/同比→列级 + Time lag =N。   |
| **Time grain 改了要同步改 Time lag 吗？** | 是的。粒度从 day→week 后原来 `7` 就不再代表一周，而是 7 周。                               |

---

#### 一句话总结

> **Time lag** 就是“向前错位 *n* 个时间粒度”。
>
> * *列级* Time lag：给单列做环比/同比。
> * *查询级* Time Comparison：一次拉多条对比线/列。
> * 高级组合：SQL 窗口函数或 Jinja。
>   把这三招灵活套用，你的 Superset 4.1 时间对比分析就能随心所欲。

[1]: https://docs.preset.io/docs/time-comparison "Time Comparison Advanced Feature in Preset"



## 3.过滤器

并不是 “没有过滤器”——**4.1 把旧的 Filter Box／Filter Set 全部移除了，但保留并强化了「原生过滤器（Native Filters）」体系**。换句话说：过滤能力还在，只是入口和交互方式变了。下面把核心变化和实际用法快速说明一下。

---

#### 1 为什么你会感觉“过滤器不见了”？

| 4.0 之前                     | 4.0 及以后                                           |
| -------------------------- | ------------------------------------------------- |
| **Filter Box** 以图表形式插在仪表盘里 | 被彻底删除，代码也移除；旧仪表盘会在升级脚本里自动迁移到原生过滤器面板 ([Preset][1]) |
| **Filter Set**（侧边多个预设）     | 同样删除，不再维护 ([Preset][1])                           |
| 原生过滤器（Native Filters）      | 继续存在，并成为**唯一推荐方式**                                |

---

#### 2 现在该怎么“加过滤器”？

1. **打开仪表盘 → “编辑”**
2. 右上角切换到 **Filters** 标签页
3. 点击 **＋ Add filter**，按向导选：

   * **数据集**（Dataset）
   * **列**（Column）
   * 过滤类型（下拉、多选、时间范围等）
4. （可选）在 **Scope** 里勾选哪些图表要受此过滤器影响
5. **Save** 并退出编辑，侧边就会出现一个可折叠的过滤器面板

这就是新版的“过滤栏”体验，Preset 官方把它叫 **Dashboard Native Filters** ([Restack][2])。

---

#### 3 特殊场景提示

| 需求                     | 做法                                                                            |
| ---------------------- | ----------------------------------------------------------------------------- |
| **把旧 Filter Box 自动迁移** | 升级 3.x→4.x 时运行脚本：`superset native-filters upgrade`；或者手动执行 UI 提示 ([Preset][3]) |
| **跨仪表盘分享过滤状态**         | 复制浏览器地址；URL 里会带 `native_filters=` 参数，可直接粘贴给同事 ([Stack Overflow][4])           |
| **想在图表内部加过滤条件**        | 进入 Explore 页面，用 **Ad-hoc Filters**（这部分一直都在）                                   |
| **条件很复杂，想联动多列**        | 加多个 Native Filters，并用 **Filter Scoping** 指定它们各自控制哪些图表                         |

---

#### 4 和旧方案相比有哪些优势？

| 旧 Filter Box | 新 Native Filters             |
| ------------ | ---------------------------- |
| 只能做下拉、多选     | 支持下拉、多选、时间范围、滑块、自由输入         |
| 无联动          | 支持级联（父-子依赖）与**默认值**          |
| 作用域粗糙        | 可在 “Scope” 精确到单张图表           |
| URL 太长／易失效   | 用 `permalink` + 压缩存储，链接更短更稳定 |
| 性能瓶颈（前端大列表）  | 服务端分页 + 异步加载                 |

---

#### 一句话结论

> **Superset 4.1 不是取消过滤器，而是全面转向「仪表盘侧边原生过滤器」；Filter Box／Filter Set 已退役。**
> 只要在仪表盘编辑页里用 “Filters” 面板，就能添加、管理、联动所有过滤器功能，效果更强也更易用。

[1]: https://preset.io/blog/apache-superset-4-0-release-notes/?utm_source=chatgpt.com "Apache Superset 4.0 Release Notes - Preset"
[2]: https://www.restack.io/docs/superset-knowledge-apache-superset-dashboard-filter?utm_source=chatgpt.com "Add Filter to Apache Superset Dashboard - Restack"
[3]: https://preset.io/blog/superset-3-0-release-notes/?utm_source=chatgpt.com "Superset 3.0 Release Notes - Preset"
[4]: https://stackoverflow.com/questions/76713320/apache-superset-native-filters?utm_source=chatgpt.com "Apache Superset Native Filters - Stack Overflow"

