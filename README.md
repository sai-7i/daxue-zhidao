<div align="center">

# 大学之道

**面向真实目标的渐进式学习 Skill**

从目标、基础与约束出发，逐个学习、练习并验证单元。

`目标诊断` · `自主选路` · `练习验证` · `持续记录`

</div>

## ✨ Agent 支持

| Agent | 推荐 | 结构化提问 | 适配状态 | 显式调用 |
| --- | :---: | --- | :---: | --- |
| **OpenCode** | ✅ **推荐** | `question` | ✅ 已测试 | 直接描述目标 |
| Claude Code | ✅ | `AskUserQuestion` | ✅ 已适配 | `/daxue-zhidao` |
| Codex | ❌ | `request_user_input`、MCP 表单、文本降级 | ✅ 已适配 | `$daxue-zhidao` |
| Pi | ⚠️ 有条件 | `question` 扩展 | ✅ 已适配 | `/skill:daxue-zhidao` |
| ZCode | ✅ | `AskUserQuestion` | ✅ 已适配 | `/daxue-zhidao` |
| dsh（DeepSeek Harness） | ✅ | `ask_user_question` | ✅ 已适配 | `/daxue-zhidao` |

> [!TIP]
> 推荐使用 **OpenCode**：已完成实际测试，支持结构化提问、文件操作和完整课程流程。

> [!WARNING]
> 不推荐使用 **Codex**：原生结构化提问依赖客户端与运行模式，可能降级为 MCP 表单或文本询问。

### 💬 提问方式

- 结构化提问用于目标确认、能力诊断、路线选择、授权确认和单元检查。
- Codex 的降级顺序：`request_user_input` → MCP `mcpServer/elicitation/request` 表单 → 普通文本询问。
- 命令审批仅用于权限确认，不能代替课程选择。

## 🧭 学习流程

| 步骤 | 你需要做什么 | Skill 会做什么 |
| --- | --- | --- |
| `01` 🎯 | 说明目标、应用场景和已掌握技巧 | 诊断基础与熟练程度 |
| `02` 🗺️ | 从候选方向和起始单元中自主选择 | 根据你的信息规划路线 |
| `03` ✅ | 完成一个练习 | 验证结果并更新 `COURSE_PLAN.md` |

## 📦 安装

需要 Git。Windows 用户请在 Git Bash 中执行。

<details open>
<summary><strong>OpenCode、Codex、Pi、ZCode、dsh</strong></summary>

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

</details>

<details>
<summary><strong>Claude Code</strong></summary>

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao
```

</details>

> [!NOTE]
> 目标目录已存在时不要重复克隆。

## 🔄 更新

```bash
git -C ~/.agents/skills/daxue-zhidao pull --ff-only
git -C ~/.claude/skills/daxue-zhidao pull --ff-only
```

Pi 更新后执行 `/reload`；其他 Agent 更新后重启会话。

## 🚀 使用

直接描述目标：

```text
教我从零做一个 Rust CLI 工具。
按步骤带我理解 Git rebase，并让我能在项目中安全使用。
继续我的数据库课程，先检查我已经掌握的技巧。
```

<details>
<summary><strong>显式调用命令</strong></summary>

| Agent | 命令 |
| --- | --- |
| OpenCode | 直接描述学习目标 |
| Claude Code | `/daxue-zhidao` |
| Codex | `$daxue-zhidao` |
| Pi | `/skill:daxue-zhidao` |
| ZCode | `/daxue-zhidao` |
| dsh | `/daxue-zhidao` |

</details>

## 📝 课程记录

课程进度保存在 `COURSE_PLAN.md`：

- 🎯 学习目标、场景、基础、约束和偏好
- 🛠️ 已掌握技巧及熟练程度
- ✅ 当前单元、观察证据和能力边界
- 🗺️ 下一步候选和用户选择

> [!IMPORTANT]
> 后续选择与之前冲突时，以最后一次明确选择为准，并删除被取代的内容。

## 🗂️ 项目结构

```text
SKILL.md                         核心流程
references/course-plan-format.md COURSE_PLAN.md 格式
references/<agent>.md            Agent 适配规则
```
