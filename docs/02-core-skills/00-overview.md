# Core Skills 核心技能总览

本文档介绍 `prompt-skills` 项目中的 4 个核心技能，它们构成了提示词工程的完整工具链。

---

## 四大核心技能

| 技能 | 定位 | 核心能力 | 典型场景 |
|------|------|----------|----------|
| **prompt-craft** | 从零构建 | 极致压缩 + 结构化定义 | 从空白开始构建生产级 Agent |
| **prompt-optimize** | 框架匹配 | 57 种框架智能匹配 | 任务场景匹配 + 框架生成 |
| **prompt-refactor** | 系统重构 | 5 步重构法 + 铁律改写 | 修复"越写越碎"的生产 prompt |
| **skill-optimize** | 技能优化 | 审查 + 计划 + 确认 + 修改 | 优化现有 skill 的结构和设计 |

---

## 关系图

```
                    ┌─────────────────┐
                    │   你有一个任务   │
                    └────────┬────────┘
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
     ┌────────────┐  ┌─────────────┐  ┌────────────┐
     │ prompt-    │  │ prompt-     │  │ skill-     │
     │ craft      │  │ refactor    │  │ optimizer  │
     │ 从零构建   │  │ 系统重构    │  │ 技能优化   │
     └────────────┘  └─────────────┘  └────────────┘
              │              │              │
              ▼              ▼              ▼
     从空白开始        已有但有问题      检查现有 skill
     构建新 prompt     修复生产 prompt   优化结构设计
              │              │              │
              └──────────────┴──────────────┘
                             │
                    ┌────────▼────────┐
                    │ prompt-optimize │
                    │   框架匹配      │
                    └─────────────────┘
```

---

## 何时使用哪个技能

### prompt-craft（提示词修炼）

**使用场景：**
- 从零开始构建复杂的 Agent prompt
- 需要极高的执行稳定性和泛化能力
- 核心逻辑需要深度泛化，生产级应用

**不使用场景：**
- 已有 prompt 的局部修补（用 prompt-refactor）
- 简单一次性问答
- 纯文案润色

---

### prompt-optimize（提示词优化助手）

**使用场景：**
- 你有一个现成的 prompt，想优化它
- 有一个任务描述或模糊想法，需要转化为高质量 prompt
- 不确定该用什么框架来构建 prompt

**不使用场景：**
- 只想快速润色一句话（过度设计）
- 复杂生产系统需要系统性重构（用 prompt-refactor）

---

### prompt-refactor（提示词重构）

**使用场景：**
- prompt 越写越长，规则越来越碎
- 同一类约束散落在多个章节，互相打架
- 输出有明显 AI 模板腔
- 每修一个 case 就补一条规则
- 模型把内部判断逻辑说给用户听

**不使用场景：**
- 只改一个局部业务规则（结构本身稳定）
- 单纯补一个 few-shot（不涉及结构收敛）
- 纯文案润色

---

### skill-optimize（技能优化器）

**使用场景：**
- 想检查和改进现有 skill 的质量
- skill 触发不准确、工作流混乱
- 内容过于臃肿，需要拆分重组
- 需要对 skill 进行结构化审查

**不使用场景：**
- 从零创建一个新 skill（没有现有目标）
- 只需要写一个 prompt（用 prompt-craft 或 prompt-optimize）

---

## 快速选择指南

```
你的任务是什么？
│
├─ 创建新的 Agent prompt ──────→ prompt-craft
│
├─ 优化现有 prompt ───────────→ prompt-optimize
│   │
│   └─ prompt 已经很乱很碎？───→ prompt-refactor
│
└─ 优化现有 skill ─────────────→ skill-optimize
```

---

## 技能设计模式对照

每个技能采用不同的设计模式组合：

| 技能 | 主要模式 | 次要模式 | 特点 |
|------|----------|----------|------|
| prompt-craft | Generator | - | 从空白生成，强调压缩与定义 |
| prompt-optimize | Reviewer + Inversion + Generator | - | 先判断、再追问、后生成 |
| prompt-refactor | Reviewer | - | 先通读全稿，再系统性重构 |
| skill-optimize | Reviewer + Inversion（轻度 Generator） | - | 先审查、再出计划、确认后修改 |

---

## 继续阅读

- [prompt-craft — 提示词修炼](./prompt-craft.md)
- [prompt-optimize — 提示词优化助手](./prompt-optimize.md)
- [prompt-refactor — 提示词重构](./prompt-refactor.md)
- [skill-optimize — 技能优化器](./skill-optimize.md)
