# 大学之道

`daxue-zhidao` 是一个动态学习 Skill。它会先了解你在当前方向的目标、基础和约束，再逐个教授可验证的小单元。
已完成的单元不会重复教学，当前方向结束后会及时提供新方向。

支持 OpenCode、Claude Code、Codex、Pi、ZCode 和 dsh（DeepSeek Harness）。

## 安装

需要先安装 Git。Windows 用户请在 **Git Bash** 中执行命令。

Codex、Pi、OpenCode、ZCode、dsh：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

Claude Code：

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao
```

目标目录已存在时不要重复克隆。

## 更新

根据安装位置执行一条命令：

```bash
git -C ~/.agents/skills/daxue-zhidao pull --ff-only
git -C ~/.claude/skills/daxue-zhidao pull --ff-only
```

Pi 更新后执行 `/reload`；其他 Agent 未加载新版本时重启。

## 使用

```text
教我从零学习 Rust。
按步骤带我理解 Git rebase。
继续我的数据库课程。
```

显式调用：

| Agent | 命令 |
| --- | --- |
| Claude Code | `/daxue-zhidao` |
| Codex | `$daxue-zhidao` |
| Pi | `/skill:daxue-zhidao` |
| ZCode | `/daxue-zhidao` |
| dsh | `/daxue-zhidao` |

课程进度保存在 `COURSE_PLAN.md`，文件会持续精简，只保留后续学习需要的信息。
