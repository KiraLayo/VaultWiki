---
type: concept
title: "AI 核心概念"
aliases: ["AI 基础概念", "AI Core Concepts"]
topics: ["AI", "ML", "DL", "LLM", "AGI"]
status: draft
---

# AI 核心概念

> AI 领域最基础的六个核心概念，从通用 AI 到大语言模型，构成理解整个领域的地基。

## 概念层次

```
通用人工智能 (AGI)           ← 终极目标
    └─ 人工智能 (AI)         ← 总领域
        └─ 机器学习 (ML)     ← 核心方法论
            └─ 深度学习 (DL) ← 当前主流技术
                └─ 大语言模型 (LLM) ← 当前最热应用
        └─ 生成式 AI          ← 内容创造分支
```

## 各概念详解

### 人工智能 (Artificial Intelligence, AI)

通过计算机程序模拟和实现人类智能的技术领域。核心目标是让机器能**自主地感知环境、做出决策并与环境交互**。

AI 是一个总括性术语，涵盖了从简单的规则系统到复杂的深度学习模型的所有技术。

### 机器学习 (Machine Learning, ML)

人工智能的子领域，研究如何让计算机**从数据中自动学习和改进性能**，而无需明确编程。

与传统编程的关键区别：
- **传统编程**：人写规则 → 计算机执行
- **机器学习**：人给数据 + 目标 → 计算机自己找规则

### 深度学习 (Deep Learning, DL)

机器学习的一个分支，使用**多层神经网络**（如 Transformer）来处理复杂模式。是当前大语言模型的核心技术。

关键特征：层数深、参数多、能从原始数据中自动提取特征。

### 大语言模型 (Large Language Model, LLM)

基于海量文本数据预训练的大型神经网络模型，具备强大的**语言理解、生成和推理**能力。代表模型：GPT-4、Claude、Gemini 等。

LLM 常被视为 AI Agent 的"大脑"——提供核心推理能力，但需要配合规划、记忆、工具使用等组件才能成为完整的 Agent。

### 生成式 AI (Generative AI)

专注于**创造新内容**（文本、图像、代码、音频）的 AI 系统。它被视为 AI Agent 的前身：主要关注内容生成，缺乏主动执行任务的能力。

典型产品：ChatGPT、Midjourney、DALL-E、Sora。

### 通用人工智能 (Artificial General Intelligence, AGI)

人工智能研究的**终极目标**：具备与人类同等水平通用智能的系统，能理解、学习并应用知识解决**各种**问题（而非仅限特定领域）。

> 当前所有 AI 系统均为"狭义 AI"（Narrow AI），AGI 尚未实现。

## 关联

- **源文档**：[[wiki/sources/AI 名词解释]]
- **概览**：[[wiki/overviews/AI 术语总览]]
- **相关概念**：[[wiki/concepts/AI Agent]] — LLM 是 Agent 的核心组件
- **相关概念**：[[wiki/concepts/RAG]] — LLM 的关键增强技术
- **相关概念**：[[wiki/concepts/AI 应用模式]] — LLM 和生成式 AI 是 Copilot/Vibe Coding 的技术基础
