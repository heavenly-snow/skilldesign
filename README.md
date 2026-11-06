# Dev Flow

Dev Flow 是一套个人主导、AI 协作的研发 Skill。从几句话或会议纪要开始，逐步形成设计，再按可独立验收的批次开发。AI 主动展示关键技术取舍、批次初版和验收判断，用户围绕具体方案和证据参与讨论。

## 快速开始

保留整个仓库的目录结构。在支持本地 Skill 的工具里，把 `skills/` 下的 **11 个目录一起**放到工具可发现的 Skill 目录，同级放置。总调度器和子 Skill 通过相对路径引用共享规则。也可以在当前会话中指定 [总入口文件](skills/dev-flow/SKILL.md) 使用。

- `$dev-flow 根据这份会议纪要开启一轮，先整理 PRD 初稿`
- `$dev-flow-batch-plan 为 R01 制定开发批次初版`
- `$dev-flow-infrastructure 执行 R01/B00`
- `$dev-flow-batch-implement 执行 R01/B01`
- `$dev-flow-resume 恢复 R01`

## 工作方式

设计按需求澄清、架构、产品原型、数据库和接口推进。每一步显式参考已形成的前序产物。开发时，AI 按批次目标自行查阅所需资料，先建立或核实基础设施，再实现当前业务批次，提交验证证据并停在验收点。

轮次索引、设计产物与 `开发批次.md` 写入目标项目。已有约定时沿用，默认位于 `docs/dev-flow/`。二期需求开新轮次，并引用上一轮已验收的基线。各阶段沿用目标项目的技术栈和验证命令。

## 仓库结构

| 路径 | 内容 |
|---|---|
| [导引.mdc](导引.mdc) | Agent 入口和阶段选择 |
| [skills/](skills/) | 总调度器、五个设计 Skill、五个开发 Skill |
| [PRD.md](PRD.md) | 产品需求与验收场景 |
| [架构设计.md](架构设计.md) | 职责、文件命名、状态与多轮交付 |

共享契约随[总调度器](skills/dev-flow/SKILL.md)分发，批次模板随[批次规划 Skill](skills/dev-flow-batch-plan/SKILL.md)分发。
