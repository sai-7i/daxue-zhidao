# Repository Guide

## Scope

- This repository is a portable guided-learning skill, not an executable app; it has no configured build, lint, or test suite.
- `SKILL.md` is the authoritative workflow. Keep its core behavior host-neutral and put OpenCode-only tool guidance in `references/opencode.md`.
- `references/course-plan-format.md` defines persisted `COURSE_PLAN.md` semantics and is intentionally read only when creating, checking, or updating a plan.
- `agents/openai.yaml` is discovery metadata. Keep its description and default prompt aligned with the trigger conditions and mandatory flow in `SKILL.md`.

## Behavioral Contracts

- A new course or genuine direction change requires subject-specific diagnostic questions, then 2-3 proposed starting units, then an explicit semantic learner choice before teaching.
- Teach and verify exactly one observable unit per turn; update the plan only at the unit boundary and then stop for the learner's next choice.
- Do not create a course plan until the learner confirms both the topic and storage mode. Temporary mode must never write course state to disk.
- Local environment inspection requires prior consent and collects only course-relevant versions/status. Never inspect or persist secrets, complete environment variables, browser data, or credential contents.
- In course plans, environment/overview/checkpoint sections are mutable snapshots; unit, correction, and direction-change histories are append-only. Unit numbers remain consecutive integers and completion requires an observation satisfying the predeclared success criterion.

## Editing Checks

- Preserve the Chinese `daxue-zhidao` skill name, `zh-CN` metadata, and relative reference links when moving or restructuring content.
- When changing plan states, templates, or lifecycle rules, reconcile every occurrence across `SKILL.md` and `references/course-plan-format.md`.
- When changing OpenCode tool behavior, update only `references/opencode.md` unless the host-independent authorization or teaching contract also changes.
- With no automated checks, review all four shipped files together and verify YAML/frontmatter syntax, Markdown links, and cross-file terminology before finishing.
