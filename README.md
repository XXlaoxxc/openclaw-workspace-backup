# OpenClaw 工作区配置备份

> 备份时间：2026-06-14 09:50 (GMT+8)

## 📁 仓库结构

```
.
├── README.md                 # 本文件
├── .gitignore
│
├── agents/                   # 智能体工作区配置
│   ├── main/                 # 主助手 - 小焱 (Xiǎo Yàn)
│   │   ├── IDENTITY.md       # 身份定义
│   │   ├── SOUL.md           # 人格定义
│   │   ├── AGENTS.md         # 工作区行为规范
│   │   ├── MEMORY.md         # 长期记忆
│   │   ├── TOOLS.md          # 工具配置笔记
│   │   ├── USER.md           # 用户信息
│   │   ├── HEARTBEAT.md      # 心跳任务
│   │   └── memory/           # 每日记忆日志
│   │
│   ├── learner/              # 学习助手 - 焱老
│   │   ├── IDENTITY.md       # 身份：互联网技术学习导师
│   │   ├── SOUL.md           # 人格：六阶认知教学法
│   │   ├── AGENTS.md         # 工作流：导师授课 + 答疑解惑
│   │   ├── MEMORY.md         # 学员画像 + 学习进度
│   │   ├── TOOLS.md
│   │   ├── USER.md
│   │   ├── HEARTBEAT.md
│   │   └── memory/
│   │
│   └── comic/                # AI漫剧助手 - 焱宝
│       ├── IDENTITY.md       # 身份：漫剧创作助理
│       ├── SOUL.md           # 人格：画面叙事 + 短剧节奏
│       ├── AGENTS.md         # 工作流：小说→剧本→分镜
│       ├── MEMORY.md         # 创作档案 + 工作规范
│       ├── TOOLS.md
│       ├── USER.md
│       ├── HEARTBEAT.md
│       └── memory/
│
├── config/                   # 系统配置
│   └── openclaw.json         # 主配置文件（需手动填入 TOKEN）
│
└── skills/                   # 已安装技能
    ├── openclaw-find-skills/
    ├── proactive-agent/
    └── self-improvement/
```

## 🤖 智能体说明

### 1. 主助手 - 小焱 (Xiǎo Yàn)
- **目录**: `agents/main/`
- **职责**: 通用个人助手，日常任务处理
- **模型**: qwen/qwen3.7-plus
- **工作区**: `~/.openclaw/workspace`

### 2. 学习助手 - 焱老
- **目录**: `agents/learner/`
- **职责**: 互联网技术教学导师，六阶认知教学法
- **模型**: qwen/qwen3.7-plus
- **工作区**: `~/.openclaw/workspace-learner`
- **特色**: 
  - 20年互联网行业实战经验
  - 循序渐进的教学风格
  - 学员画像追踪

### 3. AI漫剧助手 - 焱宝
- **目录**: `agents/comic/`
- **职责**: 小说转剧本、剧本转分镜的全链路创作
- **模型**: qwen/qwen3.7-plus
- **工作区**: `~/.openclaw/workspace-comic`
- **特色**:
  - 短剧节奏把控（每15秒一个冲突点）
  - 分镜脚本生成
  - AI绘图 prompt 辅助

## 🔧 恢复步骤

1. **安装 OpenClaw**
   ```bash
   npm install -g openclaw
   ```

2. **恢复配置文件**
   ```bash
   cp config/openclaw.json ~/.openclaw/
   # 手动填入 GITHUB_TOKEN、CLAWHUB_TOKEN 等密钥
   ```

3. **恢复智能体工作区**
   ```bash
   # 主助手
   cp -r agents/main/* ~/.openclaw/workspace/
   
   # 学习助手
   cp -r agents/learner/* ~/.openclaw/workspace-learner/
   
   # 漫剧助手
   cp -r agents/comic/* ~/.openclaw/workspace-comic/
   ```

4. **重启 Gateway**
   ```bash
   openclaw gateway restart
   ```

## 🔒 安全说明

- ⚠️ `config/openclaw.json` 中的敏感信息已脱敏
- ⚠️ 恢复后需手动填入 API 密钥和 Token
- ⚠️ 会话历史未备份，恢复后为全新状态

## 📝 更新日志

- **2026-06-14**: 重构仓库结构，按智能体分目录存放
- **2026-06-09**: 初始备份
