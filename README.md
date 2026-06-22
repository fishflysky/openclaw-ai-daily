# 🧠 OpenClaw AI Daily · 你的个人 AI 前沿学习系统

<p align="center">
  <img src="https://img.shields.io/badge/status-active-success?style=for-the-badge" alt="Status">
  <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/badge/Powered_by-OpenClaw-purple?style=for-the-badge" alt="OpenClaw">
  <img src="https://img.shields.io/badge/Knowledge-Obsidian-7C3AED?style=for-the-badge" alt="Obsidian">
</p>

<p align="center">
  <b>每天 8 分钟 · 10 道题 · 1 张知识图�?/b><br/>
  �?AI Agent 自动化你�?AI 前沿知识学习，把"刷手�?变成"长知�?
</p>

---

## �?为什么做这个�?
> "我不�?AI 从业者，�?AI 正在影响我的工作。我想跟上前沿，但没有时间每天读几十篇论文�?

这是 Scale 的困惑，也是很多人的困惑�?
**OpenClaw AI Daily** �?**AI Agent 完全自动�?*解决这个问题�?
```
              ┌─────────────────────────────────�?              �? 每晚 20:00 自动触发              �?              �?      �?                         �?              �? SerpAPI 搜索全球 AI 新闻        �?              �?      �?                         �?              �? web_fetch 抓取原文深度阅读      �?              �?      �?                         �?              �? LLM 生成 10 道选择�?           �?              �?      �?                         �?              �? 推送到 Telegram / WebChat       �?              �?      �?                         �?              �? �?你在 Telegram 里答�?        �?              �?      �?                         �?              �? 🔍 自动批改 + 盲区分析          �?              �?      �?                         �?              �? 🧠 写入 Obsidian 知识图谱       �?              └─────────────────────────────────�?```

**全自动。零操作�?* 你只需要在 Telegram 里回�?`1�?2�?3�?..`，剩下的全部交给 Agent�?
---

## 🎯 核心亮点

| 特�?| 说明 |
|------|------|
| 🤖 **全自�?Agent 流水�?* | 搜索→阅读→出题→推送→批改→图谱，0 人工干预 |
| 📊 **10 大知识领域覆�?* | 产业趋势 / 技术方�?/ 重大发布 / 政策治理 / 企业战略 / 学术前沿 / Agent 智能�?/ AI+科学 / 安全对齐 / 开源生�?|
| 🧠 **Obsidian 知识图谱** | 每道题自动生成概念页，每日笔记成为知识网络的入口节点 |
| 🔍 **个性化盲区分析** | 答错的题自动映射到知识盲区，推荐学习资源 |
| 📱 **Telegram 原生交互** | 下班路上、睡前刷一下，像聊天一样答�?|
| 🗂�?**Cron 定时调度** | 隔离会话独立执行，主会话处理答题交互 |

---

## 🏗�?架构

```
┌──────────────────────────────────────────────────────�?�?                   OpenClaw Gateway                   �?�? ┌──────────────�? ┌──────────────�? ┌────────────�?�?�? �? Cron Job     �? �? Main Session �? �? Subagent  �?�?�? �? 每日 20:00   �? �? 答题+批改    �? �? 新闻采集  �?�?�? └──────┬───────�? └──────┬───────�? └─────┬──────�?�?�?        �?                �?               �?        �?└─────────┼─────────────────┼────────────────┼─────────�?          �?                �?               �?          �?                �?               �?   ┌──────────�?   ┌──────────────�?  ┌───────────�?   �?Telegram �?   �?Obsidian 仓库�?  �? SerpAPI  �?   �? 推�?答题�?   �? 知识图谱     �?  �? 新闻搜索 �?   └──────────�?   └──────────────�?  └───────────�?```

---

## 📂 项目结构

```
openclaw-ai-daily/
├── README.md                  # 你在看的这个
├── LICENSE
├── config/
�?  ├── cron-job.json          # Cron 任务配置（模板）
�?  └── agent-prompt.md        # Agent 系统提示�?├── obsidian/
�?  ├── README.md              # 知识体系说明
�?  ├── 知识图谱.md             # 图谱索引
�?  ├── 答案�?md              # 标准答案与解�?�?  ├── YYYY-MM-DD.md          # 每日日报（模板）
�?  └── 概念/                  # 自动生成的概念页
�?      ├── Physical AI.md
�?      ├── Agentic Era.md
�?      ├── 中国AI治理.md
�?      └── ...
├── reports/
�?  └── YYYY-MM-DD-分析报告.md  # 答题分析报告
└── docs/
    ├── deploy.md              # 部署指南
    └── architecture.md        # 架构详解
```

---

## 🚀 快速开�?
### 前置条件

- [OpenClaw](https://openclaw.ai) �?AI Agent 运行�?- [Obsidian](https://obsidian.md) �?知识图谱工具
- Telegram Bot Token �?用于推�?- SerpAPI Key �?用于搜索全球 AI 新闻（免费额�?100 �?月）

### 三步部署

```bash
# 1. 克隆项目
git clone https://github.com/your-username/openclaw-ai-daily.git
cd openclaw-ai-daily

# 2. 复制配置文件
cp config/cron-job.example.json config/cron-job.json
# 编辑 cron-job.json，填入你�?Telegram Bot Token、SerpAPI Key �?
# 3. 注册 Cron 任务
openclaw cron add --job "$(cat config/cron-job.json)"

# 完成！明�?20:00 你的第一�?AI 日报就来�?🎉
```

---

## 🧪 效果展示

### 📮 日报预览（Telegram�?
```
📮 AI 前沿日报 · 2026-06-22

🔬 本期覆盖：Anthropic 八篇重磅研究、递归自我改进�?Claude Code 数据分析、AI+网络安全新范�?
【第1�?· 产业趋势】Anthropic �?Claude Code ~40 万次
会话分析表明，决定编码任务成功率的最关键因素是：

1. 用户的编程语言熟练�?2. 用户的领域专业知�?3. 模型的参数规�?4. 会话的长度和交互轮数

【第2�?· Agent/智能体】Project Fetch Phase Two 中，
Claude Opus 4.7 操控机器狗的速度比最快人类团队快�?..

📝 回复 1x 2x ... 10x
```

### 🧠 Obsidian 知识图谱

答题后自动生成：
- **每日笔记** �?知识网络的入口节�?- **概念�?* �?`[[Physical AI]]`、`[[Agentic Era]]` 等双向链�?- **分析报告** �?错题解析 + 盲区映射 + 学习建议
- **知识图谱视图** �?�?Obsidian Graph View 中直观看到知识网络生�?
---

## 📊 知识领域矩阵

| # | 领域 | 关注重点 | 学习价�?|
|---|------|---------|---------|
| 🏭 | 产业趋势 | 元年判断、市场格局 | 宏观感知�?|
| 🔬 | 技术方�?| 架构、训练范式、推理优�?| 技术判断力 |
| 📢 | 重大发布 | 模型/产品发布、开源动�?| 信息第一�?|
| 🏛�?| 政策治理 | AI 监管、立法进�?| 合规意识 |
| 🏢 | 企业战略 | 巨头布局、商业动�?| 商业敏感�?|
| 📚 | 学术前沿 | 顶会论文、基准评�?| 学术视野 |
| 🤖 | 智能�?| Agent/工具使用/自主系统 | 前沿技�?|
| 🧬 | AI+科学 | 生物/化学/物理突破 | 交叉洞察 |
| 🔐 | 安全对齐 | AI 安全、越狱、红�?| 安全意识 |
| 🌐 | 开源生�?| 开源模型、工具链 | 动手能力 |

---

## 🛠�?技术栈

- **Agent 运行�?*: [OpenClaw](https://openclaw.ai)
- **新闻搜索**: SerpAPI Google Engine
- **内容抓取**: web_fetch（内置）
- **LLM**: DeepSeek V4 Pro / MiMo V2.5（自�?fallback�?- **推送通道**: Telegram Bot API
- **知识管理**: Obsidian + 双向链接 + Dataview
- **调度**: OpenClaw Cron（隔离会话执行）

---

## 🤔 常见问题

<details>
<summary><b>不会编程能用吗？</b></summary>

可以。部署只需要复制粘贴几条命令，日常使用只需要在 Telegram 里聊天式答题�?</details>

<details>
<summary><b>需要科学上网吗�?/b></summary>

搜索全球新闻需�?Clash/代理。Agent 本身不需要，�?SerpAPI 和部分新闻源需要�?</details>

<details>
<summary><b>能改成早上推送吗�?/b></summary>

�?Cron 表达式就行：`0 8 * * *` 就是每天早上 8 点�?</details>

<details>
<summary><b>能换成微�?钉钉推送吗�?/b></summary>

OpenClaw 支持多通道。改成其他平台需要额外配置，欢迎 PR�?</details>

<details>
<summary><b>题目质量怎么样？</b></summary>

目标难度正确�?~60%，设计在教育心理学的"学习�?（Zone of Proximal Development）。太简单无聊，太难劝退�?</details>

---

## 🎯 Roadmap

- [x] 每日自动搜索 + 出题 + 推�?- [x] Telegram 答题 + 自动批改
- [x] Obsidian 知识图谱自动生成
- [ ] 周报 / 月报汇�?- [ ] 多人答题 + 排名
- [ ] 自定义选题领域
- [ ] 音频版日报（TTS�?- [ ] 一键部署脚�?/ Docker

---

## 🙏 致谢

- [OpenClaw](https://openclaw.ai) �?�?Agent 编排如此丝滑
- [Obsidian](https://obsidian.md) �?最好的知识管理工具
- [SerpAPI](https://serpapi.com) �?稳定的搜索引�?API
- [Anthropic](https://anthropic.com) �?每日日报的重要新闻源

---

## 📄 License

MIT © 2026 Scale & OpenClaw AI Daily Contributors

---

<p align="center">
  <sub>Built with ❤️ by <a href="https://github.com/fishflysky">Scale</a> · Powered by <a href="https://openclaw.ai">OpenClaw</a></sub>
</p>
