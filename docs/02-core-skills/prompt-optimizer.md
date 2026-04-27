# prompt-optimize — 提示词优化助手

> **一句话描述：** 基于任务场景，匹配合适的提示词框架。

---

## 核心理念

> "先判断任务，再选框架。不要为了显得专业而过度设计简单 prompt。"

**设计模式：**
- **Reviewer**：先判断用户现有 prompt 或任务描述的问题
- **Inversion**：信息不足时，先追问目标、受众、约束和格式
- **Generator**：基于选定框架生成优化后的 prompt

---

## 57 种框架速查表

### 简单任务（≤3 要素）

适用于快速简单场景，不需要复杂结构。

| 框架 | 核心要素 | 适用场景 |
|------|----------|----------|
| **APE** | Action, Perspective, Expectation | 快速指令型任务 |
| **ERA** | Expectation, Role, Action | 简单角色扮演 |
| **TAG** | Task, Goal, Request | 明确目标导向 |
| **RTF** | Role, Task, Format | 格式明确的简单任务 |
| **BAB** | Before, After, Bridge | 小改进/过渡 |
| **PEE** | Point, Evidence, Explanation | 简单论证 |
| **ELI5** | Explain Like I'm 5 | 简单解释 |

### 中等任务（4-5 要素）

适用于需要一定结构和深度的场景。

| 框架 | 核心要素 | 适用场景 |
|------|----------|----------|
| **RACE** | Role, Action, Context, Expectation | 对话型任务 |
| **CIDI** | Context, Instruction, Decode, Incentive | 工具使用型 |
| **SPEAR** | Situation, Problem, Empathy, Aspiration, Response | 情感共鸣型 |
| **SPAR** | Situation, Problem, Aspiration, Resolution | 问题解决型 |
| **FOCUS** | Facts, Order, Concerns, Upshot, Suggestion | 信息汇总型 |
| **SMART** | Specific, Measurable, Achievable, Relevant, Time-bound | 目标设定 |
| **GOPA** | Goal, Obstacle, Plan, Action | 规划型 |
| **ORID** | Objective, Reflective, Interpretive, Decisional | 引导讨论 |
| **CARE** | Context, Action, Result, Expectation | 结果导向 |
| **ROSE** | Role, Objective, Style, Execute | 执行型 |
| **PAUSE** | Problem, Aim, Understand, Solutions, Evaluate | 问题分析 |
| **TRACE** | Task, Request, Audience, Context, Execute | 全面覆盖 |
| **GRADE** | Goal, Resources, Action, Details, Evaluate | 资源规划 |
| **TRACI** | Topic, Role, Action, Context, Intent | 意图明确 |
| **RODES** | Role, Objective, Details, Examples, Style | 细节丰富 |

### 复杂任务（6+ 要素）

适用于需要深度分析、复杂推理或全面规划的场合。

| 框架 | 核心要素 | 适用场景 |
|------|----------|----------|
| **RACEF** | Role, Action, Context, Expectation, Format | 全面对话 |
| **CRISPE** | Context, Role, Instruction, Script, Parameters, Extras | 角色扮演详细版 |
| **SCAMPER** | Substitute, Combine, Adapt, Modify, Put to another use, Eliminate, Reverse | 创意发散 |
| **Six Thinking Hats** | 白帽信息、红帽情感、黑帽风险、黄帽价值、绿帽创意、蓝帽流程 | 结构化思考 |
| **ROSES** | Role, Objective, Style, Execute, Subject | 创作型 |
| **PROMPT** | Person, Role, Object, Market, Product, Taste | 营销内容 |
| **RISEN** | Role, Instructions, Steps, End goal, Narrowing | 详细指导 |
| **RASCEF** | Role, Analysis, Steps, Context, Exceptions, Format | 结构化流程 |
| **Atomic Prompting** | 原子化组件重组 | 高度定制 |

---

## 工作流

```
分析输入 → 匹配场景 → 加载框架 → 澄清歧义 → 生成优化 → 迭代呈现
    ↓          ↓           ↓           ↓           ↓           ↓
```

### Step 1: 分析输入

接收你的请求，可能是：
- 一个需要优化的原始 prompt
- 一个任务描述或需求
- 一个模糊的想法

### Step 2: 匹配场景与选择框架

根据任务复杂度和领域匹配最适合的框架。

**按复杂度选择：**
- 简单任务（≤3 要素）：用 APE、ERA、TAG 等
- 中等任务（4-5 要素）：用 RACE、CIDI、FOCUS 等
- 复杂任务（6+ 要素）：用 CRISPE、SCAMPER 等

**按领域选择：**
- 营销文案：BAB、SPEAR、Challenge-Solution-Benefit
- 决策分析：RICE、Pros and Cons、Six Thinking Hats
- 教育培训：Bloom's Taxonomy、ELI5、Socratic Method
- 产品开发：SCAMPER、HMW、CIDI
- AI 对话：COAST、ROSES、TRACE、RACE
- 图片生成：Atomic Prompting

### Step 3: 加载框架详情

选定框架后，从 `references/frameworks/` 目录读取对应的框架文件。

每个框架文件包含：
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

---

## 适用场景

- 你有一个现成的 prompt，想优化它
- 你有一个任务描述或模糊的想法，需要转化为高质量 prompt
- 你不确定该用什么框架来构建 prompt

## 不适用场景

- 只想快速润色一句话（不要过度设计）
- 复杂生产系统需要系统性重构（用 prompt-refactor）
- 简单问答不需要任何框架

---

## 如何选择正确的复杂度？

### 判断流程

```
问自己：这个任务需要几个核心要素？
 │
 ├─ ≤3 个要素 → 用简单框架（APE/ERA/TAG）
 │
 ├─ 4-5 个要素 → 用中等框架（RACE/CIDI/SPAR）
 │
 └─ 6+ 个要素 → 用复杂框架（CRISPE/SCAMPER）
```

### 快速判断问题

| 问题 | 答案 | 推荐复杂度 |
|------|------|------------|
| 需要多少个明确角色？ | 1 个 | 简单 |
| 需要多少个执行步骤？ | 1-2 步 | 简单 |
| 需要多少个约束条件？ | 0-1 个 | 简单 |
| 需要多少个评估维度？ | 2-3 个 | 中等 |
| 需要多少个示例？ | 2-3 个 | 中等 |
| 需要全面规划？ | 是 | 复杂 |

### 一句话原则

> 如果你能用一句话说清楚"让 AI 做什么、怎么做"，就用简单框架。
> 如果需要"先分析情况，再分步骤执行，最后评估结果"，用中等框架。
> 如果涉及"角色扮演 + 复杂推理 + 多轮迭代"，用复杂框架。

---

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

---

## 注意事项

- 不要一上来就套框架，先判断任务是否真的需要复杂框架
- 简单任务不要过度设计
- 如果只想快速润色一句 prompt，不需要输出一整套长模板
- 如果目标、受众、输出格式不清楚，会先补问最小必要问题
- 理解**为什么**选这个框架，比堆很多框架名更重要

---

## 继续阅读

- [prompt-craft — 提示词修炼](./prompt-craft.md)
- [prompt-refactor — 提示词重构](./prompt-refactor.md)
