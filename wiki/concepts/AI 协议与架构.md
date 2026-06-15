---
type: concept
title: "AI 协议与架构"
aliases: ["MCP", "A2A", "模型上下文协议", "智能体间通信协议"]
topics: ["AI", "协议", "Agent", "MCP", "互操作"]
status: draft
---

# AI 协议与架构

> 定义 AI 系统与外部世界、以及 AI Agent 之间如何通信的开放标准。

## 两大核心协议

### 模型上下文协议 (Model Context Protocol, MCP)

一种开放标准，旨在实现 AI 模型与外部工具、数据源之间的**"即插即用"式连接**。

> 类比：MCP 之于 AI 应用，就像 USB 之于外设 —— 统一的连接标准。

核心价值：
- **标准化接口**：不同的工具/数据源通过同一协议暴露给 LLM
- **解耦**：LLM 应用不需要为每个数据源写定制集成
- **生态**：类似插件市场，工具可以一次开发、多模型复用

### 智能体间通信协议 (Agent-to-Agent, A2A)

一种新兴协议，用于定义**不同 AI Agent 之间**进行直接协作和通信的通用语言。

> 类比：如果 MCP 是 AI 的"USB"，A2A 就是 AI 之间的"TCP/IP"。

核心价值：
- **跨系统协作**：不同厂商、不同框架的 Agent 能互通
- **大规模编排**：实现跨组织的 Agent 协同工作
- **标准化对话**：定义 Agent 间消息的通用格式和语义

## 协议层次

```
A2A（Agent ↔ Agent 通信层）
  └─ MCP（Agent ↔ 工具/数据源 连接层）
      └─ LLM（核心推理引擎）
```

## 关联

- **源文档**：[[wiki/sources/AI 名词解释]]
- **概览**：[[wiki/overviews/AI 术语总览]]
- **相关概念**：[[wiki/concepts/AI Agent]] — 协议是 Agent 生态的基础设施
- **相关概念**：[[wiki/concepts/AI 关键技术]] — Function Calling 是 MCP 的基础能力
- **相关实体**：[[wiki/entities/AI Agent 开发框架]] — 框架是实现协议的工程载体
