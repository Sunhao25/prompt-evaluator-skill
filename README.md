# Prompt Evaluator (Agent Skill)

Evaluate, score, and improve system prompts and assistant prompts with a **weighted 15‑dimension rubric**.  
Use it to run a single prompt audit, compare prompt variants (A/B), or diagnose whether user feedback is **prompt‑related vs backend‑related**.

---

## What this skill does

### 1) Single prompt scoring
- Scores a prompt across **15 dimensions (total = 100%)**
- Flags **Critical / Warning / Minor** issues with evidence (quotes)
- Provides **specific, line‑level fixes** and a prioritized improvement plan

### 2) Multi‑prompt comparison (2–5 prompts)
- Side‑by‑side scoring + ranking table
- Identifies trade‑offs by dimension
- Recommends a “best overall” prompt and an upgrade roadmap

### 3) Feedback / bug analysis
- Classifies issues as **Prompt / Backend / Hybrid / Not an issue**
- Maps symptoms to rubric dimensions
- Outputs actionable prompt edits + validation criteria

---

## Install

> Replace `<owner>/<repo>` with your GitHub repo.

```bash
npx skills add <owner>/<repo>
```

List skills inside the repo:

```bash
npx skills add <owner>/<repo> --list
```

---

## Use

After installing, ask your agent to use **prompt-evaluator**.

### Mode 1: Single prompt evaluation (example)
```text
Use prompt-evaluator to evaluate this system prompt.
Focus on clarity, constraints, and fallback behavior.

PROMPT:
<PASTE YOUR PROMPT HERE>
```

### Mode 2: Multi‑prompt comparison (example)
```text
Use prompt-evaluator to compare these 3 prompts for the same task.
Pick the best overall and propose specific edits to improve it.

PROMPT A:
...

PROMPT B:
...

PROMPT C:
...
```

### Mode 3: Feedback analysis (example)
```text
Use prompt-evaluator to analyze this user feedback and bug report.
Tell me whether this is a prompt issue, and propose a fix with evidence.

PROMPT (current):
...

FEEDBACK / BUGS:
1) ...
2) ...
3) ...
```

---

## Output format (what you get)

This skill produces structured, decision‑oriented reports (templates included in `references/report-templates.md`), typically containing:

- **Summary** (overall score + grade + top risks)
- **Score breakdown** (15 dimensions)
- **Critical issues (🔴)** / **Warnings (🟡)** with quoted evidence
- **Top 3 priority fixes**
- **Recommended edits** (before/after snippets)
- **Next version roadmap**
- For feedback mode: **root cause**, **prompt vs backend judgment**, **validation criteria**

### Grading scale
| Score | Grade | Meaning |
|------:|:-----:|---------|
| 90–100 | A | Production‑ready, minimal issues |
| 80–89 | B+ | Good quality, minor improvements needed |
| 70–79 | B | Functional, several improvements recommended |
| 60–69 | C | Needs significant work |
| 50–59 | D | Major issues, not recommended for production |
| <50 | F | Fundamental problems, requires rewrite |

---

## The 15 evaluation dimensions (weights)

| # | Dimension | Weight |
|---:|---|---:|
| 1 | Role Definition | 6% |
| 2 | Task Clarity | 10% |
| 3 | Constraint Completeness | 10% |
| 4 | Output Format | 8% |
| 5 | Example Quality | 8% |
| 6 | Edge Case Handling | 10% |
| 7 | Business Alignment | 10% |
| 8 | User Experience | 8% |
| 9 | Safety & Ethics | 8% |
| 10 | Maintainability | 5% |
| 11 | Token Efficiency | 4% |
| 12 | Robustness | 5% |
| 13 | Consistency | 3% |
| 14 | Internationalization | 2% |
| 15 | Measurability | 3% |

For the full rubric (definitions, scoring guidance, and fix patterns), see:
- `references/dimensions.md`
- `references/anti-patterns.md`

---

## Repo structure

```text
skills/
  prompt-evaluator/
    SKILL.md
    references/
      dimensions.md
      anti-patterns.md
      report-templates.md
      feedback-analysis.md
```

---

## Tips for best results

- Provide the **actual prompt text** (not a summary) and keep original formatting.
- If you have it, include **real examples**: user inputs → model outputs → why it’s wrong.
- When comparing prompts, state the **business goal** (accuracy, safety, tone, conversion, latency, etc.).
- For feedback analysis, include **where the prompt sits** (system / developer / tool instructions), and any relevant backend limits (data availability, time windows, permissions).

---

## License

Add a `LICENSE` file in your repo (MIT is a common default). If your repo already includes one, this skill follows that license.

---

## Contributing

PRs are welcome:
- Add new anti‑patterns and fixes
- Add domain‑specific examples (support, analytics, sales, compliance)
- Improve report templates and validation checklists
