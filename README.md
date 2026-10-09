# Materials & Scientific Reasoning Research

**材料构效建模、机器学习表征与证据支持的科学推理**

[中文](#chinese-overview) · [English](#english-overview)

<a id="chinese-overview"></a>

由成田丸读子维护。本仓库介绍正在开展的研究、已有模型能力和当前进度。研究以材料生烟预测为主要应用之一，进一步探索数值与文本表征、智能体辅助预测修正、跨领域研究方向预测，以及化学关系与逻辑推理。

研究介绍直接维护在本 README 和 `docs/` 中，可在 GitHub 页面阅读和编辑。核心代码、研究数据、模型权重和完整实验结果目前保留在私有研究仓库中。

## 研究方向与当前进度

| 方向 | 模型或方法关注的能力 | 当前进度 | 详细介绍 |
| --- | --- | --- | --- |
| 材料生烟的机器学习建模 | 材料组成与结构表示、生烟回归预测、多性能比较、跨材料验证 | 已有传统模型与历史实验；推进数据更新后的复验及跨材料验证 | [Materials ML](docs/materials-ml.md) |
| Transformer 与数值—文本联合表征 | 材料表示学习、多性能预训练与专项微调、可学习符号图、预测与解释 | 多类模型和联合表征原型已实现；继续复验预测表现与表示一致性 | [Numeric–Text & Symbolic Graphs](docs/numeric-text.md) |
| 智能体辅助预测修正 | 基础模型误差分析、证据辅助修正、修正条件与效果评价 | 已整理校准和检索修正原型；正在明确新实验的比较条件 | [Agent-Assisted Correction](docs/agent-correction.md) |
| 跨领域证据与研究方向预测 | 文献信息组织、研究问题识别、方向发展潜力预测 | 首版评价与模型对照已完成开发回放；推进问题族扩充与独立验证 | [Research Forecasting](docs/research-forecast.md) |
| 化学关系与逻辑推理 | 化学关系表达、证据追溯、候选解释比较与机理假说推理 | 已有局部模型和文献案例原型；继续完善证据判别与独立评价 | [Chemical Reasoning](docs/chemical-reasoning.md) |

## 阶段性预测指标

以下均为总烟产生量（TSP）的已保存结果，汇总五次运行的均值与样本标准差；MAE使用原单位m²。**这些结果来自数据质量更新前的研究版本，当前清洗数据复验另行记录。**

### 历史回顾性测试

| 模型／原型 | R²，均值 ± 标准差 | MAE，均值 ± 标准差（m²） |
| --- | ---: | ---: |
| 设计阶段机器学习模型 | 0.8083 ± 0.0518 | 3.7734 ± 0.2189 |
| 单 Transformer | 0.7006 ± 0.0349 | 4.7127 ± 0.2250 |
| Transformer 集成 | 0.7132 ± 0.0696 | 4.4990 ± 0.4549 |
| Transformer 与树模型混合 | 0.7323 ± 0.0541 | 4.3130 ± 0.2467 |

采用样本行随机80∶20划分。设计阶段模型使用50 kW/m²下的材料子集，Transformer系列使用较宽条件的研究池；评价池不同，不据此跨行判断模型优劣。混合模型包含树模型，不作为纯Transformer成绩。

### 开发阶段原型

| 模型／原型 | R²，均值 ± 标准差 | MAE，均值 ± 标准差（m²） |
| --- | ---: | ---: |
| 数值—文本联合原型 | 0.7166 ± 0.0451 | 4.1689 ± 0.3198 |
| 同条件数值监督对照 | 0.7171 ± 0.0453 | 4.1593 ± 0.3102 |
| 可学习符号图原型 | 0.6893 ± 0.1373 | 5.2101 ± 1.4914 |
| 同表征数值预测对照 | 0.7061 ± 0.0984 | 4.9461 ± 1.2187 |

以上为训练侧开发验证，不能与测试成绩直接排名。联合原型与数值监督对照的预测表现接近；符号图仍弱于同表征数值预测对照。图表达与化学机理成立分别评价。

[查看评价条件与指标说明](docs/metrics.md)。

## 1．材料生烟的机器学习建模

**Machine Learning for Material Smoke Responses**

以环氧树脂等高分子材料为主要案例，研究材料组成、结构信息和测试条件如何支持生烟性能预测。主要关注总烟产生量（TSP），同时开展相关燃烧性能的建模与比较。

已有工作包括树模型与核方法等传统回归模型、材料结构表示、辅助学习和预测误差分析。研究既关注预测能力，也关注模型在不同材料和测试条件下的适用范围。

**跨材料构效验证属于这一传统机器学习方向**，用于评价结构代理表示的泛用性。它与基础预测共享研究主线，当前仍在开展不同材料体系下的验证。[查看能力、进度与后续工作](docs/materials-ml.md)。

## 2．Transformer 与数值—文本联合表征

**Transformer Models, Numeric–Text Representation & Learnable Symbolic Graphs**

研究材料信息的表示学习，将数值信息与文本信息用于性能预测和解释。已有多性能预训练、目标性能微调、不同材料表示及传统模型对照等研究实现。

数值—文本联合表征与可学习符号图是正在推进的子方向：探索怎样表达可供模型计算、也可供研究者理解的材料关系，并评价预测与解释之间的一致性。联合预测与符号图原型已跑通，后续重点是数据更新后的复验、概念与证据质量，以及独立评价。[查看能力、进度与后续工作](docs/numeric-text.md)。

## 3．智能体辅助预测修正

**Agent-Assisted Prediction Correction**

以已有机器学习预测为起点，研究智能体能否结合材料信息、预测误差与相关证据，提出有用的修正；同时判断何时应修正、何时应保留原预测。

已有数值校准与文献检索修正的历史原型，当前已完成研究方向梳理。接下来将明确基础模型、可用信息和比较条件，区分普通数值修正、证据信息与智能体本身的贡献。当前尚未确认智能体相对常规方法的独立优势。[查看能力、进度与后续工作](docs/agent-correction.md)。

## 4．跨领域证据与研究方向预测

**Cross-Domain Evidence & Research Forecasting**

研究跨领域知识及其变化能否帮助识别值得进一步研究的问题，并预测研究方向的后续发展潜力。烟科学是首个案例领域，方法研究同时关注不同领域信息的组织与比较。

已建立文献题录接入、首版量化评价和模型对照，并完成真实材料的开发回放。当前继续扩充研究问题、完善文献与问题的对应关系，以及开展独立验证；首版开发结果尚未确认相对常规趋势方法的稳定增益。[查看能力、进度与后续工作](docs/research-forecast.md)。

## 5．化学关系与逻辑推理

**Chemical Relations & Evidence-Based Reasoning**

研究如何表达化学对象、条件、关系与观测，支持可检查的推理和不同机理解释的比较。目标是让解释能够追溯依据，并保留必要假设、未知部分及竞争路径。

已有可执行关系表达、局部学习模型、文献证据组织和候选解释展示的原型，完成了部分真实文献案例的开发验证。当前推进证据判别、候选解释评价和更独立的案例比较。可执行推理和模型输出与化学机理成立分别评价。[查看能力、进度与后续工作](docs/chemical-reasoning.md)。

## 研究进度的阅读方式

“已有实现”表示相应程序或原型已经运行；“开发验证”表示已在研究开发材料上检查，不能等同于独立验证。历史版本各自保留原数据和实验条件，当前工作按更新后的数据继续复验。预测改善、解释一致性和化学机制分别依据相应证据判断。

本仓库公开研究方向、功能、阶段进展及经核对的汇总指标。核心实现、具体模型架构、公式、特征清单、训练配方和完整实验结果继续保留。后续公开范围随研究进展另行决定。

## 更新

- **2026-10-09：**补充TSP的R²、MAE、五次运行波动及评价条件，区分历史测试与开发原型。
- **2026-10-09：**以 GitHub README 和 Markdown 文档作为主要介绍入口，补充五个方向的能力、已有工作与当前进度。本日期为介绍更新日期，不作为研究起始日期。

© 2026 成田丸读子。保留权利。本仓库未授予开源许可。

<a id="english-overview"></a>

## English overview

**Materials structure–property modeling, machine learning representations, and evidence-based scientific reasoning.**

Maintained by 成田丸读子. This repository presents ongoing research, implemented capabilities, and current progress. Material smoke prediction is a major application, alongside numeric–text representations, agent-assisted prediction correction, cross-domain research forecasting, and chemical reasoning.

The research descriptions are maintained directly in this README and the Markdown files under `docs/`, which can be read and edited on GitHub. Core code, research data, model weights, and complete experimental results currently remain in private research repositories.

### Research areas and progress

| Area | Capabilities under study | Current progress | Details |
| --- | --- | --- | --- |
| Machine learning for material smoke responses | Composition and structural representations, smoke regression, multiple property comparisons, cross-material validation | Traditional models and historical experiments implemented; re-evaluation with updated data and cross-material validation ongoing | [Materials ML](docs/materials-ml.md) |
| Transformer and numeric–text representations | Material representation learning, multi-property pretraining and fine-tuning, learnable symbolic graphs, prediction and explanation | Multiple models and joint representation prototypes implemented; predictive performance and representation consistency under evaluation | [Numeric–Text & Symbolic Graphs](docs/numeric-text.md) |
| Agent-assisted prediction correction | Error analysis, evidence-assisted correction, conditions for correction and evaluation | Calibration and retrieval prototypes organized; conditions for new comparative experiments being defined | [Agent-Assisted Correction](docs/agent-correction.md) |
| Cross-domain evidence and research forecasting | Literature organization, research problem identification, forecasting direction development | Initial evaluation and model comparisons completed on retrospective development materials; problem coverage and independent validation being expanded | [Research Forecasting](docs/research-forecast.md) |
| Chemical relations and logical reasoning | Chemical relation representations, evidence tracing, comparison of explanations and mechanistic hypotheses | Local models and literature case prototypes implemented; evidence assessment and independent evaluation ongoing | [Chemical Reasoning](docs/chemical-reasoning.md) |

### Representative prediction metrics

These are saved total smoke production (TSP) results, reported as means and sample standard deviations over five runs. MAE is in the original unit, m². **They come from research versions preceding the data quality update; re-evaluation with cleaned data is tracked separately.**

#### Historical retrospective tests

| Model / prototype | R², mean ± SD | MAE, mean ± SD (m²) |
| --- | ---: | ---: |
| Design-stage machine learning model | 0.8083 ± 0.0518 | 3.7734 ± 0.2189 |
| Single Transformer | 0.7006 ± 0.0349 | 4.7127 ± 0.2250 |
| Transformer ensemble | 0.7132 ± 0.0696 | 4.4990 ± 0.4549 |
| Transformer–tree hybrid | 0.7323 ± 0.0541 | 4.3130 ± 0.2467 |

The tests use row-random 80:20 splits. The design-stage model uses a 50 kW/m² material subset, while the Transformer series uses a research pool covering broader conditions. Different evaluation pools prevent a direct cross-row ranking. The hybrid contains a tree model and is not a pure Transformer result.

#### Development prototypes

| Model / prototype | R², mean ± SD | MAE, mean ± SD (m²) |
| --- | ---: | ---: |
| Numeric–text joint prototype | 0.7166 ± 0.0451 | 4.1689 ± 0.3198 |
| Matched numerical-supervision control | 0.7171 ± 0.0453 | 4.1593 ± 0.3102 |
| Learnable symbolic graph prototype | 0.6893 ± 0.1373 | 5.2101 ± 1.4914 |
| Numerical prediction control with the same representation | 0.7061 ± 0.0984 | 4.9461 ± 1.2187 |

These are training-side development validation results, not directly comparable with test scores. The joint prototype and numerical-supervision control have similar prediction performance. The symbolic graph remains below its numerical control with the same representation. Graph expression is evaluated separately from confirmation of chemical mechanisms.

[Evaluation conditions and metric notes](docs/metrics.md).

### 1. Machine learning for material smoke responses

Epoxy resins and other polymer materials provide the main cases for studying how composition, structural information, and test conditions support smoke prediction. Total smoke production (TSP) is a primary response; related combustion properties are also modeled and compared as separate tasks.

Existing work includes traditional regression with tree models and kernel methods, material structural representations, auxiliary learning, and error analysis. The research examines both predictive performance and applicability across materials and test conditions.

**Cross-material structure–property validation belongs to this traditional machine learning research area.** It evaluates the generality of structural proxy representations within the same research program. Validation across different material systems is ongoing. [Capabilities, progress, and next steps](docs/materials-ml.md).

### 2. Transformer and numeric–text representations

This area studies material representation learning for prediction and explanation using numerical and textual information. Implementations include multi-property pretraining, target-specific fine-tuning, alternative representations, and comparisons with traditional models.

Numeric–text representations and learnable symbolic graphs form an active research direction. The aim is to express material relations in ways that support computation and human understanding, and to evaluate consistency between predictions and explanations. Joint prediction and symbolic graph prototypes are operational. Priorities include re-evaluation with updated data, concept and evidence quality, and independent evaluation. [Capabilities, progress, and next steps](docs/numeric-text.md).

### 3. Agent-assisted prediction correction

Starting from existing machine learning predictions, this area investigates whether agents can use material information, prediction errors, and relevant evidence to propose useful corrections, and when the original prediction should be retained.

Historical numerical calibration and literature retrieval prototypes have been organized, and the research scope has been reviewed. Next steps will define base models, available information, and comparison conditions to separate the contributions of numerical correction, additional evidence, and agent assistance. An independent advantage over conventional methods has not yet been established. [Capabilities, progress, and next steps](docs/agent-correction.md).

### 4. Cross-domain evidence and research forecasting

This area investigates whether cross-domain knowledge and its changes help identify worthwhile research questions and forecast the development potential of research directions. Smoke science is the first case domain; the methodological work also examines how information from different fields is organized and compared.

Literature metadata access, an initial quantitative evaluation, and model comparisons have been implemented and evaluated on real development materials. Current priorities are expanding research problems, improving the mapping between literature and questions, and independent validation. Initial development results have not established a stable advantage over conventional trend-based methods. [Capabilities, progress, and next steps](docs/research-forecast.md).

### 5. Chemical relations and logical reasoning

This area studies representations of chemical objects, conditions, relations, and observations for inspectable reasoning and comparison of mechanistic explanations. Explanations should retain their evidence, necessary assumptions, unknowns, and competing paths.

Prototypes include executable relation representations, local learned models, literature evidence organization, and displays of candidate explanations. Some real literature cases have undergone development evaluation. Evidence assessment, evaluation of candidate explanations, and more independent case comparisons are ongoing. Executable reasoning and model outputs are evaluated separately from confirmation of a chemical mechanism. [Capabilities, progress, and next steps](docs/chemical-reasoning.md).

### Interpreting progress

An implemented capability means a program or prototype has run. Development evaluation uses research development materials and does not imply independent validation. Historical versions retain their original data and experimental conditions; current work is being re-evaluated using updated data. Predictive improvement, explanation consistency, and chemical mechanisms require their respective evidence.

This repository shares research directions, capabilities, progress, and verified aggregate metrics. Core implementations, detailed architectures, formulas, feature lists, training recipes, and complete experimental results remain withheld. Further disclosure will be decided as the research progresses.

### Update

- **2026-10-09:** Added TSP R², MAE, variation over five runs, and evaluation conditions, distinguishing historical tests from development prototypes.
- **2026-10-09:** GitHub README and Markdown documents became the main introduction format, with expanded capabilities and progress for five areas. This is the introduction update date, not the research start date.

© 2026 成田丸读子. All rights reserved. No open-source license is granted for this repository.
