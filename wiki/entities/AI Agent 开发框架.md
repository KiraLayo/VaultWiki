---
type: entity
entity_type: tool
title: "AI Agent 开发框架"
aliases: ["Agent 框架", "Agent Framework"]
topics: ["AI", "Agent", "框架", "LLM"]
links:
  langchain: "https://www.langchain.com/"
  crewhai: "https://www.crewai.com/"
  autogen: "https://microsoft.github.io/autogen/"
---

# AI Agent 开发框架

> 三个主流的 AI Agent 开发框架，代表了构建 LLM 驱动智能体的不同设计哲学。

## 框架对比

| 维度 | LangChain | CrewAI | AutoGen |
|------|-----------|--------|---------|
| **定位** | 通用 LLM 应用框架 | 团队协作模拟 | 对话式多智能体 |
| **核心理念** | 模块化组件（乐高式） | 角色 + 任务 = 团队 | Agent 间自然语言对话 |
| **编排方式** | Chain/Graph 显式定义 | 角色分配 → 任务委派 | 对话驱动自发协商 |
| **适合场景** | 通用 LLM 应用、原型 | 模拟团队流程、内容生产 | 研究探索、复杂协商 |
| **开发方** | LangChain Inc. | CrewAI | 微软 |

## LangChain

流行的 AI Agent 开发框架，提供构建 LLM 应用所需的**模块化组件**：

- **模型 (Models)**：统一接口调用各种 LLM
- **提示词 (Prompts)**：模板化提示词管理
- **记忆 (Memory)**：对话历史持久化
- **工具 (Tools)**：函数调用和外部 API 集成
- **链 (Chains)**：将上述组件串联成工作流
- **图 (LangGraph)**：有状态的、带分支循环的复杂 Agent 工作流

## CrewAI

专注于**模拟人类团队协作**的多智能体框架。核心理念：

- **角色 (Role)**：定义 Agent 的身份和专长
- **目标 (Goal)**：定义 Agent 需要达成的结果
- **任务 (Task)**：具体的工作单元
- **流程 (Process)**：任务执行的顺序和依赖

设计哲学：像管理团队一样管理 Agent。

## AutoGen

由微软推出的**对话式多智能体编程框架**，支持 Agent 间通过自然语言对话进行协商和协作。

核心特色：
- Agent 之间通过**消息传递**沟通
- 支持**人机协作**循环（Human-in-the-loop）
- 灵活的**对话模式**（双人对话、群组对话、嵌套对话）

## 关联

- **源文档**：[[wiki/sources/AI 名词解释]]
- **概览**：[[wiki/overviews/AI 术语总览]]
- **相关概念**：[[wiki/concepts/AI Agent]] — 这些框架是实现 Agent 的工程工具
- **相关概念**：[[wiki/concepts/AI 关键技术]] — Function Calling 是框架的基础能力
- **相关概念**：[[wiki/concepts/AI 协议与架构]] — 框架是实现 MCP/A2A 协议的工程载体
