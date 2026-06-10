# Concept Growth Subskill (CPA)

## Role

Guide CPA concepts to grow naturally from prior business problems. Every rule or method should appear as a necessary response to a limitation or gap in the existing business framework.

## Universal Template

For any CPA concept, reconstruct:

```markdown
## 当前商业问题

...

## 现有规则/方法的不足

...

## 新规则为什么必须出现

...

## 核心规则/方法

...

## 最小商业例子

...

## 它自然引出的下一个问题

...
```

Use this diagnostic sequence:

1. What business problem were we originally trying to solve?
2. What rules or methods did we already have?
3. Why were those rules or methods insufficient?
4. What new provision, entry, formula, or procedure do we need?
5. What is the simplest version of this new concept?
6. How can we test it with a concrete business case?
7. What new question or complexity does it create?

---

## CPA Subject Concept Chains

### 1. 会计 (Accounting)

```text
商业活动需要记录
↓
会计等式 (资产 = 负债 + 所有者权益)
↓
会计科目 (对会计等式的细化分类)
↓
借贷记账法 (有借必有贷，借贷必相等)
↓
会计分录 (每笔交易的借贷记录)
↓
会计凭证 (原始凭证 → 记账凭证)
↓
账簿 (总账、明细账)
↓
权责发生制 (何时确认收入/费用)
↓
期末调整 (应计、递延、摊销、折旧)
↓
结账与试算平衡
↓
财务报表 (资产负债表、利润表、现金流量表、所有者权益变动表)
```

**Growth Logic:**

- **商业活动 → 会计等式**: Without an accounting equation, there is no way to verify that the records are internally consistent. The equation is the self-checking mechanism: every resource must have a source.
- **会计等式 → 会计科目**: The equation is too coarse. We need to know not just "assets exist" but *which* assets (cash? inventory? equipment?).
- **会计科目 → 借贷记账法**: Having科目 names is not enough. We need a mechanical rule that ensures every transaction keeps the equation balanced. Debit-credit is that double-entry rule.
- **借贷记账法 → 会计分录**: The debit-credit rule needs to be applied concretely to each transaction. A journal entry is the atomic unit of this application.
- **会计分录 → 会计凭证**: Journal entries need documentary evidence. This is both a legal requirement and a practical necessity for audit trail.
- **会计凭证 → 账簿**: Individual凭证 are too granular. We need organized records (ledgers) that aggregate entries by account.
- **账簿 → 权责发生制**: Raw ledger entries based on cash timing do not match economic reality. Accrual accounting matches revenue and expenses to the period when economic activity actually occurs.
- **权责发生制 → 期末调整**: Accrual accounting means that at period end, we must adjust for unrecorded revenues, unrecorded expenses, prepaid items, and depreciation.
- **期末调整 → 结账与试算平衡**: After adjustments, we close temporary accounts and verify that debits still equal credits.
- **结账 → 财务报表**: The adjusted, closed ledger provides the data to produce the four financial statements, which is the ultimate output of the accounting system.

### 2. 审计 (Auditing)

```text
财务报表由管理者自己编制（存在动机偏差）
↓
需要独立第三方鉴证
↓
审计风险模型 (审计风险 = 重大错报风险 × 检查风险)
↓
重要性水平 (Materiality)
↓
风险评估程序 (了解被审计单位及环境)
↓
控制测试 (测试内部控制有效性)
↓
实质性程序 (直接验证账户余额和交易)
↓
审计证据 (充分性 + 适当性)
↓
审计工作底稿
↓
审计调整与审计差异
↓
审计报告 (无保留意见 / 保留意见 / 否定意见 / 无法表示意见)
```

**Growth Logic:**

- **管理者动机偏差 → 独立鉴证需求**: Management prepares its own report card (financial statements). This structural conflict of interest creates demand for independent verification.
- **独立鉴证 → 审计风险模型**: The auditor cannot check everything, so s/he must manage risk. The model quantifies: "risk of wrong opinion = risk that material errors exist × risk that I fail to find them."
- **审计风险模型 → 重要性水平**: Risk management requires defining what "material" means. Materiality is the magnitude of misstatement that would influence a reasonable user's decision.
- **重要性水平 → 风险评估程序**: Before designing substantive tests, the auditor must understand where risks are highest — what could go wrong at the entity level.
- **风险评估 → 控制测试**: If internal controls appear strong, the auditor can test those controls rather than doing 100% substantive checking.
- **控制测试 → 实质性程序**: Whether controls are strong or weak, some direct testing of account balances and transactions is always required.
- **实质性程序 → 审计证据**: The output of audit procedures is evidence. Evidence must be both sufficient (quantity) and appropriate (quality = relevance + reliability).
- **审计证据 → 审计工作底稿**: Evidence must be documented so another auditor could understand what was done and why.
- **工作底稿 → 审计调整与差异**: Evidence may reveal misstatements. Uncorrected misstatements are evaluated against materiality.
- **审计差异 → 审计报告**: The culmination: based on all evidence and adjustments, the auditor issues an opinion on the financial statements.

### 3. 财务成本管理 (Financial Management)

```text
企业面临投融资决策
↓
货币时间价值 (今天的 1 元 ≠ 明天的 1 元)
↓
风险与收益权衡
↓
资本资产定价模型 (CAPM)
↓
债券与股票估值
↓
资本预算 (NPV, IRR, 回收期)
↓
资本成本 (WACC)
↓
资本结构 (MM 理论)
↓
杠杆 (经营杠杆, 财务杠杆, 总杠杆)
↓
股利政策
```

**Growth Logic:**

- **投融资决策 → 货币时间价值**: Cash today can be invested to earn more cash tomorrow. Without time value, we cannot compare cash flows at different points in time.
- **货币时间价值 → 风险与收益**: Time value alone assumes a sure return. But in reality, investments carry risk, and rational investors demand higher expected returns for higher risk.
- **风险与收益 → CAPM**: How do we quantify the risk-return tradeoff for a specific asset? CAPM relates an asset's expected return to its systematic risk (beta) relative to the market.
- **CAPM → 债券与股票估值**: With a discount rate (from CAPM or similar), we can value any financial asset as the present value of its expected future cash flows.
- **估值 → 资本预算**: Firms need a systematic way to decide which projects to accept. NPV, IRR, and payback period are the decision tools.
- **资本预算 → 资本成本**: The discount rate for NPV is the firm's cost of capital — the minimum return required by all providers of capital (debt and equity holders).
- **资本成本 → 资本结构**: A firm's mix of debt vs equity affects its WACC. MM theory asks: does capital structure even matter? (Answer: yes, once taxes and bankruptcy costs enter.)
- **资本结构 → 杠杆**: Debt magnifies both returns (to equity holders) and risk. Operating leverage comes from fixed costs; financial leverage comes from fixed financing charges.
- **杠杆 → 股利政策**: Should the firm retain earnings (reinvest) or distribute them? The decision interacts with capital structure, taxes, and signaling.

### 4. 税法 (Tax Law)

```text
国家需要财政收入
↓
税收法定原则 (什么该征税由法律规定)
↓
税制要素 (纳税人、征税对象、税基、税率)
↓
增值税 (流转环节征收)
↓
消费税 (特定消费品加征)
↓
企业所得税 (对企业利润征税)
↓
应纳税所得额 (会计利润 → 税法利润的调整)
↓
个人所得税 (综合 + 分类)
↓
税收优惠与税收筹划
↓
税款征收与管理
```

**Growth Logic:**

- **财政需求 → 税收法定原则**: The power to tax must be constrained by law; otherwise, the state can arbitrarily confiscate property. This is the constitutional foundation.
- **税收法定 → 税制要素**: For any tax to be legally imposed, four elements must be clear: who pays (纳税人), on what (征税对象), from what base (税基), at what rate (税率).
- **税制要素 → 增值税**: The simplest form is a turnover tax — but that creates cascading (tax on tax). VAT solves this through input tax credit mechanism: each stage in the chain is taxed only on value added.
- **增值税 → 消费税**: VAT is broad-based. To discourage consumption of specific goods (tobacco, alcohol, luxury items) or to raise additional revenue, excise taxes are layered on top.
- **增值税 → 企业所得税**: Businesses are taxed on profits, not revenue. But "profit" for tax purposes ≠ accounting profit — hence the need for tax adjustments.
- **企业所得税 → 应纳税所得额**: The bridge from accounting profit to taxable income involves permanent differences (items never deductible/taxable) and temporary differences (timing differences → deferred tax).
- **企业所得税 → 个人所得税**: Similar logic applies to individuals, but with a hybrid model (comprehensive for labor income, classified for capital income).
- **税种 → 税收优惠**: Governments use tax preferences (reduced rates, exemptions, credits) as policy tools to incentivize behaviors (R&D, environmental investment, regional development).
- **所有税种 → 征收管理**: Tax law is only effective if there is a system to collect. This covers filing deadlines, payment methods, audits, penalties, and taxpayer rights.

### 5. 经济法 (Economic Law)

```text
商业活动需要法律框架界定权利义务
↓
法律关系 (主体、客体、内容)
↓
民事法律行为 (合同、代理)
↓
合同法 (合同的订立、效力、履行、终止、违约责任)
↓
物权法 (所有权、用益物权、担保物权)
↓
公司法 (公司设立、组织机构、股权、合并分立、解散清算)
↓
证券法 (发行与交易、信息披露、禁止行为)
↓
破产法 (破产申请、管理人、债权确认、重整与清算)
```

**Growth Logic:**

- **商业活动 → 法律关系**: Every business interaction creates legal relationships. Without a framework to define who can do what, commerce collapses into disputes.
- **法律关系 → 民事法律行为**: Legal relationships don't form automatically. They arise from juristic acts — primarily contracts and authorized agency.
- **民事法律行为 → 合同法**: Contracts are the engine of commerce. Contract law provides the default rules: how contracts form, when they bind, what happens on breach.
- **合同法 → 物权法**: Contracts create obligations, but property rights define ownership. 物权法 answers: "Who owns this thing, and what can they do with it?"
- **物权法 → 公司法**: Natural persons alone cannot scale business. The corporation is a legal fiction that pools capital, limits liability, and separates ownership from management.
- **公司法 → 证券法**: When companies raise capital from the public, investors need protection against fraud and insider abuse. Securities law mandates disclosure and prohibits manipulation.
- **公司法 → 破产法**: When a corporation cannot pay its debts, normal contract and property remedies fail. Bankruptcy provides a collective, orderly process for creditor recovery or business rehabilitation.

### 6. 公司战略与风险管理 (Strategy & Risk)

```text
企业需要在不确定环境中做出方向选择
↓
战略分析 (宏观环境 & 产业环境 & 内部能力)
↓
SWOT 分析
↓
总体战略 (发展战略 vs 稳定战略 vs 收缩战略)
↓
竞争战略 (成本领先 vs 差异化 vs 集中化)
↓
职能战略 (营销、研发、人力资源、财务……)
↓
战略实施 (组织结构、企业文化、预算与控制)
↓
风险识别与评估
↓
风险应对 (规避、转移、承担、控制)
↓
内部控制 (COSO 框架)
```

**Growth Logic:**

- **不确定环境 → 战略分析**: Before making any decision, the firm must understand its environment. PESTEL (macro), Porter's Five Forces (industry), and VRIO (internal) are the analytical lenses.
- **战略分析 → SWOT**: The three analyses converge into a structured summary: Strengths, Weaknesses (internal), Opportunities, Threats (external).
- **SWOT → 总体战略**: The highest-level choice: grow, hold steady, or shrink. This is the company's direction.
- **总体战略 → 竞争战略**: Within the chosen direction, how does the firm beat competitors? Porter's generic strategies are the classic answer.
- **竞争战略 → 职能战略**: Strategy must cascade to each business function. Marketing, R&D, HR, and finance all need aligned sub-strategies.
- **战略制定 → 战略实施**: A brilliant strategy poorly executed is worthless. Implementation requires the right structure, culture, and control systems.
- **实施 → 风险识别**: As strategy executes, uncertainties surface. What could go wrong? Systematic risk identification is the first step.
- **风险识别 → 风险应对**: Once risks are known, the firm must decide how to handle each one. The four classic responses: avoid, transfer, accept, mitigate.
- **风险应对 → 内部控制**: Risk mitigation at scale requires a formal internal control system. COSO provides the framework: control environment, risk assessment, control activities, information & communication, monitoring.

---

## Expansion Rules

When asked to expand a CPA concept into a framework:

- Give a concept chain, not a textbook chapter outline.
- Explain **why** each next concept becomes necessary — what business problem or regulatory gap does it fill?
- Mark the user's current concept and the next learning question.
- Keep the chain compact unless the user asks for full notes.
- Each CPA subject has its own starting problem and growth logic — do not force a single template across all six subjects.
