---
type: overview
title: "LLM Wiki 综述"
topics: ["知识管理", "LLM", "Obsidian"]
---

# LLM Wiki 综述

> 本知识库的入口页面。了解概念 → [[wiki/concepts/LLM Wiki]]，看对比 → [[wiki/comparisons/LLM Wiki vs RAG]]。

## 这是什么

[[wiki/concepts/LLM Wiki]] 模式的一个实例 —— 由 [[wiki/entities/Obsidian|Obsidian]] + LLM Agent 驱动的技术知识库。

每个页面由 LLM 根据 [[CLAUDE.md]] 的约定维护，人类负责策展源和指导方向。

## 页面地图

| 类别 | 目录 | 已有页面 |
|------|------|---------|
| 概念 | `wiki/concepts/` | [[wiki/concepts/LLM Wiki]], [[wiki/concepts/RAG]], [[wiki/concepts/AI Agent]], [[wiki/concepts/AI 核心概念]], [[wiki/concepts/AI 关键技术]], [[wiki/concepts/AI 协议与架构]], [[wiki/concepts/AI 应用模式]] |
| 实体 | `wiki/entities/` | [[wiki/entities/Obsidian]], [[wiki/entities/AI Agent 开发框架]] |
| 对比 | `wiki/comparisons/` | [[wiki/comparisons/LLM Wiki vs RAG]] |
| 概览 | `wiki/overviews/` | 本页, [[wiki/overviews/AI 术语总览]] |
| 源 | `wiki/sources/` | [[wiki/sources/LLM Wiki 蓝图]], [[wiki/sources/AI 名词解释]] |

## 目录结构

```
./
├── CLAUDE.md           ← LLM 操作手册
├── index.md            ← 内容目录
├── log.md              ← 时间日志
│
├── raw/                ← 不可变源文档
│   ├── articles/       ← 技术文章
│   ├── papers/         ← 学术论文
│   ├── docs/           ← 官方文档
│   ├── videos/         ← 讲座/视频
│   ├── books/          ← 书籍章节
│   └── assets/         ← 源文件附带图片（归档）
│
├── _templates/         ← 页面模板
│   ├── t-source.md
│   ├── t-entity.md
│   ├── t-concept.md
│   └── t-comparison.md
│
└── wiki/               ← LLM 维护的页面
    ├── concepts/       ← 概念、方法论
    ├── entities/       ← 工具、项目、人物
    ├── sources/        ← 源摘要
    ├── comparisons/    ← 结构化对比
    ├── overviews/      ← 综述 Hub
    └── assets/         ← Wiki 图片
```

## 关键约定

- 🔤 **语言**：CLAUDE.md 英文，Wiki 正文简体中文
- 🔗 **链接**：全部 `[[wikilink]]`
- 🚫 **不入链 raw**：Wiki 页不直接连源文档，只连 `wiki/sources/` 摘要页
- 📝 **零孤页**：每个新页面至少一条入链，见 [[index.md]]
- ⚠️ **矛盾显式标注**：`> ⚠️ 矛盾：...`
- 📋 **日志**：`## [YYYY-MM-DD] 操作 | 描述`，见 [[log.md]]
- 🔍 **Lint**：定期检查矛盾、过期、孤立、缺口

## 操作

详见 [[wiki/concepts/LLM Wiki#三种操作|LLM Wiki 的三种操作]]。

- **Ingest** → 说 "处理" 或 "ingest"
- **Query** → 直接提问
- **Lint** → 说 "检查" 或 "lint"

## 资产策略

| 目录 | 规则 |
|------|------|
| `raw/assets/` | 随源归档，不可变 |
| `wiki/assets/` | Wiki 图表，LLM 管理 |

两者分离避免清理源时误删 Wiki 正在使用的图片。
