# Skill Optimizer 使用指南

## 简介

Skill Optimizer 用于优化和重构现有的 skill（技能）。它检查技能的触发描述、工作流、确认门槛、渐进式披露以及资源组织方式，确保技能结构清晰、触发精准、执行稳定。

## 适用场景

- 你有一个 skill，想检查和改进它的质量
- skill 的触发不准确、工作流混乱、输出不稳定
- skill 内容过于臃肿，需要拆分和重组
- 需要对 skill 进行结构化审查

## 核心原则

- **先审查，再规划，最后确认后修改** — 绝不在未确认前直接改文件
- **围绕用户指定的方向优化** — 不擅自扩大改动面
- **小步重构** — 只在确有收益时拆分新文件

## 核心工作流

### Step 1: Scope（确定范围）

确认目标 skill 和本次优化范围：
- 优先采用用户明确提出的优化方向（触发词、description、结构拆分、脚本化、确认流程）
- 如果用户只说"优化这个 skill"，先做完整审查，再给出分优先级计划
- 如果目标 skill 不明确，只问一个最短问题

### Step 2: Review（审查目标 skill）

读取目标 skill 的 `SKILL.md`，按需读取关联的 `references/`、`scripts/`、`assets/`。

审查基线：
- `references/review-checklist.md` — 审查清单
- `references/skill-design-review-framework.md` — 设计模式判断
- `references/技能创作最佳实践 - Claude API Docs.md` — 最佳实践取舍

重点检查项：

| 检查维度 | 具体内容 |
|----------|----------|
| 命名规范 | `name` 是否小写连字符，是否与目录一致 |
| 触发描述 | `description` 是否同时说明"做什么"和"何时用" |
| 模式匹配 | 主模式（Tool Wrapper / Generator / Reviewer / Inversion / Pipeline）是否匹配任务 |
| 工作流 | 是否清晰、可执行，是否存在必须确认却没卡住的步骤 |
| 资源组织 | 是否过胖、重复，是否适合拆到 references/scripts/assets |
| 输出格式 | 是否明确，是否方便另一个 agent 稳定执行 |
| 设计问题 | 是否过度设计、railroading、默认行为过强 |

### Step 3: Plan（输出优化计划并等待确认）

输出包含两部分：

**审查结论：**
- 模式判断（主模式 / 次模式 / 是否匹配）
- 高优先级问题（影响触发、正确性或执行稳定性）
- 中优先级问题（影响可维护性、可复用性）
- 低优先级问题（体验提升项）

**优化计划：**
- 每个修改项：目标文件路径、变更内容、原因、是否受用户指定方向驱动
- 超出范围的大问题单独列为"额外建议"

### Step 4: Implement（确认后实施）

用户确认后执行修改：
- 优先改动计划中已确认的文件
- 保留用户原有有效内容
- 只删除重复、失效或与新流程冲突的部分
- 新增引用文件确保从 SKILL.md 直接链接

### Step 5: Verify（校验结果）

改完后完成校验：

- frontmatter 只包含 `name` 和 `description`
- `name`、目录名、触发语义一致
- `description` 能独立表达触发条件
- `SKILL.md` 比改动前更短、更清晰
- 新增 references 不与 SKILL.md 重复大段内容

## 审查优先级

快速判定时的处理顺序：

1. **先修** — 触发失败、确认缺失、流程不可执行
2. **再修** — 结构臃肿、重复内容、资源组织混乱
3. **最后** — 措辞润色、示例补充、可读性增强

## 注意事项

- 不要把"审查结论"和"直接开始改文件"混成一步
- 不要为了显得全面就偷偷扩大改动面
- 不要在没确认前修改目标 skill
- 不要为了"审查完整"而把无关 reference 全部读进上下文
- 如果用户明确只要某个方向优化，围绕这个方向展开

## 文件结构

```
skill-optimizer/
├── SKILL.md                                          # 核心指令集
└── references/
    ├── review-checklist.md                            # 审查清单
    ├── skill-design-review-framework.md               # 设计模式判断框架
    └── 技能创作最佳实践 - Claude API Docs.md            # 最佳实践参考
```
