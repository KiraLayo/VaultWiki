---
type: log
title: "日志"
---

# 日志 Log

> 按时间顺序记录所有操作：摄入、查询、检查。
> 条目格式：`## [YYYY-MM-DD] 操作类型 | 描述`

## [2026-06-12] init | LLM Wiki 初始化
- 创建: CLAUDE.md, index.md, log.md, `_templates/` (4 个模板)
- 建立目录结构: `raw/`, `_templates/`, `concepts/`, `entities/`, `sources/`, `comparisons/`, `overviews/`, `assets/`
- 摘要: 根据 [[raw/llm-wiki.md]] 蓝图初始化整个知识库骨架，定位为技术/编程领域

## [2026-06-12] overview | LLM Wiki 综述
- 创建: [[wiki/overviews/LLM Wiki 综述]]
- 更新: CLAUDE.md (raw/assets/ 与 wiki/assets/ 分离), index.md
- 摘要: 将所有讨论成果整理成综述页面，新增 raw/assets/ 目录，形成完整的 wiki 结构说明

## [2026-06-12] ingest | CLAUDE.md (方法论提取)
- 创建: [[wiki/concepts/LLM Wiki]], [[wiki/concepts/RAG]], [[wiki/comparisons/LLM Wiki vs RAG]], [[wiki/entities/Obsidian]]
- 更新: [[wiki/overviews/LLM Wiki 综述]], index.md
- 摘要: 从 CLAUDE.md 提取核心方法论，创建概念页和对比页，综述页精简为 Hub

## [2026-06-12] lint | 文件归位检查
- 移动: llm-wiki.md → raw/llm-wiki.md (根目录归档)
- 创建: [[wiki/sources/LLM Wiki 蓝图]] (源摘要页)
- 更新: CLAUDE.md, log.md, [[wiki/concepts/LLM Wiki]], index.md (全量引用更新)
- 摘要: 唯一不在位的文件 llm-wiki.md 归档至 raw/，所有引用修复

## [2026-06-15] ingest | AI 名词解释
- 创建: [[wiki/sources/AI 名词解释]] (源摘要页)
- 创建: [[wiki/overviews/AI 术语总览]] (改造为概览页，含 6 类术语速查表)
- 创建: [[wiki/concepts/AI 核心概念]], [[wiki/concepts/AI Agent]], [[wiki/concepts/AI 关键技术]], [[wiki/concepts/AI 协议与架构]], [[wiki/concepts/AI 应用模式]] (5 个分类聚合概念页)
- 创建: [[wiki/entities/AI Agent 开发框架]] (LangChain/CrewAI/AutoGen 对比)
- 更新: index.md (8 个新条目), [[wiki/concepts/RAG]] (交叉引用), [[wiki/overviews/LLM Wiki 综述]] (页面地图)
- 摘要: 摄入 AI 术语综合表，按"分类聚合"策略创建 1 概览 + 5 概念 + 1 实体 + 1 源，共 8 个新页面。概览页为术语速查入口，各分类页展开详解并形成交叉引用网络

## [2026-06-15] lint | 全库检查
- 结果: 零孤页 ✓, 零矛盾 ✓, 零过期 ✓, 模板完整 ✓
- 修复: 4 处交叉引用缺口补全, 2 处 status stub→draft
- 摘要: 14 页面全量检查通过。补全了 AI Agent 开发框架→AI 协议与架构、AI 关键技术→AI 协议与架构、AI Agent→AI 应用模式、AI 核心概念→AI 应用模式 四条双向链接
