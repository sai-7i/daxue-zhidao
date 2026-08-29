# 大学之道

仅用户手动调用。它研究课程与课次技术地图，提供路线、课次介绍和学习规划，不教授详细内容。

## 开始

```text
/daxue-zhidao 我会 JavaScript，想学习 React 的渲染和状态更新，目标是维护一个中型项目。
```

```text
/daxue-zhidao 从零学习 Rust，目标是做一个能读取 CSV 文件的命令行工具。
```

## 安装

OpenCode、Codex、Pi、ZCode、dsh：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

Claude Code：

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao
```

更新：`git -C <安装目录> pull --ff-only`。Pi 另执行 `/reload`。

## 命令

| Agent                                    | 唤起方式                  | 安装位置               | 适配说明                 |
| ---------------------------------------- | --------------------- | ------------------ | -------------------- |
| [OpenCode](references/opencode.md)       | `/daxue-zhidao`       | `~/.agents/skills` | `question`           |
| [Claude Code](references/claude-code.md) | `/daxue-zhidao`       | `~/.claude/skills` | `AskUserQuestion`    |
| [Codex](references/codex.md)             | `$daxue-zhidao`       | `~/.agents/skills` | `request_user_input` |
| [Pi](references/pi.md)                   | `/skill:daxue-zhidao` | `~/.agents/skills` | `question` 扩展        |
| [ZCode](references/zcode.md)             | `/daxue-zhidao`       | `~/.agents/skills` | `AskUserQuestion`    |
| [dsh](references/dsh.md)                 | `/daxue-zhidao`       | `~/.agents/skills` | `ask_user_question`  |

`课程记录：COURSE_PLAN.md` &nbsp;·&nbsp; `课程地图：TECHNOLOGY_MAP.md` &nbsp;·&nbsp; `课次地图：LESSON_MAP.md`
