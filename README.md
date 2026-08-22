<div align="center"><a name="readme-top"></a>

# 大学之道

**用于自定义系统课程的 Skill**

适用：自定义的系统课程。<br>
不适用：临时问一个问题。

🧭 [开始使用](#start) · 📦 [安装](#install) · 🧩 [支持Agent](#hosts)

</div>

<a id="start"></a>

## 🚀 开始使用

装好之后，直接说明学习内容、学习目标和现有基础：

```text
我想从零学 Rust，目标是做一个能读取 CSV 文件的命令行工具。

我会写 JavaScript，想系统学习 React 渲染和状态更新，目标是能维护一个中型项目。
```

<a id="install"></a>

## 📦 安装

需要 Git。大多数Agent用 `~/.agents/skills`，Claude Code 用 `~/.claude/skills`。

### OpenCode、Codex、Pi、ZCode、dsh

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

### Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao
```

## 🔄 更新

```bash
# ~/.agents/skills 下的Agent
git -C ~/.agents/skills/daxue-zhidao pull --ff-only

# Claude Code
git -C ~/.claude/skills/daxue-zhidao pull --ff-only
```

更新完重新启动会话

Pi 可以执行 `/reload` 重新加载 Skill。

<a id="hosts"></a>

## 🧩 支持Agent

| Agent                                    | 使用命令                  | 适配工具                   |
| ---------------------------------------- | --------------------- | ---------------------- |
| [OpenCode](references/opencode.md)       | `/daxue-zhidao`       | `question`             |
| [Claude Code](references/claude-code.md) | `/daxue-zhidao`       | `AskUserQuestion`      |
| [Codex](references/codex.md)             | `$daxue-zhidao`       | `request_user_input` 等 |
| [Pi](references/pi.md)                   | `/skill:daxue-zhidao` | `question` 扩展          |
| [ZCode](references/zcode.md)             | `/daxue-zhidao`       | `AskUserQuestion`      |
| [dsh](references/dsh.md)                 | `/daxue-zhidao`       | `ask_user_question`    |

<div align="right">

[⬆️ 返回顶部](#readme-top)

</div>
