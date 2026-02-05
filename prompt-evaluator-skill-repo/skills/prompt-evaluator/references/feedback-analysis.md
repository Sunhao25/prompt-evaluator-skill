# Feedback Analysis Decision Tree

Guide for determining whether user feedback indicates a prompt issue vs. other causes.

---

## Step 1: Classify the Feedback Type

| Type | Indicators | Examples |
|------|------------|----------|
| **Behavior Complaint** | AI did something wrong | "It keeps apologizing too much" |
| **Missing Feature** | AI can't do something | "Why can't it see my DMs?" |
| **Data Issue** | Wrong/missing data | "The numbers are outdated" |
| **UX Issue** | Interaction problems | "Responses are too long" |
| **Performance Issue** | Speed/reliability | "It's too slow" |
| **Accuracy Issue** | Incorrect information | "It gave wrong advice" |

---

## Step 2: Root Cause Classification

### 🎯 PROMPT ISSUE (Fixable in prompt)

**Indicators:**
- Issue relates to AI's behavior/tone/format
- Issue relates to what AI says or doesn't say
- Issue relates to how AI handles certain scenarios
- Issue consistent across similar queries
- Issue stems from missing/wrong instructions

**Examples:**
| Feedback | Root Cause | Fix Location |
|----------|------------|--------------|
| "Too formal" | Tone not specified | Add tone guidelines |
| "Doesn't ask clarifying questions" | No ambiguity handling | Add clarification rules |
| "Mentions technical details" | No abstraction rule | Add "avoid jargon" rule |
| "Gives medical advice" | Missing safety boundary | Add disclaimer requirement |
| "Doesn't redirect to tools" | Missing referral triggers | Add cross-sell rules |

---

### ⚙️ BACKEND ISSUE (Not fixable in prompt)

**Indicators:**
- Issue relates to data availability
- Issue relates to system capabilities
- Issue relates to integration/API
- Issue requires code changes
- Issue is infrastructure-related

**Examples:**
| Feedback | Root Cause | Responsible Team |
|----------|------------|------------------|
| "Data is 3 days old" | Update frequency | Data Engineering |
| "Can't access private DMs" | API limitation | Product (can't fix) |
| "Slow responses" | Server performance | Infrastructure |
| "Crashes sometimes" | Bug in code | Engineering |
| "PDF export broken" | Feature bug | Engineering |

---

### 🔄 HYBRID ISSUE (Needs both)

**Indicators:**
- Prompt can mitigate but not fully solve
- Backend fix improves but prompt explains limitation
- User expectation mismatch needs both education and capability

**Examples:**
| Feedback | Prompt Fix | Backend Fix |
|----------|------------|-------------|
| "Data too old" | Add freshness disclaimer upfront | Increase update frequency |
| "Missing feature X" | Redirect to alternative + set expectation | Build feature X |
| "Errors sometimes" | Add graceful fallback response | Fix root cause bug |

---

### ❌ NOT AN ISSUE (Expected behavior)

**Indicators:**
- User misunderstands product scope
- User expects impossible capability
- Behavior is intentional and correct
- Edge case not worth addressing

**Examples:**
| Feedback | Why Not an Issue |
|----------|------------------|
| "Can't hack my ex's account" | Intentionally blocked |
| "Doesn't predict the future" | Not possible |
| "Won't help with illegal activity" | Safety feature |
| "Asks for clarification" | Good UX, not a problem |

---

## Step 3: Prompt Issue Deep Dive

If classified as PROMPT ISSUE, determine which dimension is affected:

### Dimension Mapping

| Symptom | Likely Dimension | Investigation |
|---------|------------------|---------------|
| Wrong tone | Role Definition, User Experience | Check tone guidelines |
| Missing content | Constraint Completeness | Check DO rules |
| Wrong content | Constraint Completeness | Check DON'T rules |
| Inconsistent format | Output Format, Consistency | Check format rules & examples |
| Missed edge case | Edge Case Handling | Check fallback rules |
| Poor error handling | Edge Case Handling | Check error templates |
| Brand misalignment | Business Alignment | Check business goals |
| Safety violation | Safety & Ethics | Check safety boundaries |
| Verbose output | Token Efficiency, Output Format | Check length constraints |
| Confusing response | User Experience, Example Quality | Check clarity rules |
| Doesn't cross-sell | Business Alignment | Check upsell triggers |
| Reveals instructions | Robustness | Check security rules |

---

## Step 4: Evidence Collection

Before concluding, collect evidence:

### For Prompt Issues
- [ ] Quote the specific rule that's failing
- [ ] Show the input that triggered the issue
- [ ] Show the problematic output
- [ ] Identify the gap in instructions

### For Backend Issues
- [ ] Confirm behavior is consistent (not just one instance)
- [ ] Check if prompt has clear instructions that are ignored
- [ ] Verify data availability/correctness
- [ ] Check system logs if available

---

## Step 5: Confidence Assessment

| Confidence | Criteria |
|------------|----------|
| **High** | Clear evidence, reproducible, single cause |
| **Medium** | Some evidence, likely cause identified |
| **Low** | Multiple possible causes, needs more investigation |

---

## Decision Flowchart

```
User Feedback
     │
     ▼
Is it about AI behavior/output?
     │
    YES ──────────────────────────────────────────────── NO
     │                                                    │
     ▼                                                    ▼
Can behavior be changed                          Is it about data?
by modifying instructions?                              │
     │                                                   │
    YES ──────────── NO                            YES ─────── NO
     │                │                             │           │
     ▼                ▼                             ▼           ▼
🎯 PROMPT        Is it about                   ⚙️ BACKEND   Is it about
   ISSUE         system capability?                ISSUE     speed/reliability?
                      │                                            │
                     YES ──── NO                              YES ─────── NO
                      │        │                               │           │
                      ▼        ▼                               ▼           ▼
                 ⚙️ BACKEND  🔄 HYBRID                    ⚙️ BACKEND   ❌ NOT AN
                    ISSUE      ISSUE                        ISSUE        ISSUE
```

---

## Common Misattributions

### Looks like Prompt Issue, Actually Backend
| Symptom | Why it Seems Like Prompt | Actual Cause |
|---------|-------------------------|--------------|
| "AI says wrong date" | Seems like format issue | Data feed error |
| "AI can't find X" | Seems like search logic | Data not indexed |
| "Slow first response" | Seems like prompt too long | Cold start latency |

### Looks like Backend Issue, Actually Prompt
| Symptom | Why it Seems Like Backend | Actual Cause |
|---------|--------------------------|--------------|
| "Doesn't show feature Y" | Seems like missing feature | Missing instruction to use Y |
| "Error messages cryptic" | Seems like code issue | No error template in prompt |
| "Inconsistent behavior" | Seems like bug | Contradictory prompt rules |

---

## Report Template

```markdown
# Feedback Analysis

## Summary
- **Feedback**: [Quote]
- **Classification**: [Prompt/Backend/Hybrid/Not Issue]
- **Confidence**: [High/Medium/Low]

## Evidence
- [Evidence point 1]
- [Evidence point 2]

## Root Cause
[Detailed explanation]

## Recommendation
[Specific fix with before/after if applicable]

## Validation
[How to verify the fix works]
```
