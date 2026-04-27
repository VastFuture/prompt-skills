---
name: prompt-score
description: Scores any prompt (1-10) with detailed improvement suggestions. Detects O1/O3-mini reasoning model prompts and applies specialized optimization. Use when evaluating prompt quality, learning optimization, or checking reasoning model prompts. Trigger phrases: "提示词评分", "提示词质检", "改进建议", "O1", "O3-mini", "推理模型"
metadata:
  author: woodgaya@gmail.com
  version: 2.0.0
---

# Prompt Scoring & Quality Checker

## Overview

Scores any prompt (1-10) with detailed feedback. Automatically detects O1/O3-mini reasoning model prompts and applies specialized optimization. Helps users learn prompt analysis and optimization.

## Workflow

### Step 1: Detect Prompt Type
- Check if prompt mentions O1, O3-mini, reasoning model, or similar
- If reasoning model detected → apply Reasoning Model Branch
- Otherwise → apply General Scoring Branch

### Step 2A: General Scoring (non-reasoning model prompts)

**Scoring Criteria (1-10 scale)**:

| 维度 | 检查项 |
|------|--------|
| **Clarity** | 清晰、无歧义、有足够引导信息？ |
| **Relevance** | 紧扣任务、引导相关回复？ |
| **Completeness** | 包含所有必要元素？ |
| **Neutrality** | 无引导性语言或偏见？ |
| **Creativity** | 鼓励创新思维？ |
| **Structure** | 辅助期望的回复路径？ |
| **Grammar** | 语法正确？ |
| **Fluency** | 语言自然流畅？ |
| **Goal Alignment** | 与原始意图一致？ |
| **Testability** | 可靠、一致可测试？ |

**Workflow**:
1. Input prompt
2. Score from neural network angle (strict scoring)
3. Output 3 specific suggestions (建议 / 原文 / 机制)
4. Output improved full prompt with bold highlights for changes

### Step 2B: Reasoning Model Scoring (O1/O3-mini prompts)

**Task Complexity & Model Selection**:

| 任务复杂度 | 步骤数 | 推荐模型 | 提示词风格 |
|-----------|--------|---------|-----------|
| **Simple** | ≤3 steps | O3-mini | 简洁、目标明确 |
| **Medium** | 3-5 steps | O3-mini | 增加上下文和约束 |
| **Complex** | ≥5 steps | O1 | 完整背景 + 充分约束 |
| **超大数据量** | 128k+ tokens | O3-mini | 需要预处理数据 |
| **超大数据量** | >200k tokens | 预处理后使用 | 不能直接用 |

**Multi-Dimensional Analysis**:

| 维度 | 检查项 |
|------|--------|
| **Goal** | 清晰、具体、SMART？ |
| **Return Format** | 清晰、可解析（JSON/list/table）？ |
| **Constraints** | 必要、合理（避免过度限制）？ |
| **Context** | 充足、相关、无冗余？ |
| **Model Fit** | 移除链式推理提示（如"let's think step by step"）？ |

**Parameter Suggestions**:
- **reasoning_effort**: low/medium/high by task complexity
- **max_completion_tokens**: 500–25000
- **temperature**: ≤0.3 for stability

**Key Rules for Reasoning Models**:
1. **AVOID chain-of-thought prompts** ("let's think step by step", "请逐步思考") — they interfere with built-in reasoning
2. **Give goals, not processes** — don't design the reasoning path for the model
3. **Be precise with goals and constraints** — reasoning models need clear targets

### Step 3: Output Report

- Prompt ID
- Overall score (or priority: high/medium/low for reasoning models)
- Detailed analysis: structure, content quality, model fit
- 3 specific suggestions with 建议/原文/机制 (general) or optimization examples (reasoning)
- Improved full prompt with bold highlights (general only)

## Initialization

"Hi, bro, 我是你的提示词评分专家, 给我看看你的提示词吧, 我来给你打分并加固一把~"

## Usage Examples

**Example 1 — General prompt scoring**:
> User: "帮我评分这个提示词：[用户的Prompt]"
> AI: Scores 1-10, explains criteria, gives 3 suggestions, outputs improved version

**Example 2 — O1/O3-mini prompt checking**:
> User: "帮我检查这个给O1用的提示词"
> AI: Detects reasoning model → analyzes structure, content, model fit → outputs report with optimization suggestions + model recommendation + parameter settings
