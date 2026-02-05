---
name: prompt-evaluator
description: |
  Comprehensive evaluation framework for system prompts and AI assistant prompts.
---

# Prompt Evaluator

A comprehensive framework for evaluating, comparing, and debugging system prompts for AI assistants.

  
  CAPABILITIES:
  1. Single prompt scoring: Evaluate a prompt across 15 dimensions with detailed scores, issues, and specific fix recommendations
  2. Multi-prompt comparison: Compare 2-5 prompts side-by-side with ranking table and improvement roadmap
  3. Feedback analysis: Analyze user feedback, bug reports, or improvement suggestions to determine if issues are prompt-related and provide actionable fixes
  
  TRIGGERS - Use this skill when:
  - User asks to "evaluate", "score", "rate", or "review" a prompt
  - User asks to "compare prompts", "which prompt is better", or "A/B test prompts"
  - User provides feedback/complaints about AI behavior and asks if it's a prompt issue
  - User asks "what's wrong with this prompt", "how to improve this prompt"
  - User mentions "system prompt", "inner prompt", "built-in prompt", "assistant prompt"
  - User asks about prompt quality, prompt optimization, or prompt debugging
  - Keywords: prompt evaluation, prompt scoring, prompt comparison, prompt analysis, prompt review
  
  OUTPUT: Structured evaluation report with scores, issues, fixes, and priority recommendations.


## Quick Start

### Mode 1: Single Prompt Evaluation
```
Input: One prompt (text or file)
Output: 15-dimension score card + prioritized fix recommendations
```

### Mode 2: Multi-Prompt Comparison
```
Input: 2-5 prompts to compare
Output: Comparison table + winner analysis + improvement roadmap
```

### Mode 3: Feedback Analysis
```
Input: User feedback/complaints + current prompt
Output: Root cause analysis + prompt-specific fixes (if applicable)
```

---

## Evaluation Framework

### 15 Evaluation Dimensions

Load `references/dimensions.md` for the complete scoring rubric. Summary:

| # | Dimension | Weight | Key Question |
|---|-----------|--------|--------------|
| 1 | Role Definition | 6% | Is the AI's identity and persona clearly defined? |
| 2 | Task Clarity | 10% | Is the primary task unambiguous? |
| 3 | Constraint Completeness | 10% | Are DO/DON'T rules comprehensive? |
| 4 | Output Format | 8% | Is the expected output format specified? |
| 5 | Example Quality | 8% | Are examples concrete and representative? |
| 6 | Edge Case Handling | 10% | Are boundary conditions addressed? |
| 7 | Business Alignment | 10% | Does it serve business goals? |
| 8 | User Experience | 8% | Does it create good UX? |
| 9 | Safety & Ethics | 8% | Are safety guardrails in place? |
| 10 | Maintainability | 5% | Is it modular and easy to update? |
| 11 | Token Efficiency | 4% | Is context used efficiently? |
| 12 | Robustness | 5% | Is it resistant to misuse/injection? |
| 13 | Consistency | 3% | Are rules internally consistent? |
| 14 | Internationalization | 2% | Does it handle multiple languages? |
| 15 | Measurability | 3% | Can outcomes be measured? |

---

## Mode 1: Single Prompt Evaluation

### Input Requirements
- The prompt to evaluate (as text, file, or pasted content)
- Optional: Context about the product/use case
- Optional: Known issues or user complaints

### Evaluation Process

**STEP 1: Initial Scan**
- Count total lines and estimate tokens
- Identify structural elements (sections, headers, examples)
- Detect language(s) used

**STEP 2: Dimension-by-Dimension Scoring**
For each of the 15 dimensions:
1. Score 1-10 based on rubric in `references/dimensions.md`
2. Identify specific issues (quote line numbers)
3. Classify severity: 🔴 Critical / 🟡 Warning / 🟢 Minor
4. Provide concrete fix recommendation

**STEP 3: Calculate Weighted Score**
```
Total Score = Σ (dimension_score × weight) × 10
```

**STEP 4: Generate Report**

Output format:
```markdown
# Prompt Evaluation Report

## Summary
| Metric | Value |
|--------|-------|
| Total Score | XX/100 (Grade) |
| Lines | XXX |
| Est. Tokens | ~X,XXX |
| Critical Issues | X |
| Warnings | X |

## Score Breakdown
[15-dimension table with scores and brief notes]

## Critical Issues (🔴)
[Detailed issues with line references and fixes]

## Warnings (🟡)
[Detailed issues with line references and fixes]

## Top 3 Priority Fixes
1. [Most impactful fix with before/after example]
2. [Second priority fix]
3. [Third priority fix]

## Improvement Roadmap
[Ordered list of all recommended changes]
```

---

## Mode 2: Multi-Prompt Comparison

### Input Requirements
- 2-5 prompts to compare (labeled A, B, C, etc.)
- Optional: Evaluation focus (e.g., "focus on safety" or "focus on UX")

### Comparison Process

**STEP 1: Individual Evaluation**
Evaluate each prompt using Mode 1 (abbreviated)

**STEP 2: Head-to-Head Comparison**
For each dimension, compare all prompts and identify:
- Winner for that dimension
- Key differentiator

**STEP 3: Generate Comparison Report**

Output format:
```markdown
# Prompt Comparison Report

## Overall Ranking
| Rank | Prompt | Score | Strengths | Weaknesses |
|------|--------|-------|-----------|------------|
| 1 | [Name] | XX/100 | ... | ... |
| 2 | [Name] | XX/100 | ... | ... |

## Dimension-by-Dimension Comparison
| Dimension | Prompt A | Prompt B | Prompt C | Winner |
|-----------|----------|----------|----------|--------|
| Role Definition | 7 | 8 | 6 | B |
| Task Clarity | 9 | 7 | 8 | A |
| ... | ... | ... | ... | ... |

## Key Differentiators
[What makes the winner better in specific areas]

## Synthesis Recommendation
[How to combine the best elements of each prompt]

## Next Version Roadmap
[Prioritized improvements for the winning prompt]
```

---

## Mode 3: Feedback Analysis

### Input Requirements
- User feedback, complaints, or bug reports
- Current prompt being used
- Optional: Conversation logs showing the issue

### Analysis Process

**STEP 1: Classify Feedback**
Determine if the issue is:
- 🎯 **Prompt Issue**: Fixable by modifying the prompt
- ⚙️ **Backend Issue**: Requires code/data/infrastructure changes
- 🔄 **Hybrid Issue**: Needs both prompt and backend fixes
- ❌ **Not an Issue**: User misunderstanding or expected behavior

**STEP 2: Root Cause Analysis**
If prompt-related:
1. Identify which dimension(s) are failing
2. Locate specific rule gaps or conflicts
3. Trace the failure path

**STEP 3: Generate Analysis Report**

Output format:
```markdown
# Feedback Analysis Report

## Feedback Summary
| Item | Details |
|------|---------|
| Feedback Type | [Complaint/Bug/Suggestion] |
| Issue Classification | [Prompt/Backend/Hybrid/Not an Issue] |
| Confidence | [High/Medium/Low] |

## Root Cause Analysis
[Detailed explanation of why the issue occurs]

## Is This a Prompt Issue?
[YES/NO/PARTIAL with reasoning]

## Affected Dimensions
| Dimension | Current Score | Impact |
|-----------|---------------|--------|
| [Dimension] | X/10 | [How feedback relates] |

## Recommended Prompt Fixes
[If prompt-related, provide specific fixes with before/after]

## Backend Recommendations
[If backend-related, describe what needs to change]

## Validation Criteria
[How to verify the fix works]
```

---

## Grading Scale

| Score Range | Grade | Description |
|-------------|-------|-------------|
| 90-100 | A | Production-ready, minimal issues |
| 80-89 | B+ | Good quality, minor improvements needed |
| 70-79 | B | Functional, several improvements recommended |
| 60-69 | C | Needs significant work |
| 50-59 | D | Major issues, not recommended for production |
| <50 | F | Fundamental problems, requires rewrite |

---

## Common Anti-Patterns

When evaluating, watch for these red flags:

1. **Vague Role**: "You are a helpful assistant" (no specificity)
2. **Missing Constraints**: No DO NOT rules
3. **No Examples**: Abstract rules without concrete demonstrations
4. **Contradictory Rules**: Conflicting instructions
5. **Token Bloat**: Unnecessary repetition or verbose explanations
6. **No Safety Rails**: Missing content/behavior boundaries
7. **Hardcoded Values**: Values that should be dynamic
8. **No Fallback**: Missing error/edge case handling
9. **Monolithic Structure**: No modular sections
10. **Injection Vulnerability**: No protection against prompt attacks

See `references/anti-patterns.md` for detailed examples and fixes.

---

## Output Quality Standards

All evaluation outputs must:

1. **Be Actionable**: Every issue must have a specific fix recommendation
2. **Include Evidence**: Quote specific lines/sections from the prompt
3. **Prioritize**: Rank issues by impact (Critical > Warning > Minor)
4. **Provide Before/After**: Show concrete examples of recommended changes
5. **Be Measurable**: Include expected improvement metrics where possible
