---
name: prioritization-frameworks
description: "包含 9 种优先级框架的参考指南，提供公式、使用时机说明及模板——RICE、ICE、Kano 模型、MoSCoW、机会评分等。适用于选择优先级方法、比较 RICE 与 ICE 等框架，或学习不同优先级方法的工作原理。"
---

## 优先级框架参考指南

帮助你选择并应用适合当前场景的优先级框架。

### Core Principle（核心原则）

永远不要让客户来设计解决方案。优先处理**问题（机会）**，而非功能。

### Opportunity Score（机会评分，Dan Olsen，《The Lean Product Playbook》）

推荐用于客户问题优先级排序的框架。

对每个需求向客户调研**重要性**和**满意度**（归一化至 0-1 范围）。

三个相关公式：
- **当前价值** = 重要性 × 满意度
- **机会评分** = 重要性 × （1 - 满意度）
- **为客户创造的价值** = 重要性 × （S2 - S1），其中 S1 = 改进前满意度，S2 = 改进后满意度

高重要性 + 低满意度 = 最高机会评分 = 最佳机会。在重要性 vs 满意度图表上绘制——左上象限是黄金区域。优先处理客户问题，而非解决方案。

### ICE Framework（ICE 框架）

适用于计划和想法的优先级排序，不仅考虑价值，还考虑风险和经济因素。

- **I**（影响力 Impact）= 机会评分 × 受影响的客户数量
- **C**（置信度 Confidence）= 我们有多确定？（1-10）代表风险因素。
- **E**（简易度 Ease）= 实施难度如何？（1-10）代表经济因素。

**评分** = I × C × E。分数越高，优先级越高。

### RICE Framework（RICE 框架）

将 ICE 的影响力拆分为两个独立因素，适合需要更细粒度分析的较大团队。

- **R**（覆盖范围 Reach）= 受影响的客户数量
- **I**（影响力 Impact）= 机会评分（每位客户的价值）
- **C**（置信度 Confidence）= 我们有多确定？（0-100%）
- **E**（工作量 Effort）= 实施工作量？（人月）

**评分** = （R × I × C）/ E

### 9 Frameworks Overview（9 种框架概览）

| 框架 | 最适用场景 | 核心洞察 |
|------|---------|---------|
| 艾森豪威尔矩阵 | 个人任务 | 紧急 vs 重要——适用于 PM 个人任务管理 |
| 影响力 vs 工作量 | 任务/计划 | 简单 2×2——快速分类，不适合战略决策 |
| 风险 vs 回报 | 计划 | 类似影响力 vs 工作量，但考虑了不确定性 |
| **机会评分** | 客户问题 | **推荐。** 重要性 × （1 - 满意度）。归一化至 0-1。 |
| Kano 模型 | 理解用户期望 | 必备型、期望型、兴奋型、无差异型、反向型。用于理解，而非优先排序。 |
| 加权决策矩阵 | 多因素决策 | 对标准赋权，对每个选项打分。适合获得干系人认同。 |
| **ICE** | 想法/计划 | 影响力 × 置信度 × 简易度。推荐用于快速优先排序。 |
| **RICE** | 规模化的想法 | （覆盖范围 × 影响力 × 置信度）/ 工作量。在 ICE 基础上增加覆盖范围。 |
| MoSCoW | 需求 | 必须有/应该有/可以有/不会有。注意：源自项目管理领域。 |

### Templates（模板）

- [机会评分入门（PDF）](https://drive.google.com/file/d/1ENbYPmk1i1AKO7UnfyTuULL5GucTVufW/view)
- [重要性 vs 满意度模板——Dan Olsen（Google Slides）](https://docs.google.com/presentation/d/1jg-LuF_3QHsf6f1nE1f98i4C0aulnRNMOO1jftgti8M/edit#slide=id.g796641d975_0_3)
- [ICE 模板（Google Sheets）](https://docs.google.com/spreadsheets/d/1LUfnsPolhZgm7X2oij-7EUe0CJT-Dwr-/edit?usp=share_link&ouid=111307342557889008106&rtpof=true&sd=true)
- [RICE 模板（Google Sheets）](https://docs.google.com/spreadsheets/d/1S-6QpyOz5MCrV7B67LUWdZkAzn38Eahv/edit?usp=sharing&ouid=111307342557889008106&rtpof=true&sd=true)

---

### Further Reading（延伸阅读）

- [产品管理框架大全 + 模板](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [Kano 模型：如何在不成为功能工厂的情况下让客户满意](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [持续产品探索大师课（CPDM）](https://www.productcompass.pm/p/cpdm)（视频课程）
