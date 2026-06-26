# Chapter Specification

## Chapter 04：Repository 标准

Status：Architecture Approved  
Implementation：Pending

---

# 章节目标

本章回答一个核心问题：

> 如何设计一个能够让 AI 第一次进入项目就开始工作的 Repository？

本章不是 Git 教程，也不是目录清单，而是建立 AI Native Repository Standard。

Repository 是 Workspace 的组成单位。

- Workspace 负责组织整个研发环境。
- Repository 负责组织单个项目。
- Runtime 负责本地运行环境。

本章只讨论单个 Repository，不重新讨论 Workspace。

---

# 本章定位

第 03 章已经定义：

> Workspace 是整个研发环境的组织规范。

第 04 章进一步定义：

> Repository 是单个项目的唯一可信来源，也是 AI 进入项目后的基本理解单位。

因此，本章重点不在“如何使用 Git”，而在“如何让一个 Repository 具备自解释能力”。

---

# 本章需要解决的问题

读者读完本章后，应该能够回答：

1. Repository 为什么存在？
2. AI Native Repository 与传统 Repository 有什么区别？
3. 为什么 Repository 是 AI 协作的基本单位？
4. Repository 应包含哪些长期文件？
5. 哪些内容属于 Repository，哪些内容不属于 Repository？
6. Repository 的生命周期如何维护？

---

# 本章边界

本章不讨论：

- Git 命令
- GitHub 使用方法
- Branch 策略
- Commit 规范
- Pull Request 流程
- CI/CD

这些内容属于第 06 章《Git 工作流》。

本章也不重新定义 Workspace。Workspace 已在第 03 章定义。

---

# 核心思想

Repository 不只是代码仓库。

在 AI Native 工作流中，Repository 应该能够完整描述一个项目。

对于 AI 而言，进入一个 Repository 后，应该能够快速理解：

- 项目是什么
- 项目为什么存在
- 当前做到哪里
- 架构如何组织
- 近期任务是什么
- 有哪些历史决策
- 如何开始工作

因此，本章需要强调：

> AI Native Repository 应该是 AI Self-Describing Repository。

即：AI 可自解释仓库。

---

# 核心定义

Repository 是一个项目的唯一可信来源（Single Source of Truth）。

Repository 应同时包含：

- 代码
- 文档
- 规范
- 决策
- 上下文
- 历史记录

而不是只有代码。

---

# 必须介绍的长期文件

本章必须首次正式介绍以下文件的职责：

## README.md

项目入口文件。用于让人和 AI 快速了解项目基本信息。

## PROJECT_CONTEXT.md

项目上下文文件。用于让 AI 理解项目目标、背景、边界、现状和约束。

## ARCHITECTURE.md

架构说明文件。用于描述系统结构、模块关系、核心技术选择和架构边界。

## DECISIONS.md

决策记录文件。用于记录重大设计选择、原因和影响。

## TASKS.md

任务管理文件。用于记录当前任务、短期计划和待办事项。

## CHANGELOG.md

变更记录文件。用于记录项目演进历史。

注意：

本章只说明这些文件为什么存在、承担什么职责，不展开完整模板。

完整模板放到第 22 章《模板中心》。

---

# 推荐章节结构

正文必须遵守 `WRITING_RULES.md` 的固定结构：

1. 为什么
2. 核心思想
3. 标准规范
4. 实施方法
5. 推荐结构
6. 示例
7. 最佳实践
8. 常见错误
9. Checklist
10. 本章总结

---

# 标准要求

## MUST

Repository 必须能够让新的 AI 第一次进入项目后，理解：

- 项目目标
- 当前状态
- 基本架构
- 工作规范
- 当前任务

## SHOULD

Repository 应该长期保持自解释能力。

所有重要知识应沉淀到仓库，而不是只存在于聊天记录或个人记忆中。

## MAY

Repository 可以根据项目规模增加：

- ADR
- docs/
- examples/
- scripts/
- tests/
- specifications/

但不应为了形式而堆叠目录。

---

# Editorial Goals

本章写作时必须遵守：

- 工程实践优先。
- 长期有效。
- 不绑定具体 AI 工具。
- 不绑定具体平台。
- 不写 Git 教程。
- 不写 GitHub 教程。
- 不展开模板正文。
- 所有案例必须能够落地。

---

# 验收标准

Codex 完成本章正文后，应满足：

- [ ] 没有重新定义 Workspace。
- [ ] 没有介绍 Git 命令。
- [ ] 没有介绍 Branch / Commit / PR。
- [ ] 明确提出 AI Self-Describing Repository。
- [ ] 解释 README、PROJECT_CONTEXT、ARCHITECTURE、DECISIONS、TASKS、CHANGELOG 的职责。
- [ ] 严格遵守 WRITING_RULES.md。
- [ ] 内容可直接落地。
- [ ] 未修改其他章节正文。

---

# Architecture Review

Status：APPROVED

可以进入 Implementation。
