---
{"dg-publish":true,"permalink":"/01.工作/工具使用/Superset/Superset 4.1对比1.5版本升级/","title":"Superset 4.1对比1.5版本升级"}
---



**核心结论（先看这一段即可）**
从 Superset 1.5（2022 年 5 月）升级到 4.1（2024 年 11 月）要跨越 2 → 3 → 4 三个大版本和多个小版本。整个过程中，Superset 完成了底层架构重构、可视化体验革新、数据治理与安全模型强化，以及性能与稳定性的大幅提升。对终端用户来说，4.1 提供了更丰富的图表类型、可对比的时间分析、新的标签系统、拖放式编辑器、Catalog 切换、Slack 头像与自定义报表标题等功能；对运维与开发者来说，4.x 清理了大量过期代码与特性标志，改进了缓存、权限和数据库连接模型，使部署与二次开发更容易、更安全。([Preset][1], [Preset][2], [LinkedIn][3])

---

## 版本里程碑简述

| 版本  | 发布时间       | 主要定位                                                                                               |
| --- | ---------- | -------------------------------------------------------------------------------------------------- |
| 1.5 | 2022-05-17 | **LTS**；聚焦原生过滤器性能、URL 缓存、MetastoreCache，新增 DuckDB/Azure Data Explorer 适配等([Preset][4])             |
| 2.0 | 2022-07    | 清除技术债、统一 UI、Viz Picker、横向条形图、`dataset()` Jinja 宏等([Preset][5])                                     |
| 3.0 | 2023-10    | 稳定性与简化为主，进一步删除旧特性旗标、精简代码路径([Preset][6])                                                            |
| 4.0 | 2024-04-08 | **架构大清洗**：移除 Filter Box / Filter Set、引入 Tagging 系统、Alerts\&Reports UI 重写，减少 72 % 前端漏洞([Preset][2]) |
| 4.1 | 2024-11-15 | **能力收敛与增强**：300 + 修复，新增时间对比图表、Catalog 切换、Dashboard 元信息栏、自定义刷新/邮件标题等([Preset][1])                   |

---

## 视觉与分析体验升级

### 新增或改进图表

* **Big Number With Time Comparison** 与 **Time-Compare Table**——一步完成同比/环比展示([Preset][1])
* 新增 **Heatmap、Histogram、Sankey、Rose-Pie** 等多种 ECharts v2 图表；Sunburst 已迁移到 ECharts 并自动升级旧报表([Preset][1], [Preset][2])
* 2.0 起支持 **横向条形图**、3.0/4.0 强化拖放与分组交互，4.1 继续在 Dashboard 编辑器中提供更清晰的拖拽定位区([Preset][5], [Preset][2])

### 原生过滤器 & 交互

* 1.5 解决长 URL 问题并支持 **过滤器依赖链**；4.0/4.1 增加“当前周/月/年”快捷时间、`{{ get_time_filter() }}` 宏，Dash Filters 跨组件绑定更稳健([Preset][4], [Preset][1])
* 4.1 的 Dashboard Header **元数据信息栏** 直接显示所有者与修改时间，提高协作透明度([Preset][1])

---

## 数据治理与安全

| 功能领域       | 1.5 现状                        | 4.1 变化                                                                               |
| ---------- | ----------------------------- | ------------------------------------------------------------------------------------ |
| 权限模型       | `all_database_access` 曾偶发权限泄露 | 修复并重新校准 workspace 级权限([Preset][1])                                                   |
| 标签体系       | 无                             | 4.0 引入 **Tagging System**，4.1 继承并完善 REST API 支持([Preset][2])                         |
| Catalog 支持 | 仅 schema 切换                   | **BigQuery / Trino / Snowflake 等 Catalog 切换**，统一在 SQL Lab、数据集创建、数据角色中体现([Preset][1]) |
| OAuth 数据库  | 外部配置                          | 4.1 通过 Preset 支持 BQ、Databricks、Snowflake、Trino OAuth-PKCE，一键继承原库权限([Preset][1])      |

---

## 性能与稳定性

* 1.5 引入 **SupersetMetastoreCache**，将 URL 状态持久化到 Metastore；4.x 在此基础上移除旧的客户端/仪表盘缓存旗标，统一缓存策略。([Preset][4], [Preset][2])
* 4.1 在 Arrow ADBC 查询管线优化后，**部分查询场景性能提升可达 5 倍**([LinkedIn][3])
* 4.1 合并 **300+ Bug Fix**；4.0 删除 15 k + 旧代码、减少 40 + 依赖包，前端安全漏洞数从 90 → 25。([Preset][1], [Preset][2])

---

## 报表、通知与协作

* **Alerts & Reports**：4.0 完全重做多步向导；4.1 允许自定义邮件主题、从 Slack 抓取头像，下载 Dashboard PDF/PNG 更稳定。([Preset][2], [Preset][1])
* **Dashboard 刷新频率**：4.1 支持自定义 Cron 表达式，而 1.5 仅有固定下拉选项。([Preset][1])

---

## 开发者与运维视角

| 领域            | 重大变化                                                                                                                                                      |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Feature Flags | 4.0 批量删除或默认开启 20 余个旧旗标（Filter Box、Client Cache 等），降低配置复杂度。([Preset][2])                                                                                   |
| API/插件        | 2.0-4.1 不断扩充 Chart Plugin API；4.1 引入 `roseType`、Pivot CSV 导出、HTML 渲染开关；DSL-级别宏（`dataset`, `where_in`, `get_time_filter`）更加丰富。([Preset][5], [Preset][1])   |
| 依赖支持          | Python ≥ 3.9、SQLAlchemy v2、Ant Design v5（前端）；官方 Docker/Helm 配置同时更新。([Preset][2])                                                                          |
| 升级难度          | 4.x 保持 **无破坏性数据库迁移**；建议按“1.5 → 2.1 → 3.1 → 4.1”顺序逐级执行 `superset db upgrade` 并核对 `UPDATING.md`；LTS 1.5 仍可获得关键安全补丁，方便分阶段切换。([Apache Lists][7], [GitLab][8]) |

---

## 升级路线与建议

1. **评估插件/自定义代码**：若使用了 Filter Box、短链 Redirect API 等 4.0 已删除特性，需先迁移。
2. **备份 Metadata & 数据库**：升级脚本会自动迁移 schema，但不可逆。
3. **逐级升级并验证**：推荐每跨一个大版本做一次预生产验证；重点关注缓存、Feature Flag、RBAC 变更。
4. **启用新特性**：

   * 在 `superset_config.py` 打开 `TAGGING_SYSTEM = True`、`DRILL_BY = True` 等常用旗标；
   * SQL Lab > Database 勾选 **Allow changing catalogs**；
   * 配置 `ALERT_REPORTS_NOTIFICATION_DASHBOARD_ENABLE_CRON` 以使用自定义刷新。
5. **观测指标**：用 4.1 自带的 **日常健康监控仪表盘**（Superset Monitor）验证查询/缓存命中与 Celery Worker 负载。

---

### 一句话总结

如果说 1.5 让 Superset 迈入了 **更快、更稳** 的 LTS 阶段，那么 4.1 则把 Superset 打造成一个 **更现代、更易用、更安全** 的数据可视化平台；升级后，你既能获得丰富的时间对比分析与标签治理，也能享受显著性能提升和更简洁的维护体验。

[1]: https://preset.io/blog/apache-superset-4-1-release-notes/ "Apache Superset 4.1 Release Notes | Preset"
[2]: https://preset.io/blog/apache-superset-4-0-release-notes/?utm_source=chatgpt.com "Apache Superset 4.0 Release Notes - Preset"
[3]: https://www.linkedin.com/posts/maximebeauchemin_apache-superset-41-release-notes-activity-7267230579471855616-AVc0?utm_source=chatgpt.com "Apache Superset 4.1 Release Notes | Maxime Beauchemin - LinkedIn"
[4]: https://preset.io/blog/apache-superset-1-5-release-notes/ "Apache Superset 1.5: Release Notes | Preset"
[5]: https://preset.io/blog/apache-superset-2-0-release-notes/?utm_source=chatgpt.com "Apache Superset 2.0: Release Notes - Preset"
[6]: https://preset.io/blog/superset-3-0-release-notes/?utm_source=chatgpt.com "Superset 3.0 Release Notes - Preset"
[7]: https://lists.apache.org/thread/73n73gdfkklgc3crdxq65dr54pcn5ndt?utm_source=chatgpt.com "[ANNOUNCE] Apache Superset version 4.1.1 released-Apache Mail ..."
[8]: https://git-ce.rwth-aachen.de/machine-data/mitm-superset/-/tree/a64af7e565aaf3fb4bef3b97cd0948f253b1519a/RELEASING/release-notes-1-5?utm_source=chatgpt.com "RELEASING/release-notes-1-5 ... - GitLab der RWTH Aachen"
