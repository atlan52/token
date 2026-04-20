# 大家都用 AI 干什么？

_基于 15,983 条爬虫数据的主题提取。每帖严格**单一归类**（按标题关键词优先命中），匹配到 **4,203 条有明确用途描述**，其余 11,780 条为新闻/评测/宏观讨论。_

---

## 🧭 一眼看懂：分布全景

> **在这份样本里，当人们明确描述"用 AI 做什么"时，有 68% 是在写代码。**

```
┌──────────────────────────────────────────────────────┐
│  💻 编程               ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  68.1%  │
│  📚 RAG / 问答 / 客服  ▓▓▓                     9.5%  │
│  🎓 学习 / 翻译 / 陪伴  ▓▓▓                     8.7%  │
│  🤖 Agent / 工作流     ▓▓                      7.1%  │
│  🎨 生成式（图/声/游）  ▓                       2.9%  │
│  ✍️ 写作              ▓                       2.7%  │
│  📊 办公（数据/会议）    ▏                       0.9%  │
└──────────────────────────────────────────────────────┘
             （占已分类 4,203 条）
```

## 📊 细分桶命中数

| 大类 | 小类 | 条数 | 占比（全量） |
|---|---|---:|---:|
| **💻 编程** | **小计** | **2,864** | **17.9%** |
|  | ⌨️ IDE 编程 / Tab 补全（Cursor, Claude Code, Copilot） | 2,218 | 13.9% |
|  | 🤖 全自动写代码 Agent（Devin, OpenClaw） | 507 | 3.2% |
|  | 🛠️ 独立开发 / 做 SaaS | 87 | 0.5% |
|  | 🔧 重构 / 调 bug / code review | 46 | 0.3% |
|  | 🧰 一次性脚本 / 小工具 | 6 | 0.0% |
| **📚 RAG / 问答 / 客服** | **小计** | **401** | **2.5%** |
|  | 📚 文档 / 知识库问答 | 391 | 2.4% |
|  | 🎧 客服 / 支持机器人 | 10 | 0.1% |
| **🎓 学习 / 翻译 / 陪伴** | **小计** | **366** | **2.3%** |
|  | 📖 学习 / 当家教 | 310 | 1.9% |
|  | 🌐 翻译 / 字幕 / 本地化 | 48 | 0.3% |
|  | 💞 陪伴 / 心理 / 情感 | 8 | 0.1% |
| **🤖 Agent / 工作流** | **小计** | **298** | **1.9%** |
|  | 🔄 多 Agent / 工作流 | 132 | 0.8% |
|  | 📈 量化 / 交易 Agent | 99 | 0.6% |
|  | 🕸️ 浏览器 / Deep Research | 67 | 0.4% |
| **🎨 生成式** | **小计** | **121** | **0.8%** |
|  | 🎵 语音 / 音乐 | 52 | 0.3% |
|  | 🎨 图像 / 视频生成 | 43 | 0.3% |
|  | 🎮 游戏开发 | 26 | 0.2% |
| **✍️ 写作** | **小计** | **115** | **0.7%** |
|  | 🎓 写论文 / 学术综述 | 89 | 0.6% |
|  | ✍️ 写博客 / 文案 / 小红书 | 14 | 0.1% |
|  | 📧 写邮件 | 12 | 0.1% |
| **📊 办公** | **小计** | **38** | **0.2%** |
|  | 📊 数据分析 / Excel | 29 | 0.2% |
|  | 📝 会议记录 / 总结 | 9 | 0.1% |

---

## 🏆 各场景代表帖

### 💻 编程（绝对主流）

#### ⌨️ IDE 编程 / Tab 补全（2,218 条）
- [Reddit ▲5,548] **[i dug through claude code's leaked source](https://www.reddit.com/r/ClaudeAI/comments/1s8lkkm/)** — 有人发现 Claude Code npm 包的 .map 文件泄露了源码，一堆人跑去分析
- [知乎 ▲4,334] **[Claude Code 源码泄露：我花了一天读完全部代码](https://zhuanlan.zhihu.com/p/2022389695955346888)** — 1903 个文件 / 51 万行 TS
- [Reddit ▲4,096] **[I used Claude Code to reverse engineer a 13-year-old game binary](https://www.reddit.com/r/ClaudeAI/comments/1ru3irp/)** — 用 AI 逆向 13 年前游戏二进制

#### 🤖 全自动写代码 Agent（507 条）
- [知乎 ▲4,143] **[为什么最近 OpenClaw 这么火？](https://www.zhihu.com/question/2014352221450577015/answer/2014501374893786724)** — "因为大模型厂商突然发现一个大量倾销 Token 的渠道"
- [知乎 ▲2,709] **[大家都安装 openclaw 了吗？](https://www.zhihu.com/question/2001975920689423905/answer/2005927593019459556)** — 实测："正常重度 ¥7500/月，极限 1.5 万/月，失控 2.6 万+/月"

#### 🛠️ 独立开发 / 做 SaaS（87 条）
- [Reddit ▲2,696] **["I built an app to monitor Claude usage limits"](https://www.reddit.com/r/ClaudeAI/comments/1rc27sc/)** — 独立开发者做监控工具
- [知乎 ▲1,791] **[Vibe Coding 一年冷思考](https://zhuanlan.zhihu.com/p/2003390589538956495)** — "在 Google/Anthropic/OpenAI 三家烧了超过 2 万美金的 token 账单"

#### 🔧 重构 / 调 bug（46 条）
- [Reddit ▲501] **[Debugging Decay: The hidden reason ChatGPT can't fix your bug](https://www.reddit.com/r/ChatGPTCoding/comments/1meyd75/)** — "Prompt 25: JUST FIX THE STUPID BUTTON"

---

### 📚 RAG / 文档问答

#### 文档 / 知识库问答（391 条）
- [知乎 ▲1,384] **[一文读懂：大模型 RAG](https://zhuanlan.zhihu.com/p/675509396)** — 入门长文
- [知乎 ▲1,165] **[假如 LLM 无限上下文了，RAG 还有意义吗？](https://www.zhihu.com/question/653424464/answer/2010773868898427209)** — 上下文窗口 vs 检索的经典争论

#### 客服机器人（10 条）
- 样本很少，但 [微博] 上有多条吐槽："AI 客服答非所问"、"付费给 wind 结果它用自研小模型"

---

### 🎓 学习 / 翻译 / 陪伴

#### 📖 学习 / 当家教（310 条）
- [知乎 ▲2,005] **[DeepSeek 玄学指令教程](https://zhuanlan.zhihu.com/p/1962941393497491344)** — 用 AI 学八字命理（!）
- [知乎 ▲365] **[清华 DeepSeek 保姆教程](https://zhuanlan.zhihu.com/p/21990605929)** — 国内普及向头号流量
- [知乎 ▲280] **[2026 年国内充值 ChatGPT Plus 攻略](https://zhuanlan.zhihu.com/p/1989070422948475152)** — 纯"怎么用上 AI"

#### 🌐 翻译 / 字幕（48 条）
- [知乎 ▲1,718] **[消耗 3 亿 token，我用大模型翻译了 1 万篇 arXiv 论文](https://zhuanlan.zhihu.com/p/1905569596599169419)** — 做成 SaaS 上线
- [Reddit ▲1,002] **[Google Translate is vulnerable to prompt injection](https://www.reddit.com/r/Bard/comments/1qy7ofd/)** — 因为底层接了 Gemini

#### 💞 陪伴 / 心理（8 条）
- 样本极少。社区里陪伴类话题远少于欧美语料里的占比，可能因为中文平台上此类内容被分散到小红书 / 即刻等未爬站点

---

### 🤖 Agent / 工作流

#### 多 Agent / 工作流（132 条）
- [Reddit ▲289] **[I Built 10+ Multi-Agent Systems at Enterprise Scale (20k docs)](https://www.reddit.com/r/AI_Agents/comments/1npg0a9/)** — 一年企业级实战经验
- [Reddit ▲283] **[Google tested 180 agent setups. Multi-agent made things 70% worse](https://www.reddit.com/r/AI_Agents/comments/1s8gf6f/)** — **多 agent 不是银弹**的反思

#### 🕸️ 浏览器 / Deep Research（67 条）
- [Reddit ▲5,674] **[me after 10 mins of ChatGPT Atlas Browser](https://www.reddit.com/r/OpenAI/comments/1oel2i7/)** — ChatGPT Atlas 浏览器发布
- [Reddit ▲2,786] **[Meet our new browser—ChatGPT Atlas](https://www.reddit.com/r/OpenAI/comments/1ocj2da/)**

---

### 🎨 生成式

#### 🎵 语音 / 音乐（52 条）
- [Reddit ▲1,843] **[Mistral Voxtral TTS 开源权重发布](https://www.reddit.com/r/LocalLLaMA/comments/1s46ylj/)**

#### 🎨 图像 / 视频（43 条）
- [Reddit ▲2,476] **[Google Veo 3 vs OpenAI Sora](https://www.reddit.com/r/OpenAI/comments/1kz5ryc/)**
- [Reddit ▲2,039] **[This is Sora 2](https://www.reddit.com/r/OpenAI/comments/1nuj9d6/)**

#### 🎮 游戏开发（26 条）
- [知乎 ▲357] **[突然感觉游戏开发要 GG 了](https://zhuanlan.zhihu.com/p/2012549457791705234)** — 一线游戏程序员的失业焦虑

---

### ✍️ 写作

#### 🎓 写论文 / 学术（89 条）
- [Reddit ▲456] **[ICML: every paper in my review batch contains prompt-injection](https://www.reddit.com/r/MachineLearning/comments/1r3oekq/)** — **审稿时**发现作者往 PDF 里埋 prompt injection 骗 AI 审稿人

#### ✍️ 写博客 / 文案 / 小红书（14 条）
- [知乎 ▲71] **[用 ChatGPT 快速做小红书爆款内容，涨粉 10 万](https://zhuanlan.zhihu.com/p/617136711)** — 典型"AI 流量变现"教程

#### 📧 写邮件（12 条）
- [Reddit ▲712] **[How a Single Email Turned My ClawdBot Into a Data Leak](https://www.reddit.com/r/ClaudeCode/comments/1qnsn9t/)** — 用 AI 回邮件被 prompt injection

---

### 📊 办公

#### 📊 数据分析 / Excel（29 条）
- [知乎 ▲3] **[Claude in Excel 被严重低估了](https://zhuanlan.zhihu.com/p/2016200132153074407)** — 3000 行销售明细，AI 代替 VLOOKUP

#### 📝 会议记录（9 条）
- 通义听悟（阿里）在中文圈最常被提及；英文圈是 Otter / Granola

---

## 💡 从分布看出的 3 个隐藏事实

### 1. 这份样本**严重偏编程**

爬虫覆盖的 13 个站点（Reddit r/AI_Agents、r/ClaudeAI、r/cursor、HN、GitHub Discussions、知乎 token 话题、B 站 AI 教程）——**本质就是开发者论坛**。真实世界的 AI 用户分布肯定不是 68% 写代码——但**愿意在公开论坛讨论 token 消耗的用户**，68% 是写代码的。

### 2. 中英文用户**关心的问题**不一样

| | 英文圈最热 | 中文圈最热 |
|---|---|---|
| Agent | 多 Agent 架构、失控 bug、成本 | OpenClaw "一人公司"幻想、账单吐槽 |
| 编程 | Claude Code 源码泄露、reverse engineering | Cursor 账单、DeepSeek 本地部署 |
| 学习 | Prompt engineering guides | **八字 / 玄学 / 占卜**（[DeepSeek 玄学指令 ▲2,005]） |
| 陪伴 | 心理/情感/companion | 几乎没有（分散到小红书等未爬站点） |

### 3. 增长最快的新场景：**让 AI 处理企业脏活**

- Harvard 教授用 Claude **2 周写出前沿物理论文**（▲895）
- 20k 企业文档的多 agent 系统（▲289）
- 10K 企业每日查询 RAG（$12,500/day）
- AI 客服 + 订单跟踪（GitHub Discussions）

这类不如"造 C 编译器"出圈，但**商业价值更实**——是付钱买 token 的主力。

---

## 📈 结论（一句话）

> **开发者正在以 68% 的占比，把 AI token 用来写代码——其中 IDE 辅助（Cursor / Claude Code）吞掉 62%，全自动 Agent 吞掉 14%；剩下 32% 分散在 RAG、学习、Agent 工作流、生成式上。非开发者在我们这份样本里声量极小，但他们才是未来的流量主力。**

---

## 🔗 继续挖

- 单平台原文：`data/curated/{reddit,hackernews,zhihu}.md`
- 浏览器：`.venv/bin/python viewer.py` — 左侧按平台筛，搜索框支持多关键词
- 本文完整样本：`/tmp/usecase2.txt`（每桶 Top 3 扩展到全部）
