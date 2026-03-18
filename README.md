<div align="center">
<img src='https://github.com/user-attachments/assets/38baa5b6-b6c4-42a3-96ae-f5a300013b5c' alt='MGBIE' height='150px'>
</div>

# <p align="center"><font size=50><strong>[CCL2026 第一届杂粮育种信息抽取评测](https://github.com/zhiweihu1103/CCL2026-MGBIE)</strong></font></p>

<div align="center">

  <div style="display: inline-block; text-align: center; margin: 0 20px;">
    <div>山西省后稷实验室</div>
    <img src="https://github.com/user-attachments/assets/aa11d15e-f55a-4b48-af90-b8be6e101a87" height="90px">
  </div>

  <div style="display: inline-block; text-align: center; margin: 0 20px;">
    <div>山西农业大学</div>
    <img src="https://github.com/user-attachments/assets/4d0aa98e-8b86-4d34-b8cd-1f65ec6256ed" height="90px">
  </div>

  <div style="display: inline-block; text-align: center; margin: 0 20px;">
    <div>山西大学</div>
    <img src="https://github.com/user-attachments/assets/94aeaa28-45dc-446c-9a8d-9f39fc51bd44" height="90px">
  </div>

  <div style="display: inline-block; text-align: center; margin: 0 20px;">
    <div>武汉大学</div>
    <img src="https://github.com/user-attachments/assets/ebbb1edd-21db-4d6f-83b1-a161904461bd" height="90px">
  </div>

</div>

## 评测组织者
* 胡志伟（山西省后稷实验室、山西农业大学）
* 孔照胜（山西省后稷实验室、山西农业大学）
* 高建华（山西省后稷实验室、山西农业大学）
* 谭红叶（山西大学）
* 闫智超（山西大学）
* 李茹（山西大学）
* 谢倩倩（武汉大学）

## 联系人及联系方式
* 杨森杰（山西大学硕士生，yangsenjie1@sxu.edu.cn）

第二十五届中国计算语言学大会（The 25th China National Conference on Computational Linguistics, CCL 2026）将于2026年10月15至18日在湖北省宜昌市举行。中国计算语言学大会创办于1991年，由中国中文信息学会计算语言学专业委员会主办。经过30余年的发展，中国计算语言学大会已成为国内自然语言处理领域权威性最高、规模和影响最大的学术会议。作为中国中文信息学会（国内一级学会）的旗舰会议，CCL聚焦于中国境内各类语言的智能计算和信息处理，为研讨和传播计算语言学最新学术和技术成果提供了最广泛的高层次交流平台。

## 1 任务介绍
杂粮（如谷子、黍稷、高粱、燕麦、荞麦、各种食用豆等）育种领域相关信息长期以自然语言形式沉淀在论文、品种审定与登记材料、区域试验报告、栽培技术规程等文本中。这些文本记录了材料来源与系谱演化、目标性状及其测定结果，同时包含栽培管理与胁迫处理条件及其分子标记、基因位点和QTL等分子证据。由于杂粮育种文本专业术语密集，同一概念存在多种表述，材料名称与试验要素还会嵌套表达，导致关键信息难以稳定抽取并统一结构化，进而限制了知识检索、跨文献证据汇总与育种决策支持等应用。为推动信息抽取技术在杂粮育种知识管理与数据资源建设中的落地应用，提升育种信息整理与证据汇总的自动化水平，我们提出面向杂粮育种的信息抽取评测任务，并构建标注数据集，用于评估模型在育种语境理解、术语识别与结构化表达方面的能力。数据集来源于公开论文、品种认定与登记材料、区域试验报告和栽培技术文档等多类型文本，重点标注育种材料、系谱信息、关键性状指标、试验条件、对照关系及分子证据等核心要素，以评估系统对育种要素的识别能力与跨句信息组织能力。具体来说，本次杂粮育种信息抽取评测主要包含以下两个子任务：
* **子任务1：命名实体识别**：该任务要求从杂粮育种文本中自动识别并抽取关键实体，输出实体边界及实体类型标签，为后续结构化抽取提供基础。
* **子任务2：关系抽取**：该任务要求在已识别实体基础上抽取实体间语义关系，输出关系三元组，用于刻画育种知识链条中的系谱、性状表现、试验条件及其分子证据等内容。

## 2 评测数据
本次评测数据来自科研论文、育种报告等文本信息源，总规模为2,000条样本。为确保评估的科学性与可复现性，数据集划分为训练集、验证集和测试集三部分，样本数量分别为1,000条、400条和600条；评测流程分为A榜与B榜两个阶段，其中验证集用于A榜阶段的模型调试与初步排名，测试集用于B榜阶段的最终性能评估与结果确认。命名实体识别与关系抽取任务的数据标注字段说明如下：

### 2.1 命名实体识别任务

| 类型 | 英文（缩写） | 说明 | 示例 |
|------|-------------|------|------|
| 作物 | Crop (CROP) | 杂粮作物的物种或类别名称，用于指明研究对象 | 谷子 |
| 品种 | Variety / Cultivar (VAR) | 审定/登记/推广的具体品种名称或代号 | 晋谷21 |
| 性状 | Trait (TRT) | 表型/农艺/品质/抗性等性状名称 | 株高、千粒重 |
| 生育时期 | Growth Stage (GST) | 作物生长发育阶段节点 | 出苗期、拔节期 |
| 基因 | Gene (GENE) | 与性状相关的功能基因/候选基因名称 | Waxy |
| 数量性状位点 | QTL (QTL) | 与数量性状相关的遗传位点/区间标识 | qPH3.1 |
| 分子标记 | Molecular Marker (MRK) | 用于定位/选择的 SSR/SNP/Indel/KASP 等标记 | SSR-Xgwm20 |
| 染色体 | Chromosome (CHR) | 染色体编号或名称 | Chr1 |
| 育种方法 | Breeding Method (BM) | 育种或选择的技术路线/方法 | 杂交育种 |
| 亲本/杂交组合 | Parent / Cross (CROSS) | 父本/母本材料及其杂交组合表达 | A×B |
| 非生物胁迫 | Abiotic Stress (ABS) | 非生命因素引起的胁迫条件 | 干旱胁迫 |
| 生物胁迫 | Biotic Stress (BIS) | 生物因素引起的胁迫类型 | 螟虫、蚜虫 |

### 2.2 关系抽取任务

| 关系名称 | 英文（缩写） | 关系类型| 说明 | 示例 |
|----------|-------------|----------------------|------|------|
| 作物-包含品种 | has_variety (HV) | (CROP, VAR) | 品种属于某作物 | 晋谷21号属于谷子 |
| 品种-采用育种方法 | uses_breeding_method (UBM) | (VAR, BM) | 品种选育所用方法 | 晋谷21号采用杂交育种 |
| 品种-具有性状 | has_trait (HT) | (VAR, TRT) | 品种具备或关注某性状 | 晋谷21号具有抗倒伏 |
| 非生物胁迫-影响性状 | affects_trait (AT) | (ABS, TRT) | 非生物胁迫对性状产生影响 | 干旱胁迫影响产量 |
| 性状-发生于生育时期 | trait_measured_at_stage (TMAS) | (TRT, GST) | 性状在某时期测定 | 千粒重测定于成熟期 |
| 非生物胁迫-发生于生育时期 | stress_occurs_at_stage (SOAS) | (ABS, GST) | 胁迫发生阶段 | 低温胁迫发生于拔节期 |
| QTL-关联性状 | qtl_associated_trait (QAT) | (QTL, TRT) | QTL对应目标性状 | qPH3.1关联株高 |
| 基因-影响性状 | gene_affects_trait (GAT) | (GENE, TRT) | 基因调控性状 | Waxy影响直链淀粉含量 |
| 分子标记-关联性状 | marker_associated_trait (MAT) | (MRK, TRT) | 标记与性状关联 | SNP_rs12345关联抗旱性 |
| 分子标记-定位于QTL | marker_in_qtl (MIQ) | (MRK, QTL) | 标记指示或位于QTL | KASP_Chr2_15Mb定位于qYLD2.2 |
| QTL-位于染色体 | qtl_on_chromosome (QOC) | (QTL, CHR) | QTL所在染色体 | qPH3.1位于Chr3 |
| 分子标记-位于染色体 | marker_on_chromosome (MOC) | (MRK, CHR) | 标记所在染色体 | SNP_rs12345位于Chr2 |
| 基因-位于染色体 | gene_on_chromosome (GOC) | (GENE, CHR) | 基因所在染色体 | DREB位于Chr1 |
| 品种-抗生物胁迫 | resistant_to_biotic_stress (RTP) | (VAR, BIS) | 品种抗病虫害 | 晋谷21号抗蚜虫 |
| 生物胁迫-发生于生育时期 | biotic_stress_occurs_at_stage (POAS) | (BIS, GST) | 生物胁迫发生时期 | 螟虫发生于灌浆期 |

## 3 评价标准
本评测的两个任务均采用Precision、Recall 和 F1-Score作为评价指标。

## 4 评测赛程

- **2026年2月**：评测任务发布 & 宣传  
- **2026年4月1日**：训练集、测试A榜（验证集）数据发布  
- **2026年5月15日**：测试A榜 Leaderboard 发布  
- **2026年6月1日**：测试B榜（测试集）数据发布、Leaderboard 发布  
- **2026年6月30日**：评测任务结束  
- **2026年7月1日–9日**：任务组织者、获奖队伍撰写技术报告  
- **2026年7月10日**：提交技术报告  
- **2026年7月25日**：评测论文审稿 & 录用通知  
- **2026年8月15日**：Camera-ready 版本提交  
- **2026年9月15日**：论文排版 & 提交 ACL/CCL Anthology  
- **2026年10月**：会议召开

## 5 资助情况
本届评测将设置一、二、三等奖，由中国中文信息学会提供荣誉证书。
