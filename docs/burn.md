# 哪些任务最烧 Token？

*基于 15,983 条爬虫数据的深度提取，保留真实用户故事、剔除宏观新闻与标题党*

---

## 🎯 五大最烧场景（按严重程度排）

### 1. 🔄 Agent 无限循环 / 失控 Bug — 一夜烧掉几万刀

这是**最剧烈**的烧法：一个 bug、一个递归、一个忘了设上限的 while 循环，就能在睡觉期间烧空整个月的预算。


| $                  | 来源                                                               | 故事                                                                                                                                  |
| ------------------ | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| **$47,000 / 3 天**  | [YouTube](https://www.youtube.com/watch?v=bicRYtihQmQ)           | "A single agent bug, no errors, no alerts" — 每一次 API 调用都返回 200                                                                      |
| **$47,000 / 11 天** | [YouTube](https://www.youtube.com/watch?v=xV5C9AIUyAQ)           | 单 Agent 11 天烧光 $47k                                                                                                                 |
| **$2,847**         | [HN: ClawWatcher](https://news.ycombinator.com/item?id=47014829) | "infinite loops $2,847 + wrong AI models $1,200 + broken skills $890"                                                               |
| **$2,000 一夜**      | [HN: AgentGuard](https://news.ycombinator.com/item?id=44742710)  | "Your AI agent hits an infinite loop and racks up $2,000 in API charges overnight. This happens **weekly** to AI developers." — ▲47 |
| **$400 / 1 小时**    | [HN: OpenWorkers](https://news.ycombinator.com/item?id=46490761) | 侧项目零用户，Durable Object alarms 跑进死循环，1 小时 bill $400                                                                                   |


**结论**：Agent 失控是"尾部风险"——大多数时候没事，一旦 bug 触发就是几千到几万美金级。

---

### 2. 🤖 多 Agent / 自动化工作流 — 堆叠消耗

让 Agent 团队 7x24 跑业务流水线，不是 bug 也会月月几万。


| $                            | 来源                                                                              | 故事                                                                                                                               |
| ---------------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| **$20,000 / 2,000 sessions** | [HN #46905771](https://news.ycombinator.com/item?id=46905771)                   | Opus 4.6 Agent 团队造 C 编译器                                                                                                         |
| **$22,950 / 252 亿 tokens**   | [知乎](https://zhuanlan.zhihu.com/p/2023566534086272021)                          | Mana 团队用 Claude Code 开发，两个 Max x20 账号轮着用，日均十几个小时挂在上面                                                                             |
| **$75,000**                  | [Reddit r/AI_Agents ▲432](https://www.reddit.com/r/AI_Agents/comments/1ox8dg0/) | 某公司造 AI agent 烧 4 个月 $75k 后拔插头                                                                                                   |
| **$32,000 / 月**              | [YouTube](https://www.youtube.com/watch?v=wc_Iccr3cDY)                          | "Users were getting responses. Everything looked good. Then finance team sent me the LLM bill. $32,000/month — 4× our estimate." |
| **$20,000 / 月**              | [YouTube](https://www.youtube.com/watch?v=ofhwCrAS__o)                          | "Your AI Agent Is Quietly Burning $20K/Month"                                                                                    |
| **$6,000**                   | [HN #45041912](https://news.ycombinator.com/item?id=45041912)                   | "一周内用 Agent swarm 做完生产级 app，token cost ~$6k"                                                                                     |


**核心病灶**：每一步 Agent 都把整份上下文发回去，10 步之后上下文翻了 10 倍，每一步都在为历史内容付费。

---

### 3. ⌨️ IDE 编程 — Cursor / Claude Code "订阅幻觉"

表面是订阅，实际跑 API 模式。很多人以为装了 Cursor 就"包年"，不知道每一次 tab 补全都在刷 token。


| $                         | 来源                                                                      | 故事                                                                                               |
| ------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **~¥10,000+ / 月**         | [B站 BV1pAy5BXE5z](https://www.bilibili.com/video/BV1pAy5BXE5z)          | "给团队上 Cursor 一个多月就烧了上万元"                                                                         |
| **$4,000 / 3 月**          | [Reddit ▲1,549](https://www.reddit.com/r/AI_Agents/comments/1o0k3fv/)   | 独立开发者 3 个月烧 $4k 做 SaaS，dev 环境全 work，prod 全崩                                                      |
| **$2,800 / 月**            | [知乎](https://zhuanlan.zhihu.com/p/2028787969658463587)                  | 客服+文档工具升 GPT-5.4 后月账单从 $600 翻到 $2,800                                                            |
| **$417 一晚**               | [Reddit ▲234](https://www.reddit.com/r/ChatGPTCoding/comments/1k46x92/) | 用 Claude Code 造一款小游戏，单次实验 $417                                                                   |
| **$300 / 月（$20 订阅名义）**    | [HN #47132224](https://news.ycombinator.com/item?id=47132224)           | Claude Pro 订阅 + API 同时刷，一月 $78 + 另一月 $300                                                        |
| **$500+ / 月**             | [HN #46668399](https://news.ycombinator.com/item?id=46668399)           | "Today I use Claude Code for almost all non-trivial programming, spent $500+ just last December" |
| **$100 / day → $5 / day** | [YouTube](https://www.youtube.com/watch?v=lTXFv1Z0qfI)                  | 教程作者优化前后对比                                                                                       |


**典型路径**：买订阅 → 发现超额 → 走 API → 忘了关限流 → 月底傻眼。

---

### 4. 📚 RAG / 长上下文重复送 — 每一次查询都重传

没有做 prompt cache 的 chatbot，每次回合都把 system prompt + 全部历史发回去。


| $                       | 来源                                                                              | 故事                                                 |
| ----------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------- |
| **$4,000 → $2,000 / 月** | [Reddit r/LangChain ▲145](https://www.reddit.com/r/LangChain/comments/1pzno6m/) | "几百个日活用户，OpenAI bill 月 $4k" — 加 semantic cache 砍一半 |
| **$3,150 → $420 / 月**   | [devtk.ai 博客](https://devtk.ai/en/blog/how-to-reduce-ai-api-costs/)             | Sonnet 4.5 聊天机器人 10M in / 5M out 每天                |
| **$12,500 / day**       | [markaicode](https://markaicode.com/vs/rag-vs-long-context/)                    | 10k 查询/天用 Gemini long-context，年 $4.5M；换 RAG 节 90%  |
| **$70 / month → 几分钱**   | [HN #46760285 ▲40](https://news.ycombinator.com/item?id=46760285)               | 作者一天 bill $2.30，换 Haiku + batch + 过滤后几乎 0          |


**典型比例**（来自知乎 Claude-Mem 译文）：一个原本 20,000 token 的上下文，筛选后只需 3,000 token——**浪费了 85%**。

---

### 5. 📏 Benchmark / 评测 — 批量 rollout 一次 $40k

学术圈/工具开发者为了 benchmark 一次性烧大额——不是日常运营，但一跑就是一辆车。


| $                                    | 来源                                                                | 故事                                                               |
| ------------------------------------ | ----------------------------------------------------------------- | ---------------------------------------------------------------- |
| **$40,000 / 2.6B tokens**            | [HN Princeton HAL](https://news.ycombinator.com/item?id=45753085) | 220 agent runs × 9 benchmarks，"burned 2.6 billion prompt tokens" |
| **$38,000 / 12B tokens / 17M calls** | [HN Stanford HELM](https://news.ycombinator.com/item?id=35182743) | 17 million model calls，12 billion tokens 评测                      |
| **$23,000**                          | [HN ▲955](https://news.ycombinator.com/item?id=37484135)          | "Fine-tune Llama 2 替代 GPT-4 — 原来用 GPT-4 跑整个数据集要 $23k"            |


---

## ⚡ 最烧 Token 的 7 个**具体姿势**（共性提炼）

按被提及次数排：


| #   | 姿势                             | 说明                                     | 典型代价                          |
| --- | ------------------------------ | -------------------------------------- | ----------------------------- |
| 1   | **Agent 无限循环**                 | `while True` 掉进 loop 后每秒 N 次 API       | **$2k / 夜**，极端 **$47k / 3 天** |
| 2   | **上下文雪球**                      | 每轮对话携带完整历史，10 轮后每次都在为 350 万 token 付费   | 单次请求 $0.5+                    |
| 3   | **没做 prompt cache**            | 相同 system prompt 每次全额付，cache 开了直接 -90% | $4k/月 → $2k/月                 |
| 4   | **用 Sonnet/Opus 做能 Haiku 做的活** | 模型选型拉满，3× 成本只换 +5% 准确度                 | $70/月 → 几分钱                   |
| 5   | **给 AI 喂垃圾（"lol"、"+1"、代码块）**   | 付钱让 AI 告诉你"这不是反馈"                      | 30~50% 浪费                     |
| 6   | **大表/大库全量丢进上下文**               | 8k 联系人分页查询一次 $180（120 次 compaction）    | vs. 针对性调用 $0.003              |
| 7   | **并发/批量未开**                    | 一次 API 一次 round-trip，不 batch           | 2~4× 浪费                       |


---

## 💰 中位数对照（样本有限，但方向清晰）


| 场景                                 | 样本  | 中位月账单      |
| ---------------------------------- | --- | ---------- |
| IDE 编程（Cursor/Claude Code/Copilot） | 13  | **$300**   |
| Agent 无限循环                         | 10  | **$2,000** |
| RAG / 长上下文                         | 18  | **$1,300** |
| 多 Agent 自动化                        | 38  | **$1,500** |
| Benchmark / 评测                     | 4   | **$1,000** |


> **要点**：IDE 编程基数低但人数多（整体黑洞），Agent 单点极高（尾部风险），RAG 是"慢烧"（每天都在流）。

---

## 🧯 社区总结的"省 Token 六板斧"

从高赞帖子反复出现的省钱姿势汇总：

1. **开 prompt cache**（Claude Sonnet 4.5 cached reads $3.00/M → $0.30/M，直接 -90%）
2. **选对模型**（Haiku / Gemini 2.5 Flash-Lite $0.10/M，对简单任务够用）
3. **Batch 调用**（小时级批处理代替实时，折扣 ~50%）
4. **Filter before AI**（正则/规则先筛，别让 LLM 判断"lol"是不是反馈）
5. **短输出**（用 `H/M/L` 代替 `high/medium/low`，40 字 title 而不是段落）
6. **硬上限 + 告警**（AgentGuard 类工具，API call 频率 + 累计 $ 双阈值熔断）

---

## 🔗 如何继续深挖

- 这份报告对应的**原始条目**：`data/curated/analysis.csv`（15,983 行）按 `token_burn_signal` desc + `cost_usd` 筛
- 浏览器查看：`.venv/bin/python viewer.py` → 选"🔥 极燃 ≥0.7"筛选器
- 单平台深挖：`data/curated/{reddit,hackernews,zhihu}.md` 已按热度排序

