<div align="center">

# 大学之道

**面向真实任务的动态学习 Skill**

先补前置，再讲清原理；课程会根据你的起点，在主线、深化、扩展和应用之间调整。

[开始使用](#start) · [选择学习方式](#choose) · [安装](#install) · [课程记录](#record)

</div>

## 这是什么

大学之道把“教我……”变成一门可以持续调整的课程：

- 从真实目标、使用场景和已有基础开始。
- 只询问会影响起点、路线、教学方式或授权的信息。
- 每一课先讲核心概念、关系、机制、前提、边界与取舍，再补充相关扩展。
- 允许随时提问，不要求每课完成问答或练习才能继续。
- 把下一轮教学需要的状态保存在 `COURSE_PLAN.md`，而不是保存整段课堂对话。

它适合从零学习、已有基础的系统化学习，也适合从上次的课程检查点继续。

<a id="start"></a>
## 开始使用

安装后，直接说出你想学什么、为什么学，以及已有的相关经验。下面的例子可以直接改写：

```text
我想从零学 Rust，目标是做一个能读取 CSV 文件的命令行工具。

我已经会 Python，想理解 Git rebase 的原理、风险和团队协作中的使用边界。

继续我的数据库课程，从上次的检查点开始；如果前置知识不够，先补齐再讲。
```

接下来会发生三件事：

1. 确认真正影响课程的起点和约束。
2. 提供主线、原理深化、相关扩展或应用迁移等不同方向，由你选择。
3. 讲完当前单元并处理你的问题后，直接进入下一单元；不需要输入“继续”。

<a id="choose"></a>
## 选择学习方式

<details>
<summary><strong>我想从零学</strong></summary>

告诉 Skill 你的目标和使用场景即可，不需要先准备课程大纲。

```text
我想从零学 Docker，最后能把一个小型 Web 服务部署到自己的服务器上。
```

</details>

<details>
<summary><strong>我已经有基础</strong></summary>

说明你做过什么，以及现在想解决的具体问题。课程会从能改变路线的缺口开始，而不是重复已掌握内容。

```text
我会写 JavaScript，也用过 React，但不理解渲染、状态更新和并发之间的关系。
请从这些原理开始，并带我看相关的替代方案和边界。
```

</details>

<details>
<summary><strong>我想继续课程</strong></summary>

直接说“继续课程”。Skill 会读取已有的 `COURSE_PLAN.md` 和当前检查点，再从记录的位置开始。

```text
继续我的 HTTP 课程，先复述当前检查点，然后进入下一课。
```

</details>

<details>
<summary><strong>我只想了解一个问题</strong></summary>

直接提问即可。这类一次性问答不需要创建完整课程，也不需要维护课程记录。

```text
为什么 TCP 需要三次握手？它解决了什么问题？
```

</details>

## 一节课会做什么

| 阶段 | 内容 |
| --- | --- |
| 了解起点 | 利用你已经提供的描述、作品和上下文；只有必要时才做少量诊断。 |
| 补足前置 | 发现会阻碍理解的基础缺口时，先用简短背景、例子或解释补齐。 |
| 讲核心原理 | 说明概念、组成关系、运行机制、因果链、适用前提、边界和取舍。 |
| 带出扩展 | 连接相关概念、替代方案、对比边界或后续应用，不堆砌无关知识。 |
| 继续推进 | 你可以提问；问题处理后，课程会沿已知方向自动进入下一课。 |

不强制使用小测、判断题、练习或正式产出验收。你的提问、反馈、作品和后续迁移会在自然发生时帮助修正能力判断。

<a id="install"></a>
## 安装

需要 Git。大多数宿主使用 `~/.agents/skills`，Claude Code 使用 `~/.claude/skills`。

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

目标目录已经存在时，使用更新命令，不要重复克隆：

```bash
# ~/.agents/skills 下的宿主
git -C ~/.agents/skills/daxue-zhidao pull --ff-only

# Claude Code
git -C ~/.claude/skills/daxue-zhidao pull --ff-only
```

更新后重新打开会话；Pi 可执行 `/reload` 重新加载 Skill。

<a id="hosts"></a>
## 支持的宿主

| 宿主 | 开始方式 | 适配说明 |
| --- | --- | --- |
| [OpenCode](references/opencode.md) | 直接描述学习目标 | `question` |
| [Claude Code](references/claude-code.md) | `/daxue-zhidao` | `AskUserQuestion` |
| [Codex](references/codex.md) | `$daxue-zhidao` | `request_user_input` 等宿主能力 |
| [Pi](references/pi.md) | `/skill:daxue-zhidao` | `question` 扩展 |
| [ZCode](references/zcode.md) | `/daxue-zhidao` | `AskUserQuestion` |
| [dsh](references/dsh.md) | `/daxue-zhidao` | `ask_user_question` |

不同宿主的调用方式不同，课程规则保持一致：需要选择时由你决定，讲解中可以随时提问。

<a id="record"></a>
## 课程记录

课程项目目录中的 `COURSE_PLAN.md` 是下一轮教学的执行快照，主要保留：

- 学习目标、场景、基础、约束和必要偏好。
- 当前单元的原理范围、相关扩展和未解决问题。
- 有自然证据支持的能力边界。
- 当前方向以及下一课可选的主线、深化、扩展和应用方向。

创建、恢复、切换方向和单元边界都会清理无关历史。它不记录完整讲义，也不要求以固定练习或验收表结束课程。

## 项目结构

```text
SKILL.md                         核心课程流程
references/course-plan-format.md COURSE_PLAN.md 格式与生命周期
references/<agent>.md            各宿主的调用和工具适配规则
```

需要查看具体规则时，从 [SKILL.md](SKILL.md) 开始；需要检查课程记录格式时，阅读 [course-plan-format.md](references/course-plan-format.md)。
