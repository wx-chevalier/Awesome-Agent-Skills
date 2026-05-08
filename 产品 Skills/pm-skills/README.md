![GitHub stars](https://img.shields.io/github/stars/phuryn/pm-skills)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](https://github.com/phuryn/pm-skills/blob/main/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](https://github.com/phuryn/pm-skills/blob/main/CONTRIBUTING.md)

# PM Skills Marketplace（简体中文版）：助你做出更好产品决策的 AI 操作系统

> 本项目是 [pm-skills](https://github.com/phuryn/pm-skills/) 的简体中文翻译版。原始项目由 [Paweł Huryn](https://www.productcompass.pm) 创建和维护。

> 8 个插件，65 个 PM 技能，36 个链式工作流。支持 Claude Code、Cowork 等。从发现到策略、执行、发布和增长，全链路覆盖。

![插件概览](.docs/images/plugins-overview.webp)

专为 Claude Code 和 Cowork 设计。技能亦兼容其他 AI 助手。

## 快速开始

有新想法？→ `/discover`
需要策略清晰度？→ `/strategy`
写 PRD？→ `/write-prd`
规划产品发布？→ `/plan-launch`
定义指标？→ `/north-star`

如果这个项目对你有帮助，请给仓库点个 ⭐。

## 为什么选择 PM Skills Marketplace？

通用 AI 给你的只是文本。PM Skills Marketplace 给你的是**结构**。

每个技能都编码了一个经过验证的产品管理框架——发现、假设映射、优先级排序、策略——并引导你一步步完成。你可以将 Teresa Torres、Marty Cagan 和 Alberto Savoia 的严谨方法融入日常工作流，而不是让它们在书架上落灰。

结果：更好的产品决策，而不仅仅是更快的文档。

## 运作原理（技能、命令、插件）

**技能（Skills）** 是 Marketplace 的基础构件。每个技能为 Claude 提供特定 PM 任务的领域知识、分析框架或引导式工作流。部分技能也作为可复用的基础模块，供多个命令共享。

技能在与对话相关时会**自动加载**——无需显式调用。如需强制加载（例如优先使用技能而非通用知识），可使用 `/plugin-name:skill-name` 或 `/skill-name`（Claude 会自动添加前缀）。

**命令（Commands）** 是用户触发的工作流，通过 `/command-name` 调用。它们将一个或多个技能串联成端到端流程。例如，`/discover` 串联了四个技能：brainstorm-ideas → identify-assumptions → prioritize-assumptions → brainstorm-experiments。

**插件（Plugins）** 将相关的技能和命令打包为可安装的包。每个插件覆盖一个 PM 领域——发现、策略、执行等。安装 Marketplace 即可一次获得全部 8 个插件。

![技能运作方式](.docs/images/how-skills-work.webp)

命令使用技能。部分技能服务于多个命令。有些技能（如 `prioritization-frameworks` 或 `opportunity-solution-tree`）是独立的参考资料，Claude 会在相关时自动引用——无需命令触发。

命令之间设计为环环相扣，匹配产品管理工作流。每个命令完成后，都会建议相关的下一步命令——跟着提示走就行。

## 安装

### Claude Cowork（推荐非开发者使用）

1. 打开 **Customize**（左下角）
2. 进入 **Browse plugins** → **Personal** → **+**
3. 选择 **Add marketplace from GitHub**
4. 输入：`phuryn/pm-skills`

全部 8 个插件自动安装。你将同时获得命令（`/discover`、`/strategy` 等）和技能。

![在 Claude Cowork 中安装 PM Skills](.docs/images/pm-skills-install.gif)

### Claude Code（CLI）

```bash
# 第 1 步：添加 marketplace
claude plugin marketplace add phuryn/pm-skills

# 第 2 步：安装各个插件
claude plugin install pm-toolkit@pm-skills
claude plugin install pm-product-strategy@pm-skills
claude plugin install pm-product-discovery@pm-skills
claude plugin install pm-market-research@pm-skills
claude plugin install pm-data-analytics@pm-skills
claude plugin install pm-marketing-growth@pm-skills
claude plugin install pm-go-to-market@pm-skills
claude plugin install pm-execution@pm-skills
```

### 其他 AI 助手（仅技能）

`skills/*/SKILL.md` 文件遵循通用技能格式，适用于任何能读取该格式的工具。命令（`/slash-commands`）是 Claude 专属功能。

| 工具 | 使用方式 | 支持内容 |
|------|----------|----------|
| **Gemini CLI** | 将技能文件夹复制到 `.gemini/skills/` | 仅技能 |
| **OpenCode** | 将技能文件夹复制到 `.opencode/skills/` | 仅技能 |
| **Cursor** | 将技能文件夹复制到 `.cursor/skills/` | 仅技能 |
| **Codex CLI** | 将技能文件夹复制到 `.codex/skills/` | 仅技能 |
| **Kiro** | 将技能文件夹复制到 `.kiro/skills/` | 仅技能 |

```bash
# 示例：为 OpenCode 复制所有技能（项目级别）
for plugin in pm-*/; do
  mkdir -p .opencode/skills/
  cp -r "$plugin/skills/"* .opencode/skills/ 2>/dev/null
done

# 示例：为 Gemini CLI 复制所有技能（全局级别）
for plugin in pm-*/; do
  cp -r "$plugin/skills/"* ~/.gemini/skills/ 2>/dev/null
done
```

---

## 可用插件

<details>
<summary><strong>1. pm-product-discovery</strong> — 创意构思、实验设计、假设验证、OST、客户访谈（13 个技能，5 个命令）</summary>

**技能（13）：**

- `brainstorm-ideas-existing` — 现有产品的多视角创意构思（产品经理、设计师、工程师）
- `brainstorm-ideas-new` — 新产品初期发现阶段的创意构思
- `brainstorm-experiments-existing` — 为现有产品设计假设验证实验
- `brainstorm-experiments-new` — 为新产品设计精益创业预型实验（Alberto Savoia）
- `identify-assumptions-existing` — 识别价值、可用性、可行性和商业可行性维度的风险假设
- `identify-assumptions-new` — 识别 8 个风险类别的假设，包括市场进入、策略和团队
- `prioritize-assumptions` — 使用影响力 × 风险矩阵排序假设，附带实验建议
- `prioritize-features` — 基于影响力、工作量、风险和策略一致性排序功能 backlog
- `analyze-feature-requests` — 按主题和策略匹配度分析、分类客户功能需求
- `opportunity-solution-tree` — 构建机会解决方案树（Teresa Torres）— 目标 → 机会 → 方案 → 实验
- `interview-script` — 创建结构化客户访谈脚本，包含 JTBD（待完成工作）探测问题
- `summarize-interview` — 将访谈记录总结为 JTBD、满意度信号和行动项
- `metrics-dashboard` — 设计产品指标仪表盘，包含北极星指标、输入指标和告警阈值

**命令（5）：**

- `/discover` — 完整发现周期：创意构思 → 假设映射 → 优先级排序 → 实验设计
- `/brainstorm` — 多视角创意构思（`ideas|experiments` × `existing|new`）
- `/triage-requests` — 分析和排序一批功能需求
- `/interview` — 准备访谈脚本或总结访谈记录（`prep|summarize`）
- `/setup-metrics` — 设计产品指标仪表盘

**示例：**

技能：
- `我们的 AI 写作助手创意最大的风险假设是什么？`
- `帮我为提升用户激活率构建一棵机会解决方案树`
- `排序这 12 个来自企业客户的功能需求 [附 CSV]`

命令：
- `/discover 面向远程团队的 AI 会议摘要工具`
- `/brainstorm experiments existing — 我们需要降低新手引导流程的流失率`
- `/interview prep — 我们正在访谈企业采购人员，了解他们的采购工作流`

</details>

<details>
<summary><strong>2. pm-product-strategy</strong> — 愿景、商业模式、定价、竞争格局（12 个技能，5 个命令）</summary>

产品策略、愿景、商业模式、定价和宏观环境分析。涵盖从愿景制定到竞争格局扫描的完整策略工具箱。

**技能（12）：**

- `product-strategy` — 全面的 9 模块产品策略画布（愿景 → 护城河）
- `startup-canvas` — 创业画布，融合产品策略（9 模块）+ 商业模式——新产品的 BMC 和精益画布替代方案
- `product-vision` — 打造鼓舞人心、可实现且有感染力的产品愿景
- `value-proposition` — 6 要素 JTBD 价值主张（谁、为什么、之前怎样、如何、之后怎样、替代方案）
- `lean-canvas` — 面向创业公司和新产品的精益画布商业模式
- `business-model` — 包含全部 9 个构件的商业模式画布
- `monetization-strategy` — 头脑风暴 3-5 种商业化策略及验证实验
- `pricing-strategy` — 定价模型、竞品分析、支付意愿和价格弹性
- `swot-analysis` — SWOT 分析及可行动建议
- `pestle-analysis` — 宏观环境分析：政治、经济、社会、技术、法律、环境
- `porters-five-forces` — 竞争力量分析（行业竞争、供应商、买方、替代品、新进入者）
- `ansoff-matrix` — 跨市场和产品的增长策略映射

**命令（5）：**

- `/strategy` — 创建完整的 9 模块产品策略画布
- `/business-model` — 探索商业模式（`lean|full|startup|value-prop|all`）
- `/value-proposition` — 使用 6 要素 JTBD 模板设计价值主张
- `/market-scan` — 宏观环境分析，整合 SWOT + PESTLE + 波特五力 + 安索夫矩阵
- `/pricing` — 设计定价策略，包含竞品分析和验证实验

**示例：**

技能：
- `对比精益画布、商业模式画布和创业画布，我的平台型创业项目该用哪个？`
- `为面向非英语母语者的 AI 写作助手设计价值主张`
- `对项目管理 SaaS 市场做波特五力分析`

命令：
- `/strategy 面向代理公司的 B2B 项目管理工具`
- `/business-model startup — 面向非英语母语者的 AI 写作工具`
- `/value-proposition 面向企业客户的 SaaS 新手引导工具`

</details>

<details>
<summary><strong>3. pm-execution</strong> — PRD、OKR、路线图、Sprint、回顾、发布说明、干系人管理（15 个技能，10 个命令）</summary>

日常产品管理：PRD、OKR、路线图、Sprint、回顾会、发布说明、事前验尸、干系人管理、用户故事和优先级排序框架。

**技能（15）：**

- `create-prd` — 全面的 8 模块 PRD 模板
- `brainstorm-okrs` — 与公司目标对齐的团队级 OKR
- `outcome-roadmap` — 将功能列表转化为以成果为导向的路线图
- `sprint-plan` — Sprint 规划，包含产能估算、故事选择和风险识别
- `retro` — 结构化 Sprint 回顾会引导
- `release-notes` — 从 ticket、PRD 或 changelog 生成面向用户的发布说明
- `pre-mortem` — 使用老虎/纸老虎/大象分类法的风险分析
- `stakeholder-map` — 权力 × 利益矩阵及定制沟通计划
- `summarize-meeting` — 会议记录 → 决策 + 行动项
- `user-stories` — 遵循 3C 原则和 INVEST 标准的用户故事
- `job-stories` — 工作故事：当 [场景]，我想要 [动机]，从而可以 [结果]
- `wwas` — Why-What-Acceptance 格式的产品 backlog 条目
- `test-scenarios` — 测试场景：正常路径、边界情况、错误处理
- `dummy-dataset` — 生成 CSV、JSON、SQL 或 Python 格式的仿真数据集
- `prioritization-frameworks` — 9 种优先级排序框架参考指南（机会评分、ICE、RICE、MoSCoW、Kano 等）

**命令（10）：**

- `/write-prd` — 从功能创意或问题陈述创建 PRD
- `/plan-okrs` — 头脑风暴团队级 OKR
- `/transform-roadmap` — 将基于功能的路线图转换为以成果为导向
- `/sprint` — Sprint 生命周期（`plan|retro|release`）
- `/pre-mortem` — 对 PRD 或发布计划进行事前验尸风险分析
- `/meeting-notes` — 将会议记录总结为结构化笔记
- `/stakeholder-map` — 映射干系人并创建沟通计划
- `/write-stories` — 将功能拆解为 backlog 条目（`user|job|wwa`）
- `/test-scenarios` — 从用户故事生成测试场景
- `/generate-data` — 创建仿真数据集

**示例：**

技能：
- `50 个条目的 backlog 应该用哪个优先级排序框架？`
- `为平台迁移项目映射我们的干系人`
- `机会评分、ICE 和 RICE 有什么区别？`

命令：
- `/write-prd 减少告警疲劳的智能通知系统`
- `/sprint retro — 这是我们上个 Sprint 的笔记`
- `/write-stories job — 将"团队仪表盘"功能拆解为工作故事`

</details>

<details>
<summary><strong>4. pm-market-research</strong> — 用户画像、市场细分、旅程地图、市场规模估算、竞品分析（7 个技能，3 个命令）</summary>

用户研究与竞品分析：用户画像、市场细分、旅程地图、市场规模估算、竞品分析和反馈分析。

**技能（7）：**

- `user-personas` — 基于研究数据创建精细化用户画像
- `market-segments` — 识别 3-5 个客户细分，包含人口统计、JTBD 和产品匹配度
- `user-segmentation` — 基于行为、JTBD 和需求从反馈数据中细分用户
- `customer-journey-map` — 端到端旅程地图，包含阶段、触点、情绪和痛点
- `market-sizing` — TAM（总体有效市场）、SAM（可服务有效市场）、SOM（可获得服务市场），自上而下和自下而上两种方法
- `competitor-analysis` — 竞品优劣势及差异化机会
- `sentiment-analysis` — 用户反馈的情感分析和主题提取

**命令（3）：**

- `/research-users` — 构建用户画像、细分用户并绘制客户旅程
- `/competitive-analysis` — 分析竞争格局
- `/analyze-feedback` — 从用户反馈中进行情感分析和细分洞察

**示例：**

技能：
- `估算美国市场 AI 代码审查工具的 TAM/SAM/SOM`
- `为我们的电商结账流程创建客户旅程地图`
- `按行为和需求对这些调研受访者进行细分 [附 CSV]`

命令：
- `/research-users 我们有 12 位健身 App 用户的访谈数据`
- `/competitive-analysis 设计工具领域的 Figma 竞品`
- `/analyze-feedback 这是 Q4 的 200 条 NPS 反馈 [附文件]`

</details>

<details>
<summary><strong>5. pm-data-analytics</strong> — SQL 生成、群组分析、A/B 测试分析（3 个技能，3 个命令）</summary>

产品经理的数据分析：SQL 查询生成、群组分析和 A/B 测试分析。

**技能（3）：**

- `sql-queries` — 从自然语言生成 SQL（BigQuery、PostgreSQL、MySQL）
- `cohort-analysis` — 按群组分析留存曲线、功能采用率和参与度趋势
- `ab-test-analysis` — 统计显著性、样本量验证和发布/延长/停止建议

**命令（3）：**

- `/write-query` — 从自然语言生成 SQL 查询
- `/analyze-cohorts` — 对用户参与度数据进行群组分析
- `/analyze-test` — 分析 A/B 测试结果

**示例：**

技能：
- `95% 置信度、2% MDE 的情况下需要多大的样本量？`
- `订阅制应用应该跟踪哪些留存指标？`

命令：
- `/write-query 展示 2025 年 Q4 各国月活用户数（BigQuery）`
- `/analyze-test 这是我们结账流程 A/B 测试的结果 [附 CSV]`
- `/analyze-cohorts 1 月和 2 月注册用户的周留存对比`

</details>

<details>
<summary><strong>6. pm-go-to-market</strong> — 桥头堡市场、理想客户画像、消息传递、增长循环、GTM 动作、竞争作战卡（6 个技能，3 个命令）</summary>

市场进入策略：桥头堡市场、理想客户画像、消息传递、增长循环、GTM 动作和竞争作战卡。

**技能（6）：**

- `gtm-strategy` — 完整 GTM 策略：渠道、消息传递、成功指标和发布计划
- `beachhead-segment` — 识别首个桥头堡市场细分
- `ideal-customer-profile` — 理想客户画像（ICP），包含人口统计、行为、JTBD 和需求
- `growth-loops` — 设计可持续的增长循环
- `gtm-motions` — 评估 GTM 动作和工具（产品驱动、销售驱动等）
- `competitive-battlecard` — 销售就绪的竞争作战卡，包含异议处理和赢单策略

**命令（3）：**

- `/plan-launch` — 从桥头堡市场到发布计划的完整 GTM 策略
- `/growth-strategy` — 设计增长循环并评估 GTM 动作
- `/battlecard` — 创建竞争作战卡

**示例：**

技能：
- `开发者生产力工具最佳的桥头堡市场细分是什么？`
- `为带有免费增值层级的 B2B SaaS 设计增长循环`
- `为 AI 驱动的 HR 筛选平台定义 ICP`

命令：
- `/plan-launch 面向中型工程团队的 AI 代码审查工具`
- `/battlecard 我们的 CRM vs Salesforce（SMB 市场）`
- `/growth-strategy 连接自由职业者和创业公司的双边市场`

</details>

<details>
<summary><strong>7. pm-marketing-growth</strong> — 营销创意、定位、价值主张、命名、北极星指标（5 个技能，2 个命令）</summary>

产品营销与增长：营销创意、定位策略、价值主张陈述、产品命名和北极星指标。

**技能（5）：**

- `marketing-ideas` — 创意且高性价比的营销方案，包含渠道和消息策略
- `positioning-ideas` — 区别于竞品的产品定位策略
- `value-prop-statements` — 用于营销、销售和新手引导的价值主张陈述
- `product-name` — 与品牌价值观和目标受众一致的产品命名头脑风暴
- `north-star-metric` — 北极星指标 + 输入指标，附带业务博弈分类

**命令（2）：**

- `/market-product` — 头脑风暴营销创意、定位、价值主张和产品命名
- `/north-star` — 定义你的北极星指标和支撑性输入指标

**示例：**

技能：
- `头脑风暴 5 个区别于 Notion 的定位角度`
- `双边市场适合什么北极星指标？`
- `为销售团队的 pitch deck 生成价值主张陈述`

命令：
- `/market-product 面向电商管理者的 B2B 分析仪表盘`
- `/north-star 连接自由职业者和客户的双边市场`

</details>

<details>
<summary><strong>8. pm-toolkit</strong> — 简历审核、法律文档、校对（4 个技能，5 个命令）</summary>

核心产品工作之外的 PM 实用工具：简历审核、法律文档和校对。

**技能（4）：**

- `review-resume` — PM 简历审核和优化，基于 10 条最佳实践（XYZ+S 公式、关键词、结构）
- `draft-nda` — 保密协议（NDA），包含适用司法管辖区的条款
- `privacy-policy` — 符合 GDPR/CCPA 合规要求的隐私政策
- `grammar-check` — 语法、逻辑和行文检查，提供针对性修改建议

**命令（5）：**

- `/review-resume` — 全面的 PM 简历审核
- `/tailor-resume` — 根据特定职位描述定制简历
- `/draft-nda` — 起草保密协议
- `/privacy-policy` — 起草隐私政策
- `/proofread` — 检查语法、逻辑和行文

**示例：**

技能：
- `按照最佳实践审核我的 PM 简历 [附 PDF]`
- `检查这篇产品公告的语法和清晰度`

命令：
- `/review-resume [附上你的 PM 简历]`
- `/tailor-resume [附简历 + 粘贴职位描述]`
- `/proofread 这是我们 Q1 投资者更新的草稿`

</details>

---

## 关于

这个 Marketplace 随着产品管理实践和 AI 能力的发展而持续进化。

精选技能基于以下作者的工作：

- Teresa Torres — [*Continuous Discovery Habits*](https://www.amazon.com/Continuous-Discovery-Habits-Discover-Products/dp/1736633309/)（《持续发现习惯》）
- Marty Cagan — [*INSPIRED*](https://www.amazon.com/INSPIRED-Create-Tech-Products-Customers/dp/1119387507/)（《启示录》）和 [*TRANSFORMED*](https://www.amazon.com/dp/1119697336/)（《转型》）
- Alberto Savoia — [*The Right It*](https://www.amazon.com/Right-Many-Ideas-Yours-Succeed/dp/0062884654)（《正确的它》）
- Dan Olsen — [*The Lean Product Playbook*](https://www.amazon.com/dp/1118960874/)（《精益产品开发手册》）
- Roger L. Martin — [*Playing to Win*](https://www.amazon.com/Playing-Win-Expanded-Bonus-Articles/dp/B0F25SDYWV/)（《玩出胜利》）
- Ash Maurya — [*Running Lean*](https://www.amazon.com/dp/B004J4XGN6/)（《精益实战》）
- Strategyzer — [*Business Model Generation*](https://www.amazon.com/dp/0470876417/)（《商业模式新生代》）和 [*Value Proposition Design*](https://www.amazon.com/dp/1118968050/)（《价值主张设计》）
- Christina Wodtke — [*Radical Focus*](https://www.amazon.com/Radical-Focus-Achieving-Important-Objectives/dp/0996006052)（《彻底聚焦》）
- Anthony W. Ulwick — [*Jobs to Be Done*](https://jobs-to-be-done-book.com/)（《待完成工作》）
- Alistair Croll & Benjamin Yoskovitz — [*Lean Analytics*](https://www.amazon.com/Lean-Analytics-Better-Startup-Faster/dp/1449335675/)（《精益数据分析》）
- Sean Ellis — [*Hacking Growth*](https://www.amazon.com/Hacking-Growth-Fastest-Growing-Companies-Breakout/dp/045149721X/)（《增长黑客》）
- Maja Voje — [*Go-To-Market Strategist*](https://gtmstrategist.com/)（《市场进入策略师》）

由 Paweł Huryn 从 [The Product Compass Newsletter](https://www.productcompass.pm) 精选整理。

## 贡献

参见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## Windows 已知问题

如果你的 Cowork 不稳定且无法启动 VM（[claude-code/issues/27010](https://github.com/anthropics/claude-code/issues/27010)），可以尝试：

```powershell
$action = New-ScheduledTaskAction -Execute "powershell.exe" -Argument "-WindowStyle Hidden -Command `"if ((Get-Service CoworkVMService).Status -ne 'Running') { Start-Service CoworkVMService }`""

$trigger = New-ScheduledTaskTrigger -RepetitionInterval (New-TimeSpan -Minutes 1) -Once -At (Get-Date)

$settings = New-ScheduledTaskSettingsSet -AllowStartIfOnBatteries -DontStopIfGoingOnBatteries

Register-ScheduledTask -TaskName "CoworkVMServiceMonitor" `
  -Action $action `
  -Trigger $trigger `
  -Settings $settings `
  -RunLevel Highest `
  -User "SYSTEM"
```

这可以解决 Windows 上 90% 的问题。
剩余 10%：打开 services.msc > 手动启动 "Claude" 服务

## 许可证

MIT — 参见 [LICENSE](LICENSE)。
