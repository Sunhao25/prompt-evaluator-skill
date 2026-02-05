# Prompt Evaluation Report Templates

Ready-to-use output templates for each evaluation mode.

---

## Template 1: Single Prompt Evaluation Report

```markdown
# 📊 Prompt Evaluation Report

**Prompt Name**: [Name or identifier]
**Evaluation Date**: [Date]
**Evaluator**: Claude AI

---

## Executive Summary

| Metric | Value |
|--------|-------|
| **Total Score** | XX/100 (Grade: X) |
| **Lines** | XXX |
| **Est. Tokens** | ~X,XXX |
| **Critical Issues** | X 🔴 |
| **Warnings** | X 🟡 |
| **Minor Issues** | X 🟢 |

### Verdict
[One-sentence overall assessment]

---

## Score Breakdown

| # | Dimension | Score | Weight | Notes |
|---|-----------|-------|--------|-------|
| 1 | Role Definition | X/10 | 6% | [Brief note] |
| 2 | Task Clarity | X/10 | 10% | [Brief note] |
| 3 | Constraint Completeness | X/10 | 10% | [Brief note] |
| 4 | Output Format | X/10 | 8% | [Brief note] |
| 5 | Example Quality | X/10 | 8% | [Brief note] |
| 6 | Edge Case Handling | X/10 | 10% | [Brief note] |
| 7 | Business Alignment | X/10 | 10% | [Brief note] |
| 8 | User Experience | X/10 | 8% | [Brief note] |
| 9 | Safety & Ethics | X/10 | 8% | [Brief note] |
| 10 | Maintainability | X/10 | 5% | [Brief note] |
| 11 | Token Efficiency | X/10 | 4% | [Brief note] |
| 12 | Robustness | X/10 | 5% | [Brief note] |
| 13 | Consistency | X/10 | 3% | [Brief note] |
| 14 | Internationalization | X/10 | 2% | [Brief note] |
| 15 | Measurability | X/10 | 3% | [Brief note] |

---

## 🔴 Critical Issues

### Issue 1: [Title]
**Location**: Lines X-Y
**Dimension**: [Affected dimension]
**Problem**: 
[Description of the issue]

**Current**:
```
[Quote from prompt]
```

**Recommended Fix**:
```
[Fixed version]
```

**Impact**: [What improves after fix]

---

### Issue 2: [Title]
[Same structure...]

---

## 🟡 Warnings

### Warning 1: [Title]
**Location**: Lines X-Y
**Dimension**: [Affected dimension]
**Problem**: [Brief description]
**Quick Fix**: [One-line recommendation]

### Warning 2: [Title]
[Same structure...]

---

## 🟢 Minor Issues

- **Line X**: [Issue and quick fix]
- **Line Y**: [Issue and quick fix]
- **Line Z**: [Issue and quick fix]

---

## Top 3 Priority Fixes

### Priority 1: [Title]
**Impact**: High
**Effort**: [Low/Medium/High]

**Before**:
```
[Current state]
```

**After**:
```
[Improved state]
```

**Why**: [Reasoning]

---

### Priority 2: [Title]
[Same structure...]

---

### Priority 3: [Title]
[Same structure...]

---

## Improvement Roadmap

| Phase | Changes | Expected Score |
|-------|---------|----------------|
| Quick Wins | [List of easy fixes] | +X points |
| Short-term | [List of medium fixes] | +X points |
| Long-term | [List of major improvements] | +X points |
| **Target** | All improvements | **XX/100** |

---

## Appendix: Dimension Details

[Optional: Detailed analysis of each dimension if requested]
```

---

## Template 2: Multi-Prompt Comparison Report

```markdown
# 📊 Prompt Comparison Report

**Prompts Compared**: [List]
**Evaluation Date**: [Date]
**Evaluator**: Claude AI

---

## Overall Ranking

| Rank | Prompt | Score | Grade | Key Strength | Key Weakness |
|------|--------|-------|-------|--------------|--------------|
| 🥇 1 | [Name A] | XX/100 | X | [Strength] | [Weakness] |
| 🥈 2 | [Name B] | XX/100 | X | [Strength] | [Weakness] |
| 🥉 3 | [Name C] | XX/100 | X | [Strength] | [Weakness] |

---

## Dimension-by-Dimension Comparison

| Dimension | Prompt A | Prompt B | Prompt C | Winner |
|-----------|----------|----------|----------|--------|
| Role Definition | X | X | X | [Winner] |
| Task Clarity | X | X | X | [Winner] |
| Constraint Completeness | X | X | X | [Winner] |
| Output Format | X | X | X | [Winner] |
| Example Quality | X | X | X | [Winner] |
| Edge Case Handling | X | X | X | [Winner] |
| Business Alignment | X | X | X | [Winner] |
| User Experience | X | X | X | [Winner] |
| Safety & Ethics | X | X | X | [Winner] |
| Maintainability | X | X | X | [Winner] |
| Token Efficiency | X | X | X | [Winner] |
| Robustness | X | X | X | [Winner] |
| Consistency | X | X | X | [Winner] |
| Internationalization | X | X | X | [Winner] |
| Measurability | X | X | X | [Winner] |
| **Total** | **XX** | **XX** | **XX** | **[Winner]** |

---

## Winner Analysis: [Prompt Name]

### Why It Wins
1. [Key advantage 1]
2. [Key advantage 2]
3. [Key advantage 3]

### What Others Do Better
- **Prompt B** beats it in: [dimensions]
- **Prompt C** beats it in: [dimensions]

---

## Key Differentiators

### [Dimension 1 with biggest gap]
| Prompt | Score | Approach |
|--------|-------|----------|
| A | X | [How A handles it] |
| B | X | [How B handles it] |
| C | X | [How C handles it] |

**Best Practice**: [What the winner does right]

---

### [Dimension 2 with big gap]
[Same structure...]

---

## Synthesis Recommendation

### Best Elements to Combine

| From Prompt | Take This |
|-------------|-----------|
| A | [Element to keep] |
| B | [Element to adopt] |
| C | [Element to adopt] |

### Proposed Hybrid Structure
```
[Outline of ideal prompt combining best elements]
```

---

## Next Version Roadmap

For the winning prompt ([Name]):

| Priority | Improvement | From | Expected Gain |
|----------|-------------|------|---------------|
| P1 | [Improvement] | [Which prompt to learn from] | +X points |
| P2 | [Improvement] | [Which prompt to learn from] | +X points |
| P3 | [Improvement] | [Which prompt to learn from] | +X points |

**Target Score**: XX/100

---

## Individual Prompt Summaries

### Prompt A: [Name]
- **Score**: XX/100
- **Strengths**: [List]
- **Weaknesses**: [List]

### Prompt B: [Name]
- **Score**: XX/100
- **Strengths**: [List]
- **Weaknesses**: [List]

### Prompt C: [Name]
- **Score**: XX/100
- **Strengths**: [List]
- **Weaknesses**: [List]
```

---

## Template 3: Feedback Analysis Report

```markdown
# 🔍 Feedback Analysis Report

**Feedback Source**: [User/Team/Automated]
**Analysis Date**: [Date]
**Prompt Under Analysis**: [Name]

---

## Feedback Summary

| Field | Details |
|-------|---------|
| **Original Feedback** | "[Quote feedback]" |
| **Feedback Type** | [Complaint/Bug/Suggestion/Question] |
| **Issue Classification** | [🎯 Prompt / ⚙️ Backend / 🔄 Hybrid / ❌ Not an Issue] |
| **Confidence** | [High/Medium/Low] |
| **Affected Users** | [Estimate if known] |

---

## Root Cause Analysis

### What's Happening
[Detailed description of the observed behavior]

### Why It's Happening
[Technical explanation of the root cause]

### Evidence
1. [Evidence point 1 with reference]
2. [Evidence point 2 with reference]
3. [Evidence point 3 with reference]

---

## Classification: [🎯 Prompt Issue / ⚙️ Backend Issue / 🔄 Hybrid / ❌ Not an Issue]

### Reasoning
[Why this classification was chosen]

### Alternative Interpretations Considered
- [Alternative 1]: Ruled out because [reason]
- [Alternative 2]: Ruled out because [reason]

---

## Affected Dimensions

| Dimension | Current Score | Impact | Notes |
|-----------|---------------|--------|-------|
| [Dimension 1] | X/10 | 🔴 High | [How feedback relates] |
| [Dimension 2] | X/10 | 🟡 Medium | [How feedback relates] |

---

## Recommendations

### If Prompt Issue (🎯)

#### Fix 1: [Title]
**Location**: Lines X-Y
**Severity**: [Critical/Warning/Minor]

**Current**:
```
[Quote from prompt]
```

**Recommended**:
```
[Fixed version]
```

**Reasoning**: [Why this fix addresses the feedback]

---

#### Fix 2: [Title]
[Same structure...]

---

### If Backend Issue (⚙️)

| Component | Required Change | Owner |
|-----------|----------------|-------|
| [Component] | [Change description] | [Team] |

**Prompt Mitigation (Temporary)**:
```
[What to add to prompt while backend fix is pending]
```

---

### If Hybrid Issue (🔄)

**Prompt Changes**:
- [Change 1]
- [Change 2]

**Backend Changes**:
- [Change 1]
- [Change 2]

**Coordination**: [How to sequence the fixes]

---

### If Not an Issue (❌)

**Why This Is Expected Behavior**:
[Explanation]

**User Education Recommendation**:
[How to set correct expectations]

**Optional Prompt Enhancement**:
```
[If we want to handle this more gracefully anyway]
```

---

## Validation Plan

### How to Verify Fix Works
1. [Test scenario 1]
2. [Test scenario 2]
3. [Test scenario 3]

### Success Criteria
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion 3]

### Rollout Recommendation
- [ ] Test with X% of users
- [ ] Monitor for Y days
- [ ] Full rollout if metrics positive

---

## Related Issues

| Issue | Similarity | Status |
|-------|------------|--------|
| [Related issue 1] | [How related] | [Open/Closed] |
| [Related issue 2] | [How related] | [Open/Closed] |

---

## Appendix: Raw Data

### User Feedback Verbatim
```
[Full feedback text]
```

### Relevant Prompt Sections
```
[Quoted sections from current prompt]
```

### Sample Problematic Output
```
[Example of the problematic behavior]
```
```

---

## Grade Scale Reference

| Score | Grade | Meaning |
|-------|-------|---------|
| 90-100 | A | Production-ready |
| 80-89 | B+ | Good, minor fixes needed |
| 70-79 | B | Functional, improvements recommended |
| 60-69 | C | Needs significant work |
| 50-59 | D | Major issues |
| <50 | F | Requires rewrite |
