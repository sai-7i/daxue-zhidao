# 大学之道

仅用户手动调用,模型不主动触发。它研究课程与课次技术地图,提供路线、课次介绍和学习规划,不教授详细内容。

## 选择分支

本仓库提供两个功能分支,默认克隆得到 `guide`:

| 分支    | 说明                                        | 默认分支 |
|:----- |:---------------------------------------- |:----: |
| `guide` | 渐进式引导版:先建技术地图,再按真实目标逐单元讲解、评估并推进课程      | ✓      |
| `map` | 技术地图版:研究课程/课次地图,规划路线、课次介绍与学习规划,不教授内容 |       |

两者共用相同宿主适配与安装位置,仅 `SKILL.md` 流程和地图格式不同;直接克隆默认得到 `guide` 分支。

## 开始

```text
/daxue-zhidao 我会 JavaScript,想学习 React 的渲染和状态更新,目标是维护一个中型项目。
```

```text
/daxue-zhidao 从零学习 Rust,目标是做一个能读取 CSV 文件的命令行工具。
```

## 安装

安装 `guide` 分支(默认):

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

安装 `map` 分支:

```bash
mkdir -p ~/.agents/skills
git clone -b map https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

Claude Code:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao        # guide 分支(默认)
git clone -b map https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao  # map 分支
```

不指定 `-b` 时默认克隆 `guide` 分支。

## 更新

```bash
git -C ~/.agents/skills/daxue-zhidao pull --ff-only   # 保持当前分支(map/guide)
git -C ~/.claude/skills/daxue-zhidao pull --ff-only
```

切换分支(会覆盖本地改动,确认后执行):

```bash
git -C ~/.agents/skills/daxue-zhidao fetch origin
git -C ~/.agents/skills/daxue-zhidao checkout guide   # 切到 guide
git -C ~/.agents/skills/daxue-zhidao checkout map     # 切到 map
```

Pi 更新后另执行 `/reload`。

## 命令

| Agent                                    | 唤起方式                  | 安装位置               | 适配说明                 |
| ---------------------------------------- | --------------------- | ------------------ | -------------------- |
| [OpenCode](references/opencode.md)       | `/daxue-zhidao`       | `~/.agents/skills` | `question`           |
| [Claude Code](references/claude-code.md) | `/daxue-zhidao`       | `~/.claude/skills` | `AskUserQuestion`    |
| [Codex](references/codex.md)             | `$daxue-zhidao`       | `~/.agents/skills` | `request_user_input` |
| [Pi](references/pi.md)                   | `/skill:daxue-zhidao` | `~/.agents/skills` | `question` 扩展        |
| [ZCode](references/zcode.md)             | `/daxue-zhidao`       | `~/.agents/skills` | `AskUserQuestion`    |
| [dsh](references/dsh.md)                 | `/daxue-zhidao`       | `~/.agents/skills` | `ask_user_question`  |

`课程记录:COURSE_PLAN.md` &nbsp;·&nbsp; `课程地图:TECHNOLOGY_MAP.md` &nbsp;·&nbsp; `课次地图:LESSON_MAP.md`(仅 `map` 分支)
