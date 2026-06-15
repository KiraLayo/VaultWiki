---
type: concept
title: "AI 关键技术"
aliases: ["AI 关键术语", "AI Key Technologies"]
topics: ["AI", "LLM", "RAG", "Prompt", "RL"]
status: draft
---

# AI 关键技术

> 构建和使用现代 AI 系统（特别是 LLM 和 Agent）所涉及的核心技术术语。

## 技术全景

```
┌─ 输入层 ─────────────────────────────────────┐
│  提示词工程 (Prompt Engineering)               │
│  上下文工程 (Context Engineering)              │
│  上下文窗口 (Context Window)                   │
├─ 增强层 ─────────────────────────────────────┐
│  检索增强生成 (RAG)                           │
│  函数调用 (Function Calling)                  │
│  知识图谱 (Knowledge Graph)                   │
├─ 推理层 ─────────────────────────────────────┐
│  思维链 (Chain of Thought)                   │
│  强化学习 (Reinforcement Learning)            │
├─ 感知层 ─────────────────────────────────────┐
│  计算机视觉 (Computer Vision)                 │
└──────────────────────────────────────────────┘
```

## 各技术详解

### 提示词工程 (Prompt Engineering)

设计和优化输入给 AI 模型的指令（提示词），以引导模型生成期望输出的技术。

核心实践：角色设定、Few-shot 示例、结构化输出约束、Chain of Thought 嵌入。

### 上下文工程 (Context Engineering)

系统性设计和管理 AI 运行所需的**所有情境信息**（用户目标、对话历史、业务规则、外部数据等）的工程实践。被认为是构建高质量 Agent 应用的**核心能力**。

> 提示词工程关注"说什么"，上下文工程关注"给什么信息环境"。

### 上下文窗口 (Context Window)

AI 模型一次能处理的**最大 token 数**，决定了它能"记住"的信息量上限。

- 早期模型：4K–8K tokens
- 当前主流：128K–200K tokens（GPT-4o、Claude 3.5）
- 前沿模型：1M+ tokens（Gemini 1.5 Pro）

### 检索增强生成 (RAG)

> 已有独立页面：[[wiki/concepts/RAG]]

让 AI 模型在生成回答前，先从外部知识库检索相关信息，以提升答案的准确性和时效性，减少"幻觉"。

核心流程：查询 → 检索相关文档片段 → 将片段注入上下文 → 生成答案。

### 函数调用 (Function Calling)

LLM 能调用外部 API 或函数的能力，使 AI 从"只能说"进化到"能做事"。典型用例：查天气、订机票、操作数据库、调用其他微服务。

这是 AI Agent 的"工具使用"能力的基础实现。

### 思维链 (Chain of Thought, CoT)

一种引导模型进行**逐步推理**的技术，让模型展示其思考过程，以提升解决复杂问题的能力。

- **Zero-shot CoT**：加一句"Let's think step by step"
- **Few-shot CoT**：给模型展示带推理步骤的示例

### 计算机视觉 (Computer Vision)

使计算机能够从图像和视频中理解和处理视觉信息的技术。让 AI Agent 能"看见"世界。

典型任务：图像分类、目标检测、语义分割、OCR。

### 强化学习 (Reinforcement Learning, RL)

一种机器学习方法，智能体通过与环境**试错交互**，根据奖励信号学习最优行为策略。

核心要素：Agent（智能体）、Environment（环境）、Action（动作）、State（状态）、Reward（奖励）。

关键应用：RLHF（人类反馈强化学习）—— 当前对齐 LLM 的核心技术。

### 知识图谱 (Knowledge Graph, KG)

一种用**图结构**表示实体及其之间关系的知识库。为 AI Agent 提供结构化的常识和背景知识，支持更复杂的推理。

三元组形式：(实体, 关系, 实体) —— 如 (姚明, 效力于, 火箭队)。

## 关联

- **源文档**：[[wiki/sources/AI 名词解释]]
- **概览**：[[wiki/overviews/AI 术语总览]]
- **已有深度页面**：[[wiki/concepts/RAG]]
- **相关概念**：[[wiki/concepts/AI Agent]] — 这些技术是 Agent 的能力基础
- **相关概念**：[[wiki/concepts/AI 协议与架构]] — Function Calling 是 MCP 的基础能力
- **相关概念**：[[wiki/concepts/LLM Wiki]] — LLM Wiki 整合了 RAG 的思路，但采用了不同的持久化策略
- **对比**：[[wiki/comparisons/LLM Wiki vs RAG]]
