<div align="center">

# 大学之道

### 🧭 面向真实技术任务的渐进式学习 Skill

`zh-CN` · `6` 个宿主适配 · `技术地图` 驱动 · `单元制` 教学

[⚡ 开始](#-开始学习) · [📦 安装](#-安装) · [🔄 更新](#-更新) · [🧩 宿主](#-支持宿主)

</div>

> [!TIP]
> 仅由用户手动调用，模型不主动触发。它会先联网调研技术生态，建立可追溯的技术地图，再按你的真实目标逐单元推进。

## 🌿 分支选择

本仓库提供两个功能分支，默认克隆得到 `guide`：

| 分支     | 说明                                                         | 默认  |
| ------- | ---------------------------------------------------------- |:---: |
| `guide` | 渐进式引导版：先建技术地图，再按真实目标逐单元讲解、评估并推进课程                         | ✓   |
| `map`   | 技术地图版：研究课程/课次地图，规划路线与学习计划，不教授内容                            |     |

两者共用相同宿主适配与安装位置，仅 `SKILL.md` 流程与地图格式不同。

## ✨ 适用范围

| ✅ 适合                         | ❌ 不适合          |
| ---------------------------- | -------------- |
| 学习编程语言、框架、库、SDK、CLI、云服务与工程实践 | 只需要一个即时答案      |
| 围绕真实项目目标系统补齐技术能力             | 要求一次性给出完整大纲或教程 |
| 比较技术路线、迁移方案、旧技术与新生态          | 希望 AI 替你决定学习方向 |

## 📍 项目状态

| 模块                                            | 状态       | 作用                |
| --------------------------------------------- |:--------:| ----------------- |
| [核心流程](SKILL.md)                              | 🟢       | 研究 → 选路 → 教学 → 推进 |
| [技术地图格式](references/technology-map-format.md) | 🟢       | 记录主流、成熟、冷门与迁移路线   |
| [课程计划格式](references/course-plan-format.md)    | 🟢       | 维护精简、可恢复的学习快照     |
| 宿主适配                                          | 🟢 `6/6` | 结构化提问与实际工具边界      |

## ⚡ 开始学习

安装后，输入对应命令，再描述目标：

```text
/daxue-zhidao 我会 JavaScript，想学习 React 的渲染和状态更新，目标是维护一个中型项目。
```

```text
/daxue-zhidao 从零学习 Rust，目标是做一个能读取 CSV 文件的命令行工具。
```

<details>
<summary><strong>🧠 学习过程</strong></summary>

| 阶段   | 你提供          | Skill 处理                                      |
|:----:| ------------ | --------------------------------------------- |
| `01` | 主题、真实目标、已有基础 | 先依据初始请求建立带来源和日期的 `TECHNOLOGY_MAP.md` |
| `02` | 技术地图、已有知识 | 依据地图诊断已有知识，再规划路线                    |
| `03` | 选择方向           | 提供未完成且不重复的主线与扩展路线                  |
| `04` | 阅读与回答          | 按水平讲解；等待阅读，以单元问题校准程度后继续课程        |
| `05` | 课程结束           | 评估整体掌握度，选择新课或深化当前内容               |

</details>

## 📦 安装

> 前置条件：已安装 [Git](https://git-scm.com/)。选择与你的 Agent 对应的一组命令执行一次；不指定 `-b` 时默认克隆 `guide` 分支。

### 🗂️ OpenCode · Codex · Pi · ZCode · dsh

```bash
# guide 分支（默认）
mkdir -p ~/.agents/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao

# map 分支
git clone -b map https://github.com/sai-7i/daxue-zhidao.git ~/.agents/skills/daxue-zhidao
```

### 🟠 Claude Code

```bash
# guide 分支（默认）
mkdir -p ~/.claude/skills
git clone https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao

# map 分支
git clone -b map https://github.com/sai-7i/daxue-zhidao.git ~/.claude/skills/daxue-zhidao
```

## 🔄 更新

| 安装位置                            | 更新命令                                                  |
| ------------------------------- | ----------------------------------------------------- |
| `~/.agents/skills/daxue-zhidao` | `git -C ~/.agents/skills/daxue-zhidao pull --ff-only` |
| `~/.claude/skills/daxue-zhidao` | `git -C ~/.claude/skills/daxue-zhidao pull --ff-only` |

更新后可在当前会话继续；Pi 可额外执行 `/reload`。切换分支会覆盖本地改动，确认后执行：

```bash
git -C ~/.agents/skills/daxue-zhidao fetch origin
git -C ~/.agents/skills/daxue-zhidao checkout map     # 切到 map
git -C ~/.agents/skills/daxue-zhidao checkout guide   # 切回 guide
```

## 🧩 支持宿主

| Agent                                    | 唤起方式                  | 安装位置               | 适配说明                 |
| ---------------------------------------- | --------------------- | ------------------ | -------------------- |
| [OpenCode](references/opencode.md)       | `/daxue-zhidao`       | `~/.agents/skills` | `question`           |
| [Claude Code](references/claude-code.md) | `/daxue-zhidao`       | `~/.claude/skills` | `AskUserQuestion`    |
| [Codex](references/codex.md)             | `$daxue-zhidao`       | `~/.agents/skills` | `request_user_input` |
| [Pi](references/pi.md)                   | `/skill:daxue-zhidao` | `~/.agents/skills` | `question` 扩展        |
| [ZCode](references/zcode.md)             | `/daxue-zhidao`       | `~/.agents/skills` | `AskUserQuestion`    |
| [dsh](references/dsh.md)                 | `/daxue-zhidao`       | `~/.agents/skills` | `ask_user_question`  |

<div align="center">

`课程记录：COURSE_PLAN.md` &nbsp;·&nbsp; `研究地图：TECHNOLOGY_MAP.md`

</div>
