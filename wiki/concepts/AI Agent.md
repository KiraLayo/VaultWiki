---
type: concept
title: "AI Agent"
aliases: ["AI 智能体", "智能体", "Agentic AI"]
topics: ["AI", "Agent", "LLM", "多智能体"]
status: draft
---

# AI Agent

> AI Agent（AI 智能体）及其相关概念体系。从单个 Agent 到多智能体系统，从反应型到自主型。

## 核心定义

**AI Agent** = LLM（大脑）+ 规划（Planning）+ 记忆（Memory）+ 工具使用（Tool Use）

它是一种能**自主感知环境、进行决策并执行动作**以实现特定目标的智能系统。

## 概念层次

```
Agentic AI（多 Agent 协作体系）
  └─ Agentic Workflow（协作框架）
      └─ 多智能体系统（Multi-Agent System）
          └─ AI Agent（单个智能体）
              ├─ 自主智能体（Autonomous Agent）  ← 高度自主
              ├─ 学习型智能体（Learning Agent）    ← 从经验优化
              └─ 反应型智能体（Simple Reflex Agent） ← 仅规则驱动
```

## 各概念详解

### AI Agent（AI 智能体）

基础单元。四个核心组件：
- **LLM**：提供推理和语言能力（"大脑"）
- **规划 (Planning)**：将复杂目标分解为可执行步骤
- **记忆 (Memory)**：短期（上下文窗口）+ 长期（外部存储/RAG）
- **工具使用 (Tool Use)**：调用外部 API、函数、数据库

### Agentic AI（代理型人工智能）

代表一种更高级的范式，强调由**多个专业 AI Agent 组成系统**，通过协作、动态任务分解和持久化记忆来实现更复杂的目标。

核心思想：不是让一个超级 Agent 做所有事，而是让一个**"团队"**协作。

### Agentic Workflow（智能体工作流）

一个结构化框架，用于指导单个或多个 AI Agent **如何协作完成复杂任务**。它定义了 Agent 行动的具体步骤和方法，是 Agentic AI 的操作手册。

### 多智能体系统（Multi-Agent System）

由多个相互交互的 AI Agent 组成的系统，每个 Agent 拥有**专长**，通过协作解决单个 Agent 难以处理的复杂问题。

代表框架：[[wiki/entities/AI Agent 开发框架|CrewAI]]、[[wiki/entities/AI Agent 开发框架|AutoGen]]。

### 自主智能体（Autonomous Agent）

具有高度自主性的 AI Agent，具备完整的 **"感知 → 规划 → 行动 → 学习 → 适应"** 闭环，无需人类持续指导即可完成任务。

代表项目：AutoGPT、BabyAGI。

### 反应型智能体（Simple Reflex Agent）

仅基于**当前感知**和预设的**"条件-动作"规则**做出反应的简单 Agent，不考虑历史信息。

> 类似于 if-this-then-that 模式，是最基础的 Agent 形态。

### 学习型智能体（Learning Agent）

具备从过往经验中**学习和优化**自身行为策略能力的 Agent。典型实现方式：通过强化学习训练。

代表应用：自动驾驶系统、游戏 AI（AlphaGo）。

## 关联

- **源文档**：[[wiki/sources/AI 名词解释]]
- **概览**：[[wiki/overviews/AI 术语总览]]
- **相关概念**：[[wiki/concepts/AI 核心概念]] — LLM 是 Agent 的大脑
- **相关概念**：[[wiki/concepts/AI 关键技术]] — Prompt Engineering、Function Calling 等是 Agent 的关键使能技术
- **相关概念**：[[wiki/concepts/AI 协议与架构]] — MCP、A2A 是 Agent 间通信的标准
- **相关实体**：[[wiki/entities/AI Agent 开发框架]] — LangChain、CrewAI、AutoGen
- **相关概念**：[[wiki/concepts/AI 应用模式]] — 数字员工是 Agent 的企业应用场景
- **相关概念**：[[wiki/concepts/LLM Wiki]] — LLM Wiki 本质上是一种 Agent 行为模式
