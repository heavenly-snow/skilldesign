# 项目知识清点 · Project Knowledge Review

把 AI 辅助交付的项目变成一次从需求到设计的练习。

- 说「我想从零学会怎么做这个项目」，AI 会先帮你明确一条最小需求。你决定输入、输出和验收，AI 在独立的空目录实现，你亲手运行。之后每次加一个需求，比较取舍、验证结果，再映射回成品。
- 说「只做知识清点」，AI 会从项目提取知识点和源码落点，由你判断掌握程度，再讲你选中的缺口。

默认产物是复杂度演化线，记录每个需求怎样改变架构、你选择了什么，以及怎么验收。知识清点模式可以继续使用知识账本。

## 安装

把整个目录放到工具扫描的 skills 目录，例如 Codex 的 ~/.codex/skills/、Claude Code 的 ~/.claude/skills/，或 Hermes Agent 的 $HERMES_HOME/skills/learning/。在只支持粘贴文本的环境，可以直接粘贴 SKILL.md 使用主流程。

- [SKILL.md](SKILL.md) 是入口和默认搭建流程。
- [知识清点模式](references/knowledge-review.md) 保留原来的提取、自评、教学和记账流程。
