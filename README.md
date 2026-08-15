# 大学之道

`daxue-zhidao` 是一个动态学习 Skill：先诊断，再由你选择方向；每次只学习一个有明确成功标准的小单元，
验证后记录进度并停止。它适合“教我……”“从零学习……”“继续课程”等请求，不适合一次性问答或完整教程。

## 支持的 Agent

| Agent | 显式调用 | 结构化提问 |
| --- | --- | --- |
| OpenCode | 根据描述自动触发或手动加载 | `question` |
| Claude Code | `/daxue-zhidao` | `AskUserQuestion` |
| Codex | `$daxue-zhidao` | 可用时使用 `request_user_input` |
| Pi | `/skill:daxue-zhidao` | 默认文本；可选 `question` 扩展 |

## 前置条件

- 安装任一受支持的 Agent。
- 使用 Git 安装或更新本 Skill；也可以手动复制目录。
- Context7：推荐用于库、框架、SDK、API、CLI 和云服务的版本敏感课程。OpenCode 会优先使用它；未配置时
  仍可学习基础知识，但当前技术结论可能改用官方网页或明确标注无法核实。
- 网络、Shell、LSP、MCP、subagent、图像和浏览器能力均为按课程需要使用的可选能力，不是基础运行条件。

## 安装

### Linux / macOS

Codex、Pi 和 OpenCode 都能发现 `~/.agents/skills`：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

Claude Code 使用自己的 Skill 目录，可以复用同一份安装：

```bash
mkdir -p ~/.claude/skills
ln -s ~/.agents/skills/daxue-zhidao ~/.claude/skills/daxue-zhidao
```

只使用 Claude Code 时，也可以直接克隆到 `~/.claude/skills/daxue-zhidao`。

### Windows

在 PowerShell 中安装到 Codex、Pi 和 OpenCode 共用目录：

```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.agents\skills" | Out-Null
git clone https://github.com/sai-7i/daxue-zhidao.git "$HOME\.agents\skills\daxue-zhidao"
```

Claude Code 可以通过目录联接复用同一份安装，通常不需要管理员权限：

```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.claude\skills" | Out-Null
New-Item -ItemType Junction `
  -Path "$HOME\.claude\skills\daxue-zhidao" `
  -Target "$HOME\.agents\skills\daxue-zhidao"
```

若无法创建目录联接，或只使用 Claude Code，可独立安装：

```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.claude\skills" | Out-Null
git clone https://github.com/sai-7i/daxue-zhidao.git "$HOME\.claude\skills\daxue-zhidao"
```

执行前请确认目标 `daxue-zhidao` 目录不存在，避免覆盖已有安装或本地修改。

## 更新

```bash
git -C ~/.agents/skills/daxue-zhidao pull --ff-only
```

若只安装在 Claude Code 目录：

```bash
git -C ~/.claude/skills/daxue-zhidao pull --ff-only
```

Windows PowerShell：

```powershell
git -C "$HOME\.agents\skills\daxue-zhidao" pull --ff-only
```

若 Windows 只安装在 Claude Code 目录：

```powershell
git -C "$HOME\.claude\skills\daxue-zhidao" pull --ff-only
```

Pi 更新后执行 `/reload`；其他 Agent 未自动发现变化时重启。若目标目录已存在，请先确认它是否包含自己的
修改，不要直接覆盖。

## 使用

```text
教我从零学习 Rust。
按步骤带我理解 Git rebase。
继续我的数据库课程。
```

跨会话课程可保存为 `COURSE_PLAN.md`；也可选择临时模式，不写课程状态。环境探测会先说明范围并征得同意，
不会读取或保存密码、令牌等秘密。
