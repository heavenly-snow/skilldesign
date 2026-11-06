---
name: dev-flow-batch-implement
description: 执行已讨论的单个业务开发批次，处理设计冲突并交付验证证据。
---
# dev-flow-batch-implement

先读[共享契约](../dev-flow/references/workflow.md)，定位目标项目、轮次及现有产物或批次。

确认轮次、当前批、依赖和验收条件，标记进行中。自行选择所需代码和设计依据。发现必须改变已确认的业务规则、公开接口或数据设计时，记录冲突依据、推荐和影响，暂停相关改动并显式提交讨论。独立部分可继续。对照验收条件验证真实调用路径并更新证据。完成本批后按[验收 Skill](../dev-flow-batch-review/SKILL.md)准备初判，停在验收点。
