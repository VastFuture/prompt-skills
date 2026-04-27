# Prompt Skills

AI Agent 提示词工程技能集。从零构建、框架优化到持续重构，覆盖提示词全生命周期。

## 技能列表

### [prompt-craft](./prompt-craft/) — 提示词修炼

从零构建高质量、生产级提示词。通过极致压缩（语义点亮）与结构化定义，消除语义空洞，实现精准意图对齐与泛化能力。

**核心理念：** 得其意而忘其言。少描述，多定义。

- 7 大修炼维度：哲学、压缩、结构、注意力、角色、金阶技巧、格式适配
- 标准化构建工作流：理解本质 → 选择适配 → 分配压缩包 → 构建骨架 → 填充核心词 → 压缩脱水 → 检查验证
- 多模型格式适配（GPT / Claude / Gemini）

### [prompt-optimize](./prompt-optimize/) — 提示词优化

基于具体任务场景，匹配合适的提示词框架，生成更清晰、更可执行的 prompt。

**核心理念：** 先判断任务，再选框架。不要为了显得专业而过度设计简单 prompt。

- 内置 57 种提示词框架（CoT、CRISPE、RACEF、SCAMPER 等）
- 按复杂度和领域双维度推荐框架
- 6 步标准工作流：分析输入 → 匹配框架 → 加载详情 → 澄清歧义 → 生成优化 → 迭代改进

### [prompt-refactor](./prompt-refactor/) — 提示词重构

对现有生产级提示词进行系统性重构，解决规则碎片化、输出不稳定、AI 模板腔等退化问题。

**核心理念：** 先看全稿，再动局部。先收骨架，再改句子。少补丁，多主轴。

- 系统性问题诊断：重复、漂移、解释层过厚、边界泄漏、模板腔
- 结构化重构流程：通读全稿 → 标记问题 → 收骨架 → 改文案
- 5 条改写铁律与 Template Smell 检查清单

### [skill-optimize](./skill-optimize/) — 技能优化

优化和重构现有 skill 的结构、触发描述、工作流和资源组织方式。

**核心理念：** 先审查，再规划，最后在确认后修改。

- 5 步标准流程：确定范围 → 审查 skill → 输出优化计划 → 确认后实施 → 校验结果
- 审查清单：触发匹配、模式判断、工作流可执行性、资源组织
- 默认先审查再确认，不直接改文件

## 技能关系

```
从零构建 ──→ prompt-craft（修炼）
              ↓
框架优化 ──→ prompt-optimize（框架匹配与生成）
              ↓
持续迭代 ──→ prompt-refactor（重构）
              ↓
技能质量 ──→ skill-optimize（skill 结构优化）
              ↓
          回到 craft 重新审视底层逻辑
```

## 提示词工程方法论

> 来源：[VastFuture/usingSkills](https://github.com/VastFuture/usingSkills)
> 适用场景：不知道从哪写 → 写卡住了 → 写完了想改

### 模板型 — 不知道从哪开始写时用

| 技能 | 说明 | 什么时候用 |
|------|------|-----------|
| [prompt-template](./prompt-template/) | 六要素模板：Role / Background / Task / Requirements / Example / Reflection | 通用场景，套进去就有完整提示词 |
| [prompt-role](./prompt-role/) | CRISPE 框架（v1.4），最成熟的角色扮演模板 | 需要 AI 扮演某个角色时 |

### 原则型 — 卡在某个点，想找指导时用

| 技能 | 说明 | 什么时候用 |
|------|------|-----------|
| [prompt-principles](./prompt-principles/) | 通用法则 + Anthropic工程师实践（目标清晰 + 直接沟通 + 迭代 + 诚实） | 提示词目标模糊、过于复杂、效果不稳定 |

### 质检型 — 写完想优化时用

| 技能 | 说明 | 什么时候用 |
|------|------|-----------|
| [prompt-score](./prompt-score/) | 通用10维评分（1-10分）+ O1/O3-mini专属质检 | 想知道提示词哪里需要改、怎么改，或检查推理模型适配性 |-mini 推理模型提示词质检 | 给 O1/O3-mini 写的提示词，需要诊断适配性 |

### 平台型 — 在 Coze 平台写机器人时用

| 技能 | 说明 | 什么时候用 |
|------|------|-----------|
| [prompt-coze](./prompt-coze/) | 含输入/输出变量定义与 JSON 对齐 | 在 Coze.cn 搭智能体，卡在变量或输出格式上 |

> AI 思考与推理框架已迁移至独立仓库：[VastFuture/vastfuture-ai-thinking-frameworks](https://github.com/VastFuture/vastfuture-ai-thinking-frameworks)

## 文件约定

- **核心技能**（prompt-craft 等）：每个技能包含 `SKILL.md`、`REFERENCE.md`、`EXAMPLES.md` 及 `references/` 目录
- **提示词方法论**（根目录下的独立文件夹）：每个技能为一个独立文件夹，内含 `SKILL.md` 核心指令集

## 文档

详细的使用指南见 [docs/](./docs/) 目录。

## License

MIT
