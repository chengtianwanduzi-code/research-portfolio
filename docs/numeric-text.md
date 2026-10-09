# Transformer 与数值—文本联合表征

**Transformer Models, Numeric–Text Representation & Learnable Symbolic Graphs**

[返回研究总览](../README.md)

[中文](#chinese-details) · [English](#english-details)

<a id="chinese-details"></a>

## 研究问题与用途

研究材料数值信息、文本信息与模型预测之间的联合表达。除了性能预测，也关注研究者能否理解模型使用的关系，以及文字解释与数值输出是否一致。

## 已有模型能力

- **材料表示学习：**已有 Transformer 材料预测实现，用于比较不同材料表示对预测表现的影响。
- **多性能预训练与专项微调：**先开展共享表示学习，再针对目标性能训练和比较，研究共同知识与专项适配的作用。
- **模型与混合方法比较：**已有传统模型、Transformer 和混合方法对照；包含其他模型的方案按其实际组成评价。
- **数值—文本联合表征：**已有联合预测与解释原型，探索材料数值和语言描述之间的对应与一致性。
- **可学习符号图：**已有可执行的研究原型，探索可计算的关系表示与可理解表达，评价其预测和解释能力。

## 当前进度

多响应学习、目标性能微调和多种表示实验已运行。当前使用更新后的数据，按已有配置继续复验相应性能模型。

数值—文本联合预测与符号图原型已跑通，并完成开发阶段比较。部分研究方向仍需补充可靠的概念或过程证据；历史原型与当前可用于新训练的输入分别管理，不沿用失效的数据或监督记录。

## 正在推进的工作

1. 完成数据更新后的模型比较，整理不同性能任务的收益和波动。
2. 评价联合表征中的预测、文字解释与关系表达是否一致。
3. 改善概念与来源证据的质量，再开展更独立的评价。

可学习表示中的概念和关系仍需外部证据解释，模型输出不直接作为已成立的材料因果机理。

公开介绍更新：2026-10-09。

<a id="english-details"></a>

## English

### Research question and intended use

This area studies joint representations of material numerical information, textual information, and model predictions. Alongside property prediction, it examines whether researchers can understand the relations used by the model and whether textual explanations agree with numerical outputs.

### Implemented capabilities

- **Material representation learning:** Transformer prediction implementations support comparisons of alternative material representations.
- **Multi-property pretraining and target-specific fine-tuning:** Shared representation learning is followed by target-specific training and comparison to study common knowledge and adaptation.
- **Model and hybrid comparisons:** Traditional models, Transformers, and hybrid methods are compared according to their actual components.
- **Numeric–text representations:** Joint prediction and explanation prototypes explore correspondence and consistency between numbers and language.
- **Learnable symbolic graphs:** Executable research prototypes explore relations that support computation and understandable expression, with predictive and explanatory capabilities evaluated separately.

### Current progress

Multi-response learning, target-specific fine-tuning, and alternative representation experiments have run. Models are being re-evaluated with updated data using existing configurations.

Joint numeric–text prediction and symbolic graph prototypes are operational and have undergone development comparisons. Some directions require more reliable concept or process evidence. Historical prototypes and inputs eligible for current training are managed separately; invalid data or supervision records are not reused.

### Ongoing work

1. Complete model comparisons with updated data and examine gains and variation across tasks.
2. Evaluate consistency among predictions, textual explanations, and relation representations.
3. Improve concept and source evidence quality, followed by more independent evaluation.

Concepts and relations in learned representations require external evidence for interpretation. Model outputs do not directly establish causal material mechanisms.

Introduction updated: 2026-10-09.
