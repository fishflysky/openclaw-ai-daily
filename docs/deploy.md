# 部署指南 · OpenClaw AI Daily

## 总览

本指南将带你从零开始搭建 AI 前沿日报系统。预计耗时：**15-30 分钟**。

---

## 第 1 步：准备基础设施

### 1.1 安装 OpenClaw

```bash
npm install -g openclaw
openclaw gateway init
```

参考：[OpenClaw 安装文档](https://docs.openclaw.ai)

### 1.2 准备账号

| 服务 | 用途 | 获取方式 |
|------|------|---------|
| Telegram Bot Token | 推送日报 | [@BotFather](https://t.me/BotFather) 创建 |
| SerpAPI Key | 搜索新闻 | [serpapi.com](https://serpapi.com) 注册（免费 100 次/月） |
| Obsidian | 知识管理 | [obsidian.md](https://obsidian.md) 下载 |

### 1.3 获取你的 Telegram Chat ID

1. 给 `@userinfobot` 发消息
2. 或者给自己创建的 Bot 发一条消息，然后用 `getUpdates` API 获取

---

## 第 2 步：配置 Cron 任务

1. 打开 `config/cron-job.example.json`
2. 将 `__YOUR_TELEGRAM_CHAT_ID__` 替换为你的 Chat ID
3. 将 SerpAPI Key 写入 prompt 中的对应位置
4. 调整推送时间（可选）：
   - 改 `schedule.expr` 中的时间：`0 20` → `0 8`（早上 8 点）
   - 改 `schedule.tz` 时区

5. 导入到 OpenClaw：

```bash
openclaw cron add --job "$(cat config/cron-job.json)"
```

---

## 第 3 步：设置 Obsidian Vault

1. 打开 Obsidian
2. 新建一个 Vault，指向你希望存放 AI 日报的目录
3. 安装推荐插件：**Dataview**
4. 将 `obsidian/` 目录下的文件复制到你的 Vault 根目录
5. Agent 会自动在 Vault 中创建每日日报和分析报告

---

## 第 4 步：首次测试

### 手动触发一次 Cron 任务

```bash
openclaw cron run --id <job-id> --run-mode force
```

### 检查

- Telegram 收到日报推送
- Obsidian Vault 中出现今日日报文件

---

## 第 5 步：开始答题

在 Telegram 中回复日报，格式如：

```
1③ 2① 3② 4④ 5③ 6① 7② 8④ 9③ 10①
```

Agent 会自动：
1. 批改并评分
2. 分析知识盲区
3. 写入 Obsidian 分析报告

---

## 常见问题排查

| 问题 | 可能原因 | 解决 |
|------|---------|------|
| 推送未收到 | Bot Token 或 Chat ID 错误 | 检查配置 |
| 搜索无结果 | SerpAPI 配额用尽 | 检查 serpapi.com 控制台 |
| 题目质量差 | LLM fallback 到较弱模型 | 检查 `fallbacks` 顺序 |
| Obsidian 未写入 | 路径权限问题 | 检查 Agent 的 write 路径 |

---

## 进阶：多通道推送

如果你想同时推送到 Telegram + WebChat：

```json
"delivery": {
  "mode": "announce",
  "channel": "telegram",
  "to": "8944096717"
}
```

改为 Telegram 推送后，还可以在 WebChat 中直接查看和答题。

---

## 进阶：自定义领域

在 Cron Job 的 prompt 中调整这行：

```
领域覆盖：产业趋势、技术方向、重大发布、企业战略、政策治理、
学术前沿、Agent/智能体、AI+科学、安全对齐、开源生态
```

改为你关心的领域即可。
