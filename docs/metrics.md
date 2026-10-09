# 阶段性预测指标 / Stage Prediction Metrics

[返回研究总览 / Research overview](../README.md)

## 中文说明

### 任务与统计口径

本页公开总烟产生量（TSP）预测的阶段性汇总，不包含模型结构、权重、逐样品结果或训练配方。每项均为五次运行的均值±样本标准差；标准差表示不同运行的波动，不是置信区间。R²越高、MAE越低表示在相同评价条件下预测较好，跨任务或评价池比较需要另外设计对照。

### 历史回顾性测试

| 模型／原型 | R²，均值 ± 标准差 | MAE，均值 ± 标准差（m²） |
| --- | ---: | ---: |
| 设计阶段机器学习模型 | 0.8083 ± 0.0518 | 3.7734 ± 0.2189 |
| 单 Transformer | 0.7006 ± 0.0349 | 4.7127 ± 0.2250 |
| Transformer 集成 | 0.7132 ± 0.0696 | 4.4990 ± 0.4549 |
| Transformer 与树模型混合 | 0.7323 ± 0.0541 | 4.3130 ± 0.2467 |

- 设计阶段模型：677条材料记录，50 kW/m²，已知相容纯基体参照；五次样本行随机80∶20划分。仅公布该设计阶段分支的五次结果，不将完整输入对照或其他重复次数的成绩归给它。
- Transformer系列：主研究池1589条具有核验基体参照的记录，五次样本行随机80∶20划分。单模型、集成和混合方案在该系列的同一评价成员上报告。混合方案含树模型贡献。
- 结果属于回顾性评价，相关测试材料曾被研究过程接触；不标作新的盲验证。随机行成绩不代表未见论文、配方族或未知基体上的泛化。

### 开发原型与对应对照

| 模型／原型 | R²，均值 ± 标准差 | MAE，均值 ± 标准差（m²） |
| --- | ---: | ---: |
| 数值—文本联合原型 | 0.7166 ± 0.0451 | 4.1689 ± 0.3198 |
| 同条件数值监督对照 | 0.7171 ± 0.0453 | 4.1593 ± 0.3102 |
| 可学习符号图原型 | 0.6893 ± 0.1373 | 5.2101 ± 1.4914 |
| 同表征数值预测对照 | 0.7061 ± 0.0984 | 4.9461 ± 1.2187 |

- 数值—文本原型：使用主研究池对应的内层开发划分，各次开发验证有164—200条记录；数值监督对照与联合原型使用匹配条件。当前数值预测基本持平，不声称联合训练提高了预测精度。
- 符号图原型：使用343条共同标签记录对应的开发子集，各次验证35—43条；对照使用相同表征与评价成员。候选选择受开发诊断影响，结果不是独立测试。符号图的预测仍弱于相应数值对照，不能据此确认材料因果机理。

### 数据版本与公开范围

所有表中成绩均来自2026-10-09数据质量更新前的研究版本。当前清洗数据上的复验与后续新评价分别记录，尚未完成的运行不作为正式结果发布。此页公开有限的阶段性汇总；源代码、原始数据、模型权重、详细训练方法及完整实验资产仍保留私有。

智能体预测修正、跨领域研究方向预测和化学逻辑推理有不同的能力终点，目前不套用上述TSP回归指标，也不填入未经核实的分数。

## English

### Task and statistics

This page shares stage-level aggregates for total smoke production (TSP) prediction. Model structures, weights, individual sample results, and training recipes are not included. Each entry reports a mean and sample standard deviation over five runs. SD measures variation across runs, not a confidence interval. Higher R² and lower MAE indicate better prediction under the same evaluation conditions; comparisons across tasks or evaluation pools require separate controls.

### Historical retrospective tests

| Model / prototype | R², mean ± SD | MAE, mean ± SD (m²) |
| --- | ---: | ---: |
| Design-stage machine learning model | 0.8083 ± 0.0518 | 3.7734 ± 0.2189 |
| Single Transformer | 0.7006 ± 0.0349 | 4.7127 ± 0.2250 |
| Transformer ensemble | 0.7132 ± 0.0696 | 4.4990 ± 0.4549 |
| Transformer–tree hybrid | 0.7323 ± 0.0541 | 4.3130 ± 0.2467 |

- Design-stage model: 677 material records at 50 kW/m², with known compatible neat-matrix references; five row-random 80:20 splits. These are the five-run results of the design-stage branch, not scores reassigned from the full-input control or another repeat count.
- Transformer series: a main research pool of 1589 records with checked neat-matrix references, using five row-random 80:20 splits. Single-model, ensemble, and hybrid results use the same evaluation members within this series. The hybrid includes a tree-model contribution.
- These are retrospective evaluations of test materials previously exposed during research, not new blind validation. Row-random scores do not establish generalization to unseen papers, formulation families, or unknown matrices.

### Development prototypes and matched controls

| Model / prototype | R², mean ± SD | MAE, mean ± SD (m²) |
| --- | ---: | ---: |
| Numeric–text joint prototype | 0.7166 ± 0.0451 | 4.1689 ± 0.3198 |
| Matched numerical-supervision control | 0.7171 ± 0.0453 | 4.1593 ± 0.3102 |
| Learnable symbolic graph prototype | 0.6893 ± 0.1373 | 5.2101 ± 1.4914 |
| Numerical prediction control with the same representation | 0.7061 ± 0.0984 | 4.9461 ± 1.2187 |

- Numeric–text prototype: inner development splits associated with the main pool, with 164–200 validation records per run. Numerical-supervision and joint prototypes use matched conditions. Numerical prediction performance is essentially unchanged; improved prediction accuracy is not claimed for joint training.
- Symbolic graph prototype: a development subset associated with 343 records with common labels, with 35–43 validation records per run. The control uses the same representation and evaluation members. Candidate choices were informed by development diagnostics, so these are not independent test results. The graph remains below the corresponding numerical control and does not establish causal material mechanisms.

### Data versions and disclosure scope

All table scores come from research versions preceding the 2026-10-09 data quality update. Re-evaluation with cleaned data and subsequent evaluations are recorded separately; unfinished runs are not published as final results. This page shares limited aggregate metrics. Source code, raw data, model weights, detailed training methods, and complete experimental assets remain private.

Agent-assisted prediction correction, cross-domain forecasting, and chemical reasoning have different capability endpoints. The TSP regression scores above are not assigned to those areas, and unverified scores are not supplied.

公开介绍更新 / Introduction updated: 2026-10-09.
