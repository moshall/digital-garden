---
{"dg-publish":true,"permalink":"/01.工作/工具使用/Superset/Superset Dashboard 性能优化/","title":"Superset Dashboard 性能优化","tags":["superset"]}
---

superset1.5.1版本，有什么dashboard的性能优化方法吗？避免用户高频并行请求数据库查询 因为很多数据都是T+1的数据，就是今天看昨天的及以前的数据，所以不用反复请求最新数据 这种情况，有什么缓存机制可以提升dashboard的效率吗

---

在 Superset 1.5.1 中，如果你的数据主要是 **T+1（昨天及更早）静态数据** ，确实可以通过一系列缓存机制和配置优化 dashboard 性能，避免用户高频并发查询数据库。以下是推荐的优化方法：

---

### ✅ 一、开启 Superset 的查询缓存机制

Superset 1.5.1 默认集成了基于 Flask-Cache 的查询缓存，可以显著减少数据库压力。
#### 配置方式（在 superset\_config.py 中）：

```python

CACHE_CONFIG = {
    'CACHE_TYPE': 'redis',
    'CACHE_DEFAULT_TIMEOUT': 3600,  # 缓存一小时
    'CACHE_KEY_PREFIX': 'superset_',
    'CACHE_REDIS_URL': 'redis://localhost:6379/0',  # 指向你的 Redis 实例
}

DATA_CACHE_CONFIG = CACHE_CONFIG  # Chart 数据缓存

```

> ✅ 建议使用 Redis 作为缓存后端，避免内存压力或缓存失效。

---

### ✅ 二、启用 chart 层级缓存（查询缓存）

每个 chart 的缓存可通过图表配置中的 `Advanced Analytics → Cache Timeout` 单独设置。

- **设置建议** ： `3600` 秒（1小时）或更长（例如 T+1 数据可以缓存 `86400` 秒）

如果你有多个用户同时访问 dashboard，且数据为历史数据，则完全可以缓存较长时间。

---

### ✅ 三、Dashboard 层级缓存（视图级别缓存）

虽然 Superset 1.5.1 没有专门的 Dashboard 页面缓存，但通过 chart 缓存 + query result 缓存，几乎等效于视图缓存。

#### 配合使用方式：

- 图表缓存 + 数据源查询缓存 + 浏览器端 CDN 缓存（前端缓存）；
- 设置 Dashboard 组件的 auto-refresh 时间较长（或不设置）避免反复刷新。

---

### ✅ 四、禁用 auto-refresh（避免用户高频自动刷新）

在 dashboard 页面中，每个图表和整个 dashboard 可以设置自动刷新频率。建议将其关闭或设置为非常长的时间间隔。

---

### ✅ 五、定时离线物化表（适用于大表和聚合需求）

如果某些图表依赖大表做复杂聚合，可以提前每日离线生成结果表（如物化视图或新建中间表），然后供 dashboard 使用。

示例流程：

1. 每天 T+1 凌晨定时生成聚合表（存入 DWD/DWS 层）；
2. Superset chart 指向该轻量中间表；
3. 查询更快，缓存命中率更高。

---

### ✅ 六、合理设计 SQL 逻辑和数据集拆分

- 避免在 chart 层直接做复杂聚合逻辑，应尽量通过物理表、ETL 处理；
- 将用户常看的一些维度或时间窗口提前聚合成宽表；
- 拆分多个 dashboard 页面，每页加载更少的图表。

---

### ✅ 七、前端浏览器缓存辅助

Superset 会缓存 chart 的 API 请求结果一段时间，可借助 CDN 或浏览器缓存进一步降低频率。

---

### ✅ 小结：推荐组合策略

| 优化项 | 建议值/策略 |
| --- | --- |
| Chart 缓存时间 | 1小时（3600秒）或更长（T+1数据可用86400秒） |
| 数据源缓存 | 启用 Redis，缓存查询结果 |
| Auto-refresh | 关闭，或设置为 3600 秒以上 |
| ETL 优化 | 每天定时生成 T+1 聚合表，供 chart 使用 |
| 用户使用建议 | 限制 dashboard 中图表数量（<12个为佳） |

---

如果你希望我帮你写一个 `superset_config.py` 的示例配置文件，或给出你当前的 Redis 缓存配置，我可以继续优化建议。