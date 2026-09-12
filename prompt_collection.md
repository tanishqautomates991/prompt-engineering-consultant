# Prompt Collection

This document catalogs the prompting strategies utilized during the assessment.

## 1. Linear Chain-of-Thought (CoT) Prompt Template

**Purpose:** Used for deep diagnostic and root-cause analysis by forcing the model to break down complex operational issues sequentially.

**Template:**
```text
You are a top-tier business consultant analyzing {company_name}.
Current situation: {problem_context}.

Please perform a diagnostic analysis by thinking step-by-step:
1. Review the primary symptoms in {domain}.
2. Trace these symptoms back to potential operational failures.
3. Identify key bottlenecks, specifically addressing {bottleneck_1} and {bottleneck_2}.
4. Synthesize these into a single critical root-cause bottleneck.
5. Perform a gap analysis between {current_state} and {optimized_state}.
6. Provide a final recommendation.
```

## 2. Multi-branch Tree-of-Thought (ToT) Prompt Template

**Purpose:** Used to explore, evaluate, and compare distinct strategic paths simultaneously before converging on a single recommendation.

**Template:**
```text
You are an executive strategist deciding the future of {company_name}.
We must evaluate exactly three distinct strategic branches:
- Branch A — E-Commerce & Logistics Overhaul
- Branch B — Retail Footprint Downsizing
- Branch C — Hybrid B2B Licensing

For each branch, explore the potential outcomes by evaluating:
- Margin Impact: {margin_impact_context}
- CapEx: {capex_context}
- Risk: {risk_context}

After analyzing all three branches, score them against {decision_criteria} and conclude which branch offers the highest strategic value. Do not invent a fourth branch.
```

## Practical Difference Between CoT and ToT
- **Linear Chain-of-Thought (CoT):** CoT forces a model to proceed down a single, sequential path of logic (A → B → C → Conclusion). It is highly effective for deep-diving into a single problem, such as diagnosing a specific root cause or tracing a logical sequence of events.
- **Multi-branch Tree-of-Thought (ToT):** ToT requires the model to actively branch out into multiple, parallel possibilities (Branch A, Branch B, Branch C), evaluate each branch independently against specific criteria, and then compare them to make an optimal selection. It is superior for complex decision-making where multiple viable strategies exist.
