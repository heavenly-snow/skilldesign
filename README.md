# 项目知识清点 · Project Knowledge Review

项目做完之后，把涉及的知识提取出来，判断你掌握了没有，只教缺的那部分。

**解决的问题**：AI 时代东西做出来了，但你没学会。全看代码太贵，不看又永远不知道自己缺什么。

**不解决的问题**：它不是 code review，不评价代码好坏、不找 bug。

---

## 30 秒上手

装好之后，对 AI 说：

```
清点一下这个项目
```

它会读完项目，给你一张按知识域分组的清单，每条一个问题 + 一个精确落点。你逐条回「会 / 不会 / 不用会」，它只讲不会的那些。

---

## 安装

### Hermes Agent

```bash
mkdir -p "$HERMES_HOME/skills/learning"
cp -r project-knowledge-review "$HERMES_HOME/skills/learning/"
```

放在 `$HERMES_HOME/skills/<任意分类>/project-knowledge-review/` 下即可，Hermes 递归扫描子目录，分类名随意。

### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -r project-knowledge-review ~/.claude/skills/
```

### Codex CLI

```bash
mkdir -p ~/.codex/skills
cp -r project-knowledge-review ~/.codex/skills/
```

### Cursor / 其他支持 Agent Skills 的 runtime

放到它扫描的 skills 目录。协议是开放的（[agentskills.io](https://agentskills.io)），`SKILL.md` 加 YAML frontmatter 就够。

### 不支持 skills 的环境

`SKILL.md` 是自包含的。把它整篇粘进对话框，再说「按这个流程清点当前项目」即可。配套的 `references/` 和 `templates/` 是增强项，粘不进去也不影响主干。

---

## 目录

```
project-knowledge-review/
├── SKILL.md                    主流程（自包含，可单文件使用）
├── references/
│   ├── extraction.md           提取细则：域骨架、粒度自检、落点格式
│   └── teaching.md             教学协议：诊断、因果链、禁做清单
└── templates/
    └── ledger.md               账本模板
```

账本本体不放在这里——放在项目根或你的笔记里，跨项目累积。

---

## 一次完整对话长什么样

```
你：清点一下这个项目

AI：（读完代码和提交记录）
    ## 技术轨（12 条）
    **A1 · 数据库的锁粒度与并发写**
    问：写锁是库级还是表级？……
    落点：app/db.py › get_connection()

    **A2 · 原子认领（CAS）**
    ……

    ## 业务轨
    ### 领域知识（可迁移）
    ### 设计决策（△ 待确认）

    ## 我预判属于配方的（建议不用会）
    ……

    嫌多就只判 A/B/C 这几条主干，其余扫一眼标「不用会」。
    回格式：会：… / 不会：… / 不用会：其余

你：A1 库级，其他不知道
    会：C1
    不会：A2 A3 B2 B3
    不用会：其余

AI：（先诊断：你的目的层完整、机制层空白）
    这一批讲 A1–B3，它们是一条因果链：
    锁是库级的 → 不能靠锁排队 → 靠条件更新 → ……
    （逐条讲机制，绑到你的代码行，给准确的异常名）
    讲完了。挑一条用自己的话讲一遍，我看看卡在哪。

你：……

AI：（记账，更新账本）
```

---

## 常见问题

**没有 git 能用吗？**
能。git 只是加分项——提交记录里的 `fix` / `harden` / `raise X to Y` 是高质量的返工信号。没有就靠产物结构反推。

**项目没代码，只有文档和产出物呢？**
也能用。知识域从产出物的结构反推，落点退到文档章节或模块级。

**要花多少 token？**
读项目那一步最贵，中小型项目通常几万 token。之后每批教学几千。

**账本多人共用吗？**
不建议。这是个人认知账本，混在一起就失去意义了。

**为什么每条都是问句？**
断言（「这里没开 WAL，有隐患」）只能让人防御；问句（「两种 journal 模式下读写会不会互相阻塞？」）才能让人回答会 / 不会。整份清单的设计目的就是**可回答**。

**「不用会」是不是偷懒？**
不是。AI 时代大部分执行细节学了也是负收益。判据是「缺了它会不会剥夺你和 AI 协作时的指挥权」——不会的，就不学。

---

## 许可

MIT。
