---
name: dev-flow
description: 调度个人主导的研发流程。用于开启或定位交付轮次、从设计阶段进入分批开发，以及按现有开发记录恢复工作。
---
# Dev Flow

先读取[共享契约](references/workflow.md)，识别目标项目、轮次和用户要求执行的动作。只读取当前动作对应的子 Skill，按其停止点执行。相对路径以本文件目录为基准。

| 动作 | 子 Skill |
|---|---|
| 从零散需求形成 PRD | [需求澄清](../dev-flow-prd/SKILL.md) |
| 写架构初稿、讨论技术取舍 | [架构设计](../dev-flow-architecture/SKILL.md) |
| 生成或修改产品原型 | [产品原型](../dev-flow-prototype/SKILL.md) |
| 设计数据库 | [数据库设计](../dev-flow-data-design/SKILL.md) |
| 设计接口 | [接口设计](../dev-flow-api-design/SKILL.md) |
| 制定或调整批次 | [批次规划](../dev-flow-batch-plan/SKILL.md) |
| 建立或核实开发基线 | [基础设施](../dev-flow-infrastructure/SKILL.md) |
| 执行指定业务批 | [批次实现](../dev-flow-batch-implement/SKILL.md) |
| 审查和验收 | [批次验收](../dev-flow-batch-review/SKILL.md) |
| 恢复工作 | [恢复流程](../dev-flow-resume/SKILL.md) |

开启新轮时先登记索引和基线。用户只要求开启轮次时，展示登记结果及建议入口。已有适用产物时，从用户指定的阶段进入。依用户授权推进当前阶段，待讨论或待验收的事项按对应子 Skill 处理。
