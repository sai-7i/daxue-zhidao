---
name: daxue-zhidao
description: 仅由用户手动调用，模型不主动触发。为技术主题建立课程与课次技术地图，规划学习路线；不教授课程详细内容。
disable-model-invocation: true
compatibility: opencode, claude-code, codex, pi, zcode, dsh
metadata:
  language: zh-CN
  workflow: guided-learning
---

# 大学之道

读取当前宿主适配。无法识别则停止需要学习者决策的流程。

## 流程

1. **恢复：**按[计划格式](references/course-plan-format.md)规范化计划和地图；缺失文件按格式创建并继续。
2. **开课：**按[课程地图格式](references/technology-map-format.md)研究并生成详细 `TECHNOLOGY_MAP.md`；诊断已有知识，提供主线与扩展方向，选择后建计划。
3. **选课：**按[课次地图格式](references/lesson-map-format.md)生成详细 `LESSON_MAP.md`；只提供介绍和学习规划。
4. **调整：**仅按学习者请求评估路线、方向或深入范围；不评估具体知识内容。

## 不可违反的规则

- 诊断、方向和课程选择用宿主结构化提问；问题对应地图。工具失败即停止，不代选、不问授权或既定事项。
- 两类地图详细可追溯，覆盖当前决策所需的技术、前置、边界、成本、替代和迁移；核实失败即停止。课程地图不记录进度；每次选课重建课次地图。
- `COURSE_PLAN.md` 是六模块路线快照；确认约束不改，除取消整课外原位更新。状态仅 `进行中`/`已完成`；取消整课删计划和地图。
- 不将环境或访问限制转为提问；不可用即说明并停止。不处理秘密或无关个人资料。
