# BOOK_SDLC

> Book Software Development Life Cycle
>
> Version: 1.0

---

# 1. 目的

本文件定义《AI Native 研发操作手册（中文版）》的开发流程。

本项目采用 **Book as Code** 的开发方式。

一本书应像一个软件项目一样进行规划、实现、审查、迭代和发布。

本文件不是正文的一部分。

它用于指导所有参与本项目的人类和 AI 协作者。

---

# 2. 开发原则

本项目遵循以下原则：

* 先设计，再实现。
* Specification 驱动开发。
* 正文不直接修改。
* 所有章节必须经过 Editorial Review。
* 所有规范优先于正文。
* 所有重大决定必须记录。

---

# 3. 生命周期

每个章节必须遵循以下生命周期。

```text
Planning
    │
    ▼
Architecture
    │
    ▼
Specification
    │
    ▼
Implementation
    │
    ▼
Editorial Review
    │
    ▼
Editorial Refactor
    │
    ▼
Freeze
    │
    ▼
Release
```

任何章节不得跳过中间阶段。

---

# 4. 阶段说明

## 4.1 Planning

目标：

确定章节定位。

输出：

* 章节目标
* 边界
* 阅读对象

负责人：

ChatGPT（主编）

---

## 4.2 Architecture

目标：

确定章节整体设计。

回答：

* 为什么写这一章？
* 解决什么问题？
* 与其它章节关系？
* 不讨论什么？

输出：

Architecture Design

负责人：

ChatGPT

---

## 4.3 Specification

目标：

形成正式规格说明。

输出：

`specifications/chapter-xx-*.md`

Specification 是正文唯一依据。

负责人：

ChatGPT

---

## 4.4 Implementation

目标：

根据 Specification 编写章节正文。

禁止：

自行扩展章节。

自行增加新概念。

自行修改目录。

输出：

`chapters/...`

负责人：

Codex

---

## 4.5 Editorial Review

目标：

检查正文是否符合：

* Specification
* WRITING_RULES
* STYLE_GUIDE
* TERMINOLOGY
* PROJECT_CONSTITUTION

Review 不直接修改正文。

所有修改建议统一进入：

`EDITORIAL_NOTES.md`

负责人：

ChatGPT

---

## 4.6 Editorial Refactor

目标：

根据 Editorial Review 修改正文。

负责人：

Codex

---

## 4.7 Freeze

目标：

冻结章节。

冻结后：

不再进行编辑。

除非：

发现事实错误。

或：

重大结构问题。

负责人：

ChatGPT

---

## 4.8 Release

目标：

发布对应版本。

例如：

* Part Release
* Version Release

负责人：

ChatGPT

---

# 5. 角色分工

## ChatGPT（Editor-in-Chief）

负责：

* 方法论
* 架构
* Specification
* Editorial Review
* Terminology
* 最终批准

不负责：

长期维护正文。

---

## Codex（Technical Editor）

负责：

* 正文实现
* Markdown 维护
* 案例补充
* 格式统一
* Refactor
* Git Commit

不负责：

修改章节目标。

修改项目架构。

新增规范。

---

## GitHub

负责：

* 版本管理
* Commit History
* Release
* 协作记录

---

# 6. Definition of Done

一个章节只有满足以下条件，才算完成：

* [ ] Architecture 已完成
* [ ] Specification 已批准
* [ ] 正文已完成
* [ ] Editorial Review 已通过
* [ ] Editorial Notes 已处理
* [ ] 已提交 Git
* [ ] 已 Push
* [ ] 已 Merge
* [ ] 状态为 Freeze

---

# 7. Dogfooding Principle

本项目提出的规范，应首先应用于本项目自身。

如果本手册中的某项规范无法应用到本手册的开发过程中，应重新评估该规范是否合理。

本手册既是知识产品，也是 AI Native 工作流的实践案例。

---

# 8. 持续改进

BOOK_SDLC 属于项目架构文件。

任何修改都应：

1. 提出 Architecture Decision；
2. 更新 DECISIONS.md；
3. 通过 Editorial Review；
4. 再更新本文件。

避免在开发过程中频繁调整工作流。

---

# Version History

## v1.0

* 建立 Book Software Development Life Cycle。
* 建立章节生命周期。
* 明确 ChatGPT、Codex、GitHub 的职责分工。
* 引入 Dogfooding Principle。
