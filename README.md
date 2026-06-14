# OpenClaw 工作区配置备份

此仓库包含 OpenClaw AI 助手的工作区配置和个性化设置。

## 📁 目录结构

```
.
├── AGENTS.md              # 工作区行为规范和配置
├── SOUL.md                # AI 助手人格定义
├── IDENTITY.md            # 助手身份信息
├── USER.md                # 用户信息和偏好
├── MEMORY.md              # 长期记忆（重要决策和偏好）
├── TOOLS.md               # 本地工具配置笔记
├── HEARTBEAT.md           # 心跳检查任务配置
├── ONBOARDING.md          # 新用户引导流程
│
├── memory/                # 每日记忆日志
│   └── YYYY-MM-DD.md     # 按日期记录的事件
│
├── skills/                # 已安装的技能
│   ├── openclaw-find-skills/
│   ├── proactive-agent/
│   └── self-improvement/
│
├── .clawhub/              # ClawHub 技能管理
├── .learnings/            # 学习和错误记录
│   ├── ERRORS.md
│   ├── FEATURE_REQUESTS.md
│   └── LEARNINGS.md
│
└── .openclaw/             # 运行时状态（不提交）
```

## 🔧 配置说明

### 核心文件
- **AGENTS.md**: 工作区规则、内存管理、安全边界
- **SOUL.md**: AI 性格、沟通风格、行为准则
- **MEMORY.md**: 持久化的用户偏好和重要决策

### 技能系统
- 技能通过 ClawHub 安装和管理
- 优先使用 `clawhub` 命令下载技能
- 搜索优先使用 Tavily

### 内存机制
- **每日日志**: `memory/YYYY-MM-DD.md` 记录当天事件
- **长期记忆**: `MEMORY.md` 存储重要偏好和决策
- **学习记录**: `.learnings/` 追踪错误和改进

## 🔒 安全说明

以下文件已被 `.gitignore` 排除：
- 包含 API 密钥的配置文件
- 运行时状态文件
- 环境变量文件

## 📝 更新日志

- **2026-06-09**: 初始备份，配置 ClawHub 和 Tavily 偏好
- **2026-06-14**: 整理目录结构，完善文档

## 🚀 使用方法

1. 克隆到 OpenClaw 工作区：
   ```bash
   cd ~/.openclaw/workspace
   git clone <repo-url> .
   ```

2. 配置环境变量（如需要）：
   - `CLAWHUB_TOKEN`: ClawHub API 令牌
   - Tavily API 密钥在 `openclaw.json` 中配置

3. 启动 OpenClaw，助手会自动加载配置

## 📌 注意事项

- 敏感信息（API 密钥、令牌）不应提交到仓库
- `SESSION-STATE.md` 是运行时状态，不纳入版本控制
- 定期将 `memory/` 日志中的重要信息整理到 `MEMORY.md`
