---
name: prompt-principles
description: Core principles for writing effective LLM prompts - goal clarity, constraint flow, iteration, and honest communication. Combines universal principles with Anthropic engineer best practices. Use when writing, improving, or teaching prompt engineering. Trigger phrases: "优秀提示词", "提示词技巧", "提示词原则", "Claude工程师", "目标明确", "约束流", "工作流"
metadata:
  author: woodgaya@gmail.com
  version: 2.0.0
---

# Prompt Principles

## Overview

A unified guide combining universal prompt principles with Anthropic engineers' field-tested best practices. Covers everything from foundational rules to day-to-day workflow techniques.

## Part 1: Universal Principles

### Principle 1 — Everything Describable Is Solvable
Anything that can be described in characters can be solved by an LLM. The quality of your prompt determines the quality of your output.

### Principle 2 — Goal Clarity + Constraint Flow
The two most critical factors in any prompt:
- **Goal**: Explicit, clear, achievable
- **Constraints**: Well-defined input/output format, style, length, boundaries

### Three Key Focus Areas

| 维度 | 说明 | 示例 |
|------|------|------|
| **Goal Clarity** | 目标清晰 | 明确告诉 AI 要做什么，而不是模糊描述 |
| **Constraint Flow** | 约束明确 | 定义输入格式、输出格式、边界条件 |
| **Workflow Logic** | 工作流逻辑 | 把任务拆成可执行的步骤序列 |

## Part 2: Anthropic Engineer Best Practices

### 1. Be Direct — No Fluff
Talk to the model like a capable colleague. Skip the role-play preamble.

| ❌ Indirect | ✅ Direct |
|------------|---------|
| "You are a senior PM with 20 years of experience..." | "Write a product description for X" |
| "If you have time, please help me analyze..." | "Analyze this user feedback, find 3 core issues" |
| "As an AI language model, I need you to..." | "Translate this paragraph to English" |

### 2. Iterate — Don't Perfect on First Try
Prompt engineering is a trial-and-error process. Test edge cases: empty input, unusual data, boundary conditions. When output is wrong, ask: "Why did you get this wrong? Can you help fix my prompt?"

### 3. Be Honest — Don't Deceive the Model
Don't pretend you're giving a quiz or running a test. Tell the model your actual goal. Modern models are powerful enough — don't coax or trick them.

### 4. Don't Over-Use Role-Play
Models don't need to be "a senior lawyer" or "a patient teacher." They need clear task descriptions. Use roles only when they genuinely inform tone or expertise.

### 5. Trust the Model's Capability
Give the model the real paper, not a simplified version. Let it handle complexity. Verify facts and math, but don't over-simplify instructions.

### 6. Know When to Give Up
Some tasks: every adjustment pushes the result further from the goal. Better to wait for the next model than spend months on an unsolvable prompt.

## Quick Checklist

- [ ] 目标是否明确、具体、可达成？
- [ ] 约束条件是否清晰、无歧义？
- [ ] 执行步骤是否有逻辑、可操作？
- [ ] 提示词是直接说需求，还是在绕弯子？
- [ ] 我测试过边界情况吗？
- [ ] 我是否过度角色扮演了？
- [ ] 我对 AI 诚实、不欺骗吗？

## Usage Examples

**Example 1**: User asks for a prompt to extract email addresses.
→ AI defines goal, sets input/output constraints, designs workflow (parse → extract → validate).

**Example 2**: User asks "my prompt isn't working well, how to improve?"
→ AI applies principles: clarify task, test edge cases, avoid role-play, iterate.

**Example 3**: User asks "what are the key rules for writing prompts?"
→ AI explains goal clarity, constraint design, workflow structure, and Anthropic best practices.
