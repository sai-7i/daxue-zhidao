# Repository Guide

<!-- daxue-zhidao:critical-constraint -->
## Critical OpenCode Constraint

- During guided teaching, every choice, confirmation, authorization, diagnosis, and checkpoint confirmation MUST use the `question` tool.
- If `question` is unavailable or fails, stop that decision. Never ask in plain text, infer a choice, or continue past it.
- Before every `COURSE_PLAN.md` write and at each course boundary, normalize it to the minimal execution snapshot; delete teaching content, explanations, dialogue summaries, duplicate facts, stale candidates, resolved issues, and useless history.
<!-- /daxue-zhidao:critical-constraint -->

## Scope

- This repository is a portable guided-learning skill, not an executable app; it has no configured build, lint, or test suite.
- `SKILL.md` is the authoritative workflow. Keep its core behavior host-neutral and put OpenCode-only tool guidance in `references/opencode.md`.
- `references/course-plan-format.md` defines persisted `COURSE_PLAN.md` semantics and is intentionally read only when creating, checking, or updating a plan.
- Codex-specific `agents/openai.yaml` metadata is intentionally omitted; `SKILL.md` alone defines discovery and behavior.
- Host-specific behavior belongs in `references/opencode.md`, `references/claude-code.md`, `references/codex.md`, `references/pi.md`, `references/zcode.md`, or `references/dsh.md`; keep the core contract in `SKILL.md` host-neutral.

## Behavioral Contracts

- Ground each course in a concrete real-world mission and observable success performance. Ask only questions that can change the teaching start, route, authorization, or constraints.
- Teach and verify one tightly scoped unit at a time. Present materially different routes without recommending, ranking, or choosing one for the learner.
- Do not create a course plan until the learner confirms the topic, mission, and starting unit. Course state is always persisted to `COURSE_PLAN.md`.
- Course and unit statuses are only `进行中` or `已完成`. Unit completion records success under observed conditions, not permanent mastery; later retrieval or transfer evidence may strengthen or narrow the ability boundary.
- Reuse completed abilities through retrieval and transfer instead of reteaching them. If later evidence exposes a gap, create a focused reinforcement unit and replace the overbroad ability claim.
- Local environment inspection requires prior consent and collects only course-relevant versions/status. Never inspect or persist secrets, complete environment variables, browser data, or credential contents.
- Treat `COURSE_PLAN.md` as an execution snapshot, never course notes. Before every write and at creation, recovery, direction changes, and unit boundaries, normalize it to the minimal task, necessary constraints/environment, ability boundaries with strongest evidence, current unit, and next choices. Delete explanations, dialogue summaries, teaching content, duplicate facts, stale candidates, resolved issues, and useless history.

## Editing Checks

- Preserve the Chinese `daxue-zhidao` skill name, `zh-CN` metadata, and relative reference links when moving or restructuring content.
- When changing plan states, templates, or lifecycle rules, reconcile every occurrence across `SKILL.md` and `references/course-plan-format.md`.
- When changing one host's tool behavior, update only its reference unless the host-independent authorization or teaching contract also changes.
- With no automated checks, review `SKILL.md`, the course-plan format, and all host adapters together; verify frontmatter syntax, Markdown links, and cross-file terminology before finishing.
