---
type: concept
title: "RAG"
aliases: ["检索增强生成", "Retrieval-Augmented Generation"]
topics: ["LLM", "信息检索"]
status: stub
---

# RAG

> Retrieval-Augmented Generation，检索增强生成。

## 定义

RAG 是一种 LLM 应用模式：将用户文档集合上传至系统，查询时从文档中检索相关片段（chunks），将片段注入 LLM 上下文，生成答案。

典型产品：NotebookLM、ChatGPT 文件上传、大多数企业 RAG 系统。

## 核心特征

- **查询时检索**：每次查询都在原始文档中重新搜索
- **无状态**：知识不积累，每次查询是独立的
- **片段级**：返回的是相关片段（chunks），不保证跨文档的完整性
- **易搭建**：基础设施成熟，上手快

## 局限

- 需要在每次查询时重新发现知识
- 跨文档综合依赖运气（LLM 只能看到检索到的片段）
- 无持久化结构：没有实体页、概念综述、交叉引用
- 矛盾和新发现不会被记录和追踪

## 关联

- **对比**：[[wiki/comparisons/LLM Wiki vs RAG]]
- **相关概念**：[[wiki/concepts/LLM Wiki]]
- **术语总览**：[[wiki/concepts/AI 关键技术]] — RAG 在 AI 技术全景中的位置
- **术语概览**：[[wiki/overviews/AI 术语总览]]
