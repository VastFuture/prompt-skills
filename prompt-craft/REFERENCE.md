# Prompt Craft Reference Card

## 1. Compression Cheatsheet (脱水修炼)

| 原始描述 (段落/句子) | 压缩结果 (词语/单字) | 语义压缩包 (意) |
| :--- | :--- | :--- |
| 说话非常有逻辑，思考很深刻，总是能从本质看问题 | 哲学家 | 深度、逻辑、本质 |
| 语气尖锐，喜欢讽刺，说话不留情面，一针见血 | 辛辣反讽 | 批判、犀利、穿透 |
| 像是在黑色屋子里点亮了星星一样，精准定位 | 点亮星星 | 精准、坐标、模式 |
| 按照步骤一个一个来，先做A再做B，最后检查结果 | Workflow | 序列、受控、闭环 |

## 2. Transformation Examples (描述 → 定义)

- **Before (描述)**: 你需要写得非常生动，让读者感到很真实，就像身临其境一样。
- **After (定义)**: 注入[临场感]，使用五感联觉描写，点亮[共情]坐标。

- **Before (描述)**: 不要写得太复杂，不要用难懂的词，尽量让小学生也能看懂。
- **After (定义)**: [降维表达]，核心词汇限定在[基础词库]，保持[极致简约]。

## 3. Prompt Format Templates

### A. Markdown (逻辑框架型)
```markdown
# Role: [压缩包名称]
## Profile: [背景/技能解压]
## Rules: [强制约束/禁止事项]
## Workflow: [逻辑链路]
## Initialization: [开场动作]
```

### B. Lisp (精准定义型)
```lisp
(defun 核心函数 (输入)
  (let* ((核 (提取本质 输入))
         (意 (点亮坐标 核)))
    (输出 意)))
```

### C. XML (Claude 适配型)
```xml
<instruction>
  <role>...</role>
  <workflow>...</workflow>
</instruction>
```

## 4. Golden Words Reference

- **思维指令**: `think step by step`, `take a deep breath`, `Step-Back Prompting`.
- **质量提示**: `your answer is very important to me`, `do it right and i'll give you a tip`.
- **逻辑控制**: `First... Then... Finally...`, `反向PUA: 先列10个反对理由`.

## 5. Verification Checklist (自检表)

1. [ ] **去水**: 是否删除了所有“片汤话”和解释性长句？
2. [ ] **定性**: 核心意图是否已转化为[精准定义词]？
3. [ ] **聚拢**: 是否使用了 #, -, 或是闭合标签聚拢语义？
4. [ ] **去否**: 是否将“不要...”转化为了正面指令“保持...”、“使用...目标为...”？
5. [ ] **适配**: 格式是否符合目标模型（GPT/Claude/Gemini）的偏好？
6. [ ] **深度**: 本意是否清晰？是否已经 Read in 足够多的 Know-how？
