# 智能体辅助预测修正

**Agent-Assisted Prediction Correction**

[返回研究总览](../README.md)

[中文](#chinese-details) · [English](#english-details)

<a id="chinese-details"></a>

## 研究问题与用途

以传统机器学习或 Transformer 的已有预测为起点，研究智能体能否结合材料信息、误差信息和相关证据提出有效修正。目标同时包括改善预测、判断修正条件，以及识别应当保持原预测的情况。

## 已有工作与能力

- **数值校准原型：**已有基于预测误差的常规校准实现，用作修正方法的比较基础。
- **文献检索修正原型：**已有组织文献信息和相似材料信息的探索程序，用于研究额外证据是否有帮助。
- **方向与比较设计：**已整理历史研究，明确基础模型、修正方法与科学解释各自的评价问题。

这些是现有探索的基础。智能体修正的独立贡献仍需通过新实验检验，不能仅凭历史程序的名称判断有效性。

## 当前进度

独立研究方向已建立，历史校准与检索原型已整理，研究方向梳理已完成。当前重点是明确新实验采用的基础模型、信息条件和修正对象，而不是将历史分数作为新模型成绩。

更广义的模型或关系修订仍在讨论中，尚未作为已完成能力发布。

## 正在推进的工作

1. 固定现行数据与基础模型，确定预测时能够使用的信息。
2. 比较原预测、普通数值修正和智能体辅助修正，分析额外信息与智能体反馈的作用。
3. 记录改善、无改善和恶化情况，明确修正方法适用于哪些条件。

当前尚未确认智能体相对常规修正方法的稳定独立优势。

公开介绍更新：2026-10-09。

<a id="english-details"></a>

## English

### Research question and intended use

Starting from predictions by traditional machine learning or Transformer models, this area studies whether agents can combine material information, error information, and relevant evidence to propose useful corrections. It also examines correction conditions and cases where the original prediction should be retained.

### Existing work and capabilities

- **Numerical calibration prototypes:** Conventional error-based calibration provides a basis for comparison.
- **Literature retrieval correction prototypes:** Exploratory programs organize literature and similar material information to investigate the value of additional evidence.
- **Scope and comparison design:** Historical work has been reviewed to distinguish evaluation of base models, correction methods, and scientific explanations.

These provide a starting point for further exploration. Independent agent contributions require new experiments and cannot be inferred from historical program names.

### Current progress

The research area has been established, historical calibration and retrieval prototypes organized, and the research scope reviewed. The current focus is defining base models, information conditions, and correction targets for new experiments. Historical scores are not presented as results of a new model.

Broader model or relation revision remains under discussion and is not presented as an established capability.

### Ongoing work

1. Fix current data and base models, and define information available at prediction time.
2. Compare original predictions, conventional numerical corrections, and agent-assisted corrections; examine the roles of additional information and agent feedback.
3. Record improvements, no improvements, and deterioration to identify applicability conditions.

A stable independent advantage over conventional correction methods has not yet been established.

Introduction updated: 2026-10-09.
