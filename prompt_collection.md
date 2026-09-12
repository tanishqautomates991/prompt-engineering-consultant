# Prompt Collection

This document catalogs the prompting strategies utilized during the assessment. It distinguishes between the exact prompts executed for the Apex Retail Group case and the reusable, parameter-driven templates designed for future consulting scenarios.

---

## 1. APEX Diagnostic / Linear Chain-of-Thought (CoT)

**Purpose:** Used for deep diagnostic and root-cause analysis by forcing the model to break down complex operational issues sequentially.

### Exact Assessment Prompt / Execution Version (Exercise 2)
```text
Act as a Senior Management Consultant. We need to perform the ASSESS and PINPOINT

stages for our B2B retail client, Apex Retail Group.

[CLIENT METRICS]:

* 45 physical stores.
* Annual revenue: $12M. Margins down 15% due to inventory carry costs.
* Foot traffic down 25%.
* E-commerce conversion rate: 1.2%. Cart abandonment: 82%.
* Bottlenecks: Over-stocked warehouses, 5-7 days shipping, manual inventory tracking.

Let's think step-by-step to diagnose the situation:

1. Conduct a SWOT analysis based on the metrics.
2. Pinpoint the single most critical root-cause bottleneck. Explain your logic.
3. Generate a gap analysis comparing their current state with an optimized state.
```

### Parameter-Driven Reusable Template
```text
Act as a Senior Management Consultant. We need to perform the ASSESS and PINPOINT
stages for our client, [Insert Company Name].

[CLIENT METRICS]:
[Insert Client Metrics]

Let's think step-by-step to diagnose the situation:
1. Conduct a SWOT analysis based on the metrics.
2. Pinpoint the single most critical root-cause bottleneck. Explain your logic.
3. Generate a gap analysis comparing their current state with an optimized state.
```

---

## 2. Multi-branch Tree-of-Thought (ToT) Evaluation

**Purpose:** Used to explore, evaluate, and compare distinct strategic paths simultaneously before converging on a single recommendation.

### Exact Assessment Prompt / Execution Version (Exercise 3)
```text
We need to evaluate strategic solutions for Apex Retail Group. Generate three distinct
solution branches:

* Branch A: E-Commerce & Logistics Overhaul (Optimize online checkout, integrate
  automated inventory, and switch to 3PL shipping).

* Branch B: Retail Footprint Downsizing (Close the 15 lowest-performing stores,
  consolidate inventory, and reinvest capital).

* Branch C: Hybrid B2B Licensing (Franchise physical stores, license the brand, and
  pivot corporate focus to online wholesale).

Evaluate each branch in parallel. For each option, analyze:

1. Estimated Impact on Margins (High/Med/Low).
2. Capital Expenditure (CapEx) required (High/Med/Low).
3. Execution Risk.

Let's think step-by-step. Score each branch out of 10 and select the best candidate.
```

### Parameter-Driven Reusable Template
```text
We need to evaluate strategic solutions for [Insert Company Name]. Generate distinct
solution branches:

* [Insert Branch A Definition]
* [Insert Branch B Definition]
* [Insert Branch C Definition]

Evaluate each branch in parallel. For each option, analyze:
1. Estimated Impact on Margins (High/Med/Low).
2. Capital Expenditure (CapEx) required (High/Med/Low).
3. Execution Risk.

Let's think step-by-step. Score each branch out of 10 and select the best candidate.
```

---

## 3. Weighted Decision Matrix

**Purpose:** Quantitatively evaluates the winning ToT branch against other alternatives using strict scoring criteria.

### Parameter-Driven Reusable Template
```text
Act as a strategic analyst for [Insert Company Name]. Create a Weighted Decision Matrix for the following branches:
[Insert Evaluated Branches]

You must use exactly these four criteria and weights:
* ROI — 30%
* Low Execution Risk — 20%
* Implementation Speed — 20%
* Resource Alignment — 30%

Total weight must equal 100%.

For each branch, score each criterion from 1 to 10.
Calculate the results using exactly this formula:
Weighted Score = Raw Score × Criteria Weight

Output the results in a markdown table and state the final winner based on the highest calculated total.
```

---

## 4. 12-Month Roadmap / Planning

**Purpose:** Translates the winning strategic branch into a phased, actionable execution plan with defined milestones, accountabilities, and risks.

### Parameter-Driven Reusable Template
```text
Act as a Project Manager. Create an implementation roadmap for the selected strategy: [Insert Roadmap Strategy].

You must structure your response to simulate a two-stage planning process.

Stage 1:
Outline exactly 3 phases over a 12-month timeline.
Once the outline is complete, insert a SYSTEM PAUSE and wait for the user to type "Execute".

Stage 2:
After the user types "Execute", generate the following details for the 3 phases:
1. Detailed milestones.
2. A RACI matrix.
3. A separate Risk Log containing exactly these four columns:
| Risk Event | Probability (Low/Med/High) | Impact (Low/Med/High) | Mitigation Strategy |
```

---

## Practical Difference Between CoT and ToT
- **Linear Chain-of-Thought (CoT):** CoT forces a model to proceed down a single, sequential path of logic (A → B → C → Conclusion). It is highly effective for deep-diving into a single problem, such as diagnosing a specific root cause or tracing a logical sequence of events.
- **Multi-branch Tree-of-Thought (ToT):** ToT requires the model to actively branch out into multiple, parallel possibilities (Branch A, Branch B, Branch C), evaluate each branch independently against specific criteria, and then compare them to make an optimal selection. It is superior for complex decision-making where multiple viable strategies exist.
