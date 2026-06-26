# 第 03 章 Workspace 标准

> **Workspace 是整个研发环境的组织规范，而不是某一个目录或 Git 仓库。**

---

# 为什么

随着项目不断增加，团队通常会遇到以下问题：

* 项目越来越多，缺少统一管理方式。
* 公共组件不断复制。
* Prompt 分散在不同项目中。
* Design System 无法共享。
* AI 每进入一个项目，都需要重新建立上下文。
* 项目之间缺少统一规范。

这些问题并不是因为 Git 使用不当。

而是因为：

整个研发环境缺少统一的组织方式。

Workspace 正是为了解决这一问题而存在。

---

# 核心思想

Workspace 不是一个目录。

也不是一个 Git 仓库。

Workspace 首先是一套：

**研发环境组织规范（Engineering Workspace）。**

它回答的是：

* 当前有哪些研发资产？
* 它们之间是什么关系？
* 哪些资源可以共享？
* 哪些资源属于某一个项目？
* AI 应该从哪里开始理解整个研发环境？

因此：

Workspace 描述的是：

整个研发环境。

而不是：

某一个软件项目。

---

# 标准规范

一个 AI Native Workspace 应至少包含以下三类资产。

---

## 一、Repository（研发资产）

Repository 是研发工作的基本单位。

例如：

* 产品项目
* Design System
* SDK
* Prompt Library
* Knowledge Base

每一个 Repository 都拥有：

* 独立生命周期
* 独立版本
* 独立发布流程
* 独立权限

Workspace 负责组织这些 Repository。

而不是替代 Repository。

---

## 二、Shared Resources（共享资源）

共享资源不属于任何单一项目。

例如：

* 模板
* Prompt
* 开发规范
* Design Token
* 通用脚本
* Logo
* 示例工程

共享资源应统一维护。

避免：

每个项目复制一份。

---

## 三、Local Runtime（本地运行环境）

每位开发者都有自己的运行环境。

例如：

* 本地缓存
* Agent Runtime
* 日志
* Embedding
* 向量数据库
* 本地模型

这些内容：

不属于项目。

也不建议纳入 Git。

它们属于：

开发者自己的 Local Runtime。

---

# 实施方法

推荐采用：

**一个 Workspace。**

**多个 Repository。**

Workspace：

负责组织。

Repository：

负责版本管理。

Runtime：

负责运行。

三者职责明确。

推荐关系如下：

```text
Workspace
│
├── Repository
│
├── Shared Resources
│
└── Local Runtime
```

注意：

这是逻辑结构。

而不是固定目录。

任何能够表达这一组织关系的平台，都可以作为 Workspace。

---

# 推荐结构

对于个人开发者或中小团队，可以采用如下实现：

```text
GitHub Organization
│
├── aura
├── aivio
├── aura-design-system
├── shared
└── knowledge
```

开发者本地：

```text
D:\AI-Workspace\
```

负责：

* Clone Repository
* 本地开发
* 本地运行
* 本地缓存

共享发生在 Repository。

运行发生在 Local Runtime。

组织发生在 Workspace。

---

# 示例

假设团队维护三个产品：

* AURA
* Aivio
* 官网

同时维护：

* Design System
* Prompt Library
* Knowledge Base

这些资源：

都属于：

Workspace。

但是：

每一个 Repository：

仍然拥有自己的 Git 仓库。

这样：

任何一个项目都可以独立演进。

同时又共享统一规范。

---

# 最佳实践

建议：

Workspace 只负责：

组织。

不要承担：

版本管理。

不要承担：

运行。

不要承担：

部署。

保持：

职责单一。

Repository：

负责项目。

Runtime：

负责运行。

Workspace：

负责组织。

---

# 常见错误

**错误一：把 Workspace 理解成一个超级 Git 仓库。**

Workspace 不是 Monorepo。

Repository 才是 Git 管理单位。

---

**错误二：共享资源放在某一个项目中。**

例如：

Prompt 放在 AURA 项目。

其他项目复制使用。

长期维护成本会越来越高。

---

**错误三：把 Runtime 数据提交到 Git。**

例如：

日志。

缓存。

Embedding。

模型索引。

这些都属于 Runtime。

不属于 Repository。

---

# Checklist

请确认：

* [ ] Workspace 与 Repository 已明确区分。
* [ ] Repository 作为版本管理单位。
* [ ] Shared Resources 独立维护。
* [ ] Runtime 不进入 Git。
* [ ] Workspace 能支持多个项目长期协作。
* [ ] AI 能快速理解整个研发环境。

---

# 本章总结

Workspace 并不是一个目录。

也不是一个 Git 仓库。

它是一套组织整个研发环境的规范。

Workspace 负责组织。

Repository 负责版本。

Runtime 负责运行。

三者共同构成 AI Native 工作空间。

后续章节将进一步介绍：

如何设计一个 AI 可自解释（AI Self-Describing）的 Repository。
