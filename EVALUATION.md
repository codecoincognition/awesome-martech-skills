# Evaluation Framework

How we measure whether a skill actually works.

## Philosophy

A skill that works 90% of the time on 5 use cases beats a skill that works 50% of the time on 20 use cases. We optimize for reliability over coverage.

## Five-Dimension Rubric

Every skill is scored on these dimensions (1-5 scale):

### 1. Trigger Accuracy

Does the skill activate when it should — and stay quiet when it shouldn't?

| Score | Meaning |
|---|---|
| 5 | Triggers on 90%+ of relevant prompts, <5% false positives |
| 4 | Triggers on 80%+ of relevant prompts, <10% false positives |
| 3 | Triggers on 70%+ of relevant prompts, <15% false positives |
| 2 | Triggers inconsistently, frequent false positives or misses |
| 1 | Rarely triggers correctly |

**Testing:** Run 20 prompt variations (10 should-trigger, 10 should-not-trigger) and measure precision/recall.

### 2. Output Quality

Is the output useful, accurate, and actionable?

| Score | Meaning |
|---|---|
| 5 | Output is production-ready with zero edits needed |
| 4 | Output needs minor edits (formatting, small corrections) |
| 3 | Output provides a solid starting point but needs significant editing |
| 2 | Output has correct structure but wrong or generic content |
| 1 | Output is unusable or misleading |

**Testing:** Have 3 marketers score independently on a use case they know well.

### 3. Input Validation

Does the skill handle bad, missing, or ambiguous input gracefully?

| Score | Meaning |
|---|---|
| 5 | Catches all validation errors, provides helpful corrections |
| 4 | Catches most errors, recovery guidance is clear |
| 3 | Catches obvious errors but misses edge cases |
| 2 | Fails silently on bad input |
| 1 | Crashes or produces garbage on bad input |

**Testing:** Feed 5 adversarial inputs (missing columns, wrong formats, empty files, extra columns, ambiguous values).

### 4. Completeness

Does the skill deliver everything promised in its output contract?

| Score | Meaning |
|---|---|
| 5 | All promised outputs present with correct schemas |
| 4 | All outputs present, minor schema deviations |
| 3 | Most outputs present, some missing fields |
| 2 | Key outputs missing or wrong format |
| 1 | Output doesn't match contract at all |

**Testing:** Compare output against the skill's stated output contract. Every column, every file, every section.

### 5. Usability

Can a non-technical marketer use this skill on their first try?

| Score | Meaning |
|---|---|
| 5 | Works on first attempt, clear instructions, no confusion |
| 4 | Works on first attempt with minor clarification needed |
| 3 | Requires re-reading instructions or one retry |
| 2 | Requires multiple attempts or external documentation |
| 1 | Requires technical knowledge not stated in prerequisites |

**Testing:** Have someone unfamiliar with the skill try it with only the SKILL.md as guidance.

## Testing Phases

### Phase 1: Synthetic Testing (Automated)

Run the skill against 3 synthetic test cases with known inputs and expected outputs.

- Do outputs contain required sections/columns?
- Do outputs match expected format?
- Does the skill complete within 10 minutes?

### Phase 2: Trigger Testing (Automated)

Test 20 prompt variations for trigger accuracy.

- 10 should-trigger prompts (direct, indirect, casual, formal, problem-stated)
- 10 should-not-trigger prompts (adjacent domains, partial keyword matches)
- Measure: precision, recall, F1

### Phase 3: Adversarial Testing (Manual)

Feed the skill intentionally bad inputs.

- Missing required columns
- Wrong data types
- Empty CSV
- CSV with 10,000 rows (stress test)
- Conflicting or contradictory input values

### Phase 4: Edge Case Testing (Manual)

Test boundary conditions specific to each skill.

- Single-row input
- Non-English content
- Unusual industry verticals
- Extremely long text fields

### Phase 5: User Testing (Manual)

Have 3 real marketers use the skill on their actual data.

- Record time to first successful output
- Record number of attempts needed
- Collect qualitative feedback
- Identify common confusion points

## Minimum Quality Bar

A skill must score 3+ on all five dimensions before it ships. Scores below 3 on any dimension require iteration.

**Passing:** All dimensions >= 3, average >= 3.5
**Excellent:** All dimensions >= 4, average >= 4.5

## Reporting

Each skill's evaluation results are stored in the skill's directory as `eval-results.json`:

```json
{
  "skill_name": "keyword-cluster-analyzer",
  "eval_date": "2026-03-15",
  "version": "1.0",
  "scores": {
    "trigger_accuracy": 4,
    "output_quality": 4,
    "input_validation": 3,
    "completeness": 5,
    "usability": 4
  },
  "average": 4.0,
  "status": "passing",
  "notes": "Input validation needs work on empty CSV edge case",
  "test_cases_run": 20,
  "user_testers": 2
}
```
