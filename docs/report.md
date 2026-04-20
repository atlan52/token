# AI Token 消耗研究报告

_生成于 2026-04-19，数据源：12 平台爬虫 (`data/raw/*.jsonl`)_

## 总览

- 共采集 **15,717** 条去重发帖 / 视频 / 帖子
- 覆盖平台（12）：

  | 平台 | 条数 | 备注 |
  | --- | ---: | --- |
  | hackernews | 6,191 | 英文技术讨论主力 |
  | zhihu | 3,842 | 中文长文 / 专栏 |
  | bilibili | 2,343 | 中文 AI 教程/体验视频 |
  | github_discussions | 837 | 开发者 issue / 讨论 |
  | reddit | 625 | r/ClaudeAI, r/cursor, r/AI_Agents 等 |
  | youtube | 588 | 视频博主教程 |
  | weibo | 555 | 中文短评 |
  | x_nitter | 437 | Twitter/X 镜像短贴 |
  | google_web | 149 | 博客/厂商文章 |
  | medium | 56 | 英文 AI 博客 |
  | devto | 49 | 开发者笔记 |
  | substack | 45 | 深度长文 |

- 语言分布：英文 **8,977** (57%) ／ 中文 **6,740** (43%)
- 总观看量 ~2.04 亿（主要来自 B 站 + YouTube），总评论 ~40.5 万
- 产出：`data/curated/{platform}.md`（去重后逐条）、`analysis.md`（按 task_category 分桶）、`analysis.csv`（11,892 行结构化）

---

## 一、谁在用 AI？

### 1. 地区分布

- **英文世界** (HN / Reddit / Medium / Substack / Dev.to / X / GitHub Discussions / Google 博客) — **8,678 条**，以硬核开发者、独立创业者、小型 SaaS 团队为主。
- **中文世界** (B 站 / 知乎 / 微博) — **3,214 条**，以技术博主、付费课程向用户、"省钱攻略"爱好者为主。B 站以"保姆教程"和"白嫖方案"为主，知乎以行业长文分析为主。
- **视频平台** (YouTube + B 站) 合计 **2,616 条**，贡献 2.03 亿总观看 — 教程类是全民教育入口。

### 2. 提到最多的模型 / 产品

1. Claude (Sonnet / Opus / Haiku)
2. GPT-4 / GPT-4o
3. Cursor（IDE，中文圈"烧钱 / 省钱"话题的绝对主角）
4. DeepSeek (V3 / R1) — 中文白嫖教程顶流
5. Gemini (1.5 / 2.5 Pro / 3 Pro)
6. GPT-3.5（历史参照）
7. Llama-3 / Gemma（LocalLLaMA 自托管）
8. Qwen 3 / Qwen 3.5
9. Mistral / Mixtral
10. Claude Code / Claude Dispatch（工具形态独立成议题）

### 3. 用户画像

- **资深软件工程师 / 技术 lead**："16 年经验 sr. software engineer"（r/ClaudeAI 2,283 分）、Manus 前后端 lead（r/LocalLLaMA 1,948 分）。
- **独立 / 单人创业者**："CTO who recently went solo founder"（r/AI_Agents 1,549 分），3 小时搭社媒自动化。
- **中文程序员博主**：鱼皮、木子不写代码等 B 站 up，"团队上 Cursor 一个月烧了上万元"。
- **AI Benchmark 研究者**：Princeton CITP HAL 团队，220+ agent runs、$40,000、26 亿 prompt tokens。
- **羊毛党 / 白嫖用户**：B 站"GPT5、Claude4、Grok4、Gemini2.5Pro、DeepSeek-R1 免费白嫖"类标题。
- **金融 / 量化爱好者**：B 站"glm5.1 烧了 8 千万 token 极限测评江恩理论"、FoodTruckBench 商业模拟。
- **企业工具对接者**：Devin × 高盛 / 花旗 40,000 工程师部署。

---

## 二、用来做什么？

按规则层 `task_category`（单标签）聚合：

| 桶 | 条数 | 占比 |
| --- | ---: | ---: |
| coding | 6,497 | 41.3% |
| other | 3,913 | 24.9% |
| agent | 1,612 | 10.3% |
| chat | 1,453 | 9.2% |
| rag | 1,100 | 7.0% |
| writing | 996 | 6.3% |
| translation | 146 | 0.9% |

### coding（42.6%，最大一桶）

- [reddit] *Spent 4,000 USD on AI coding. Everything worked in dev. Nothing worked in production.* (1,549 分) — SaaS 创业者 3 个月烧 $4k，生产环境每功能踩雷。<https://www.reddit.com/r/AI_Agents/comments/1o0k3fv/>
- [reddit] *I got slammed for spending $417 making a game with Claude Code. Just made another one with Gemini 2.5 for free...* — 对比 Cursor + Gemini 的上下文利用率。<https://www.reddit.com/r/ChatGPTCoding/comments/1k46x92/>
- [bilibili] *7 个 Cursor AI 极限省钱大法* — "给团队上 Cursor 一个多月就烧了上万元"。<https://www.bilibili.com/video/BV1pAy5BXE5z>

### agent（9.8%）

- [hackernews] *Show HN: AgentGuard* — "Your AI agent hits an infinite loop and racks up $2000 in API charges overnight. This happens weekly to AI developers." <https://news.ycombinator.com/item?id=44742710>
- [zhihu] Ethan Ding 译文《大模型经济学真相》 — "10 分钟运行时间刚好足够让人们发现 for 循环…用户变成 API 编排者，在 Anthropic 费用上运行 24/7 代码转换引擎。" <https://zhuanlan.zhihu.com/p/1935794192564609333>
- [hackernews] Princeton HAL — "220 agent runs across 9 benchmarks…$40,000…'burned' 2.6 billion prompt tokens." <https://news.ycombinator.com/item?id=45753085>

### rag（7.0%）

- [google_web] *Cut AI API Costs 80%* — 10M in / 5M out per day，单月 $3,150 可降到 $420。<https://devtk.ai/en/blog/how-to-reduce-ai-api-costs/>
- [zhihu] *AI 编程节省 95% token…开源记忆系统登顶 GitHub 热榜* — 三层渐进式检索把 20,000 token 上下文压到 3,000 token。<https://zhuanlan.zhihu.com/p/2003814331087869321>

### chat / writing / translation（合计 14%）

- [reddit] *I spent 3 hours building an agent that for $0.15 automates my brand's social media* — Claude + Google Sheets + Zapier，每周 $0.15。<https://www.reddit.com/r/AI_Agents/comments/1ld2iw1/>
- [bilibili] "ChatGPT 论文写作"教程多条，播放几十万但个人消耗极小。
- translation 桶极小（77 条），说明翻译场景很少单独谈 token 成本 — 常被折叠进 coding / chat。

---

## 三、什么最烧 Token？

从 `token_burn_signal >= 0.39` 的 **1,100+ 条**中归纳：

### 1. Agent 无限循环失控

> "Your AI agent hits an infinite loop and racks up $2000 in API charges overnight. This happens weekly to AI developers." — *AgentGuard* (HN) <https://news.ycombinator.com/item?id=44742710>

> "a single agent can burn $50+ in minutes, get stuck in infinite loops, or call dangerous actions without oversight." — *SteerPlane* (HN) <https://news.ycombinator.com/item?id=47325207>

### 2. Agent for-loop 刷任务

> "10-20 分钟的连续运行时间刚好足够让人们发现 for 循环……一百亿个 Token。相当于一个月内 12,500 本《战争与和平》。" (zhihu) <https://zhuanlan.zhihu.com/p/1935794192564609333>

> "Over nearly 2,000 Claude Code sessions and $20,000 in API costs… Well there goes my weekend project plans." (HN) <https://news.ycombinator.com/item?id=46906269>

### 3. 长上下文 / Context window 爆炸

> "MCP: 18M tokens | 80m time | $180 cost ／ Max: 238 tokens | 27s time | $0.003 cost" — HubSpot 10 万联系人分页，MCP 走了 120 次 compaction 把上下文塞满。 (HN Show: Max) <https://news.ycombinator.com/item?id=47278802>

> "一个原本需要 20000 Token 才能完整加载的上下文，经过筛选后可能只需要 3000 Token。" — Claude-Mem (zhihu)

> "Claude 过去的最大痛点——它会不断重新解释核心逻辑和粘贴整文件。" — *$417 vs $0 game* (reddit)

### 4. 频繁新对话 / 缺少 Prompt 缓存

> "每次新会话都是一张白纸……开发者只能一遍遍重复解释，时间和 Token 都在这种'复读'中白白流失。" (zhihu Claude-Mem)

> "cached reads on Claude Sonnet 4.5 drop from $3.00/M to just $0.30/M — a 90% reduction on input tokens." (devtk.ai)

> [bilibili] *AI 开发避坑指南：KV 缓存让成本暴降 80%？* — "单任务成本从 14 美金砍到 3 毛 8"。<https://www.bilibili.com/video/BV1Wd6DBEEtQ>

### 5. Cursor / IDE 后台跑补全

> "I wasted about 5 hours today… it has been executing a simple file refactor task for 783 seconds as I write this." — *$100 Claude Max plan review* (reddit 2,283 分) <https://www.reddit.com/r/ClaudeAI/comments/1l5h2ds/>

> [bilibili] *我以为发现了 Cursor 的隐藏福利，结果账单让我哭了* <https://www.bilibili.com/video/BV1V7N9zuE2b>

> "I have burned $78.19 in API token costs with my $20/month Claude Pro subscription. In January I burnt over $300." (HN #47132224)

### 6. 订阅制被 vibe-coder 反薅

> "Anthropic 取消了 Claude Code 最初的 $200/月无限套餐……在这个新世界里，任何订阅模式下都无法提供无限使用。" (zhihu Ethan Ding 译)

### 7. Benchmark / 评测跑大量 rollout

HAL 初始化 220 agent runs × 9 benchmarks = **$40,000、26 亿 prompt tokens**。FoodTruckBench 测 23 模型，每轮 $0.20–$36 × 30 日模拟。

---

## 四、惊人数字（已过滤噪音）

| 金额 / 量 | 场景 | 来源 |
| ---: | --- | --- |
| **~$40,000 / 2.6B tokens** | Princeton HAL 评测 9 个 agent benchmark | [HN #45753085](https://news.ycombinator.com/item?id=45753085) |
| **$20,000 / 2,000 sessions** | Opus 4.6 agent 造 C 编译器 | [HN #46906269](https://news.ycombinator.com/item?id=46906269) |
| **$4,000** | 3 个月 vibe-code 出 SaaS，上线即崩 | [reddit 1o0k3fv](https://www.reddit.com/r/AI_Agents/comments/1o0k3fv/) |
| **$3,150 → $420 / 月** | Sonnet 4.5 聊天机器人 10M/5M tokens 每日 | [devtk.ai](https://devtk.ai/en/blog/how-to-reduce-ai-api-costs/) |
| **$2,000 overnight** | Agent 无限循环 | [HN #44742710](https://news.ycombinator.com/item?id=44742710) |
| **$417** | Claude Code 单人造词游戏一轮 | [reddit 1k46x92](https://www.reddit.com/r/ChatGPTCoding/comments/1k46x92/) |
| **$300 / 月 ($20 订阅名义)** | Claude Pro 订阅但走 API 狂刷 | [HN #47132224](https://news.ycombinator.com/item?id=47132224) |
| **~1 万元 RMB / 月** | 小团队上 Cursor 一个多月 | [bilibili BV1pAy5BXE5z](https://www.bilibili.com/video/BV1pAy5BXE5z) |
| **10B tokens / 月** | Claude Code 单用户 viberank 榜，≈每月 12,500 本《战争与和平》 | [zhihu 1935794192564609333](https://zhuanlan.zhihu.com/p/1935794192564609333) |
| **8,000 万 tokens / 轮** | B 站 up 主 GLM5.1 测江恩理论 | [bilibili BV1ZXXaBDEuw](https://www.bilibili.com/video/BV1ZXXaBDEuw) |

---

## 五、研究方法与局限

### 采集
- 12 平台 crawler 在 `crawlers/` 下，`run.py` 入口，受控于 `config.py`
- 话题过滤 `TOPIC_TOKENS_EN` / `TOPIC_TOKENS_ZH` — 必须命中 AI 词或 token/成本词
- 单平台上限 3000 条，每关键词 80 条，HN Algolia 每查询 100 hits
- producthunt 因 Cloudflare Turnstile 无法穿透（headless 和有头模式均被拦），已优雅跳过

### 分析
- Pass 1（规则层）：`analyze.py` 的 `MODEL_PATTERN`、`USD_PATTERN` / `CNY_PATTERN`（¥→USD 1/7.2）、`BURN_TERMS`、`TASK_KEYWORDS`（6 桶）
- Pass 2（LLM）：`ANALYZE_WITH_LLM=1` 启用 Haiku 4.5 精标 top 20% engagement 切片 → `enriched_{platform}.jsonl`。**本次未启用**

### 平台偏向
- HN / Reddit / Medium / GitHub Discussions → 一手技术故事，数字真实，英语中心化
- B 站 / YouTube → 教程导向，许多是"卖课 / 子站引流 / 白嫖"
- 知乎 → 观点与软文并存，质量方差大
- X (nitter) / 微博 → 短贴，`token_burn_signal` 几乎全 0

### 已知误差
- 规则层 `cost_usd` 正则会误抓"$20 订阅"、"¥200 充值"、甚至"$500,000 crypto heist"（非 token 账单），已在第四节人工剔除
- `task_category` 单标签最多命中；`coding` 关键词（cursor, copilot, code…）极宽泛，吞并了其他桶，占比偏高
- `MODEL_PATTERN` 未覆盖 `GPT-5`、`Opus 4.6`、`Gemma 4` 等新模型，需扩词表
- Discord / Slack / 企业群聊完全没采，幸存者偏差明显
- 当日快照（2026-04-19），热点随时间漂移

### 附录
- `data/curated/_index.md` — 12 平台汇总
- `data/curated/analysis.md` — 平台 × 任务类别分桶代表性摘要
- `data/curated/analysis.csv` — 15,717 行结构化标签
- `data/curated/{platform}.md` — 逐平台原文去重清单
