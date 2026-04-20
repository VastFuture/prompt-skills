# Prompt Optimizer 使用指南

## 简介

Prompt Optimizer 是一个提示词优化助手。它根据你的具体任务场景，从 57 种提示词框架中匹配合适的框架，帮你生成更清晰、更可执行的 prompt。

## 适用场景

- 你有一个现成的 prompt，想优化它
- 你有一个任务描述或模糊的想法，需要转化为高质量 prompt
- 你不确定该用什么框架来构建 prompt

## 核心工作流

### Step 1: 分析输入

接收你的请求，可能是：
- 一个需要优化的原始 prompt
- 一个任务描述或需求
- 一个模糊的想法

### Step 2: 匹配场景与选择框架

根据任务的复杂度和领域，从框架库中推荐最合适的框架。

**按复杂度推荐：**

| 复杂度 | 推荐框架 |
|--------|----------|
| 简单（≤3 个要素） | APE, ERA, TAG, RTF, BAB, PEE, ELI5 |
| 中等（4-5 个要素） | RACE, CIDI, SPEAR, SPAR, FOCUS, SMART, GOPA, ORID, CARE, ROSE, PAUSE, TRACE, GRADE, TRACI, RODES |
| 复杂（6+ 个要素） | RACEF, CRISPE, SCAMPER, Six Thinking Hats, ROSES, PROMPT, RISEN, RASCEF, Atomic Prompting |

**按领域推荐：**

| 领域 | 推荐框架 |
|------|----------|
| 营销文案 | BAB, SPEAR, Challenge-Solution-Benefit, BLOG, PROMPT, RHODES |
| 决策分析 | RICE, Pros and Cons, Six Thinking Hats, Tree of Thought, PAUSE, What If |
| 教育培训 | Bloom's Taxonomy, ELI5, Socratic Method, PEE, Hamburger Model |
| 产品开发 | SCAMPER, HMW, CIDI, RELIC, 3Cs Model |
| AI 对话/助手 | COAST, ROSES, TRACE, RACE, RASCEF |
| 写作创作 | BLOG, 4S Method, Hamburger Model, Few-shot, RHODES, Chain of Destiny |
| 图片生成 | Atomic Prompting |
| 快速简单任务 | Zero-shot, ERA, TAG, APE, RTF |
| 复杂推理 | Chain of Thought, Tree of Thought |

### Step 3: 加载框架详情

选定框架后，从 `references/frameworks/` 目录读取对应的框架文件，包含：
- 框架概述与组成要素
- 每个要素的详细解释
- 优缺点分析
- 最佳实践示例

### Step 4: 澄清歧义

在生成最终 prompt 前，会与你确认：
1. **目标**：期望的输出结果是什么？
2. **受众**：谁会接收 AI 的回复？
3. **上下文**：是否有足够的背景信息？
4. **格式**：是否有特定的输出格式要求？
5. **约束**：是否有限制条件？

### Step 5: 生成优化 Prompt

根据选定框架生成最终 prompt：
1. 按框架组件结构化 prompt
2. 整合所有已确认的信息
3. 确保清晰性和具体性
4. 包含必要的示例和约束

### Step 6: 展示与迭代

输出优化后的 prompt，并附上：
- 选用的框架名称及选择原因
- 每个框架要素的具体应用说明
- 潜在的改进建议

## 快速选框架参考

| 你想做什么 | 推荐框架 |
|------------|----------|
| 写一个简单 prompt | APE, ERA, TAG |
| 说服/推销 | BAB, SPEAR, Challenge-Solution-Benefit |
| 分析/决策 | RICE, Pros and Cons, Chain of Thought |
| 教学/解释 | ELI5, Bloom's Taxonomy, Socratic Method |
| 创意发散 | SCAMPER, HMW, SPARK, Imagine |
| 结构化写作 | BLOG, 4S Method, Hamburger Model |
| 逐步推理 | Chain of Thought, Tree of Thought |
| 生成图片 | Atomic Prompting |
| 详细计划 | RISEN, RASCEF, CRISPE |

## 注意事项

- 不要一上来就套框架，先判断任务是否真的需要复杂框架
- 简单任务不要过度设计
- 如果只想快速润色一句 prompt，不需要输出一整套长模板
- 如果目标、受众、输出格式不清楚，会先补问最小必要问题
- 理解为什么选这个框架，比堆很多框架名更重要

## 文件结构

```
prompt-optimizer/
├── SKILL.md                          # 核心指令集
├── LICENSE.txt                       # 许可证
└── references/
    ├── Frameworks_Summary.md          # 57 种框架概览
    └── frameworks/                    # 各框架详细文档
        ├── 01_RACEF_Framework.md
        ├── 02_CRISPE_Framework.md
        ├── ...
        └── 57_RASCEF_Framework.md
```
