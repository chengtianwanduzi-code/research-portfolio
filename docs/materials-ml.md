# 材料生烟的机器学习建模

**Machine Learning for Material Smoke Responses**

[返回研究总览](../README.md)

[中文](#chinese-details) · [English](#english-details)

<a id="chinese-details"></a>

## 研究问题与用途

以环氧树脂等高分子材料为主要案例，建立材料信息与生烟响应之间的预测关系。研究面向材料设计与性能比较，关注预测误差、不同材料条件下的适用性，以及哪些信息有助于解释模型表现。

主要预测对象为总烟产生量（TSP）；相关燃烧性能用于各自定义明确的建模任务，不混同为生烟终点。

## 已有模型能力

- **传统回归建模：**已有树模型、核方法等实现，支持从材料信息预测性能，并比较不同模型的误差与稳定性。
- **材料组成与结构表示：**研究不同改性体系如何使用可比较的材料表示，结合相应测试条件开展建模。
- **辅助学习与多性能比较：**已有辅助学习及多目标研究实现，用于比较不同信息与训练方式的作用。
- **误差与因素分析：**整理预测误差和候选因素，为后续独立证据检验提供研究线索。

## 子方向：结构代理表示的跨材料验证

跨材料构效建模属于传统机器学习主线，用于评价结构代理表示在不同材料体系中的适用性。重点关注共同表示是否仍有预测价值，以及哪些部分需要随材料条件调整。

当前已开展其他高分子材料的资料整理与对照建模。对新材料重新建模与直接迁移的能力分别评价，已有局部验证不代表对所有材料通用。

## 当前进度

已有多代传统模型、相应实验实现和历史比较记录。共享数据已更新质量状态，后续比较使用当前有效数据，历史成绩继续保留原数据边界。跨材料验证已进入建模与结果整理阶段，完整结论仍需对应评价。

## 正在推进的工作

1. 在更新后的数据上复验相关预测模型，检查结果是否稳定。
2. 比较材料表示与辅助信息的贡献，整理不同性能任务的误差。
3. 完成跨材料验证，明确结构代理表示的适用条件和失败情况。

预测能力与化学机制解释分别验证；特征贡献或预测提升只提供线索。

公开介绍更新：2026-10-09。

<a id="english-details"></a>

## English

### Research question and intended use

Using epoxy resins and other polymer materials as primary cases, this area studies prediction of smoke responses from material information. It supports material design and property comparisons, with attention to prediction errors, applicability under different conditions, and information that helps explain model performance.

Total smoke production (TSP) is a primary prediction target. Related combustion properties are modeled as separately defined tasks rather than treated as smoke endpoints.

### Implemented capabilities

- **Traditional regression:** Tree models and kernel methods support prediction from material information and comparisons of error and stability.
- **Composition and structural representations:** Comparable representations of different modification systems are studied together with their test conditions.
- **Auxiliary learning and property comparisons:** Implementations support comparisons of auxiliary information and training approaches across property tasks.
- **Error and factor analysis:** Prediction errors and candidate factors provide research leads for subsequent independent evidence checks.

### Cross-material validation of structural proxy representations

Cross-material structure–property modeling belongs to the traditional machine learning research program. It evaluates whether structural proxy representations remain useful across material systems and which parts require adaptation to material conditions.

Literature organization and comparative modeling for other polymers have begun. Retraining for a new material and direct transfer are evaluated separately. Local validation does not establish universality across all materials.

### Current progress

Multiple generations of traditional models, experimental implementations, and historical comparisons exist. The shared data quality status has been updated. Subsequent comparisons use currently eligible data; historical scores retain their original data boundaries. Cross-material work includes modeling and result organization, with complete conclusions subject to the corresponding evaluation.

### Ongoing work

1. Re-evaluate relevant models with updated data and examine stability.
2. Compare material representations and auxiliary information, and organize errors across property tasks.
3. Complete cross-material validation and identify applicability conditions and failures.

Predictive capability and chemical mechanisms are validated separately; feature contributions and prediction improvements provide leads.

Introduction updated: 2026-10-09.
