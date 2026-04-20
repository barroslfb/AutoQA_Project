# AutoQA Specialist — Test Task

## Context

We are building an AutoQA system that converts lesson transcripts into reliable, evidence-based teaching quality signals — and validating whether those signals predict meaningful student outcomes.

The system serves two goals that this task focuses on:
1. **Reliable quality measurement** — can we trust what the model scores?
2. **Predictive usefulness** — do the signals connect to outcomes that matter for the business?

You are not expected to build anything or redesign the system.  
We want to understand how you think about **rubric quality**, **measurement reliability**, and **predictive usefulness**.

---

## Files

| File | Contents |
|---|---|
| `autoqa_output_gpt4o_240.csv` | AutoQA output for 240 lessons — model version A |
| `autoqa_output_gpt51_240.csv` | AutoQA output for the same 240 lessons — model version B |
| `outcomes_240.csv` | Student outcomes for the same 240 lessons |

**AutoQA output contains:**
- 16 binary rubric items (0/1) with model reasoning and transcript evidence per item
- 6 quantitative comment fields (talk balance, engagement rate, feedback specificity, question quality, productive time, cognitive demand)
- Overall score (`binary_items_ones_pct`)

**Outcomes file contains:**
- `next_lesson_attended` — did the student attend the next lesson (0/1)
- `m1_retained` — was the student retained at month 1 (0/1)

---

## Block 1 — Reliability

> Can this quality signal be measured consistently?

### Task 1. Review the model outputs

Compare the two model versions across all 16 items. For each of your three selected items, explain what in the data led you to that conclusion.

Identify:
- **One item you consider ready for operational use**
- **One item you consider borderline**
- **One item you consider not ready**

### Task 2. Recommended action per item

For each of your three selected items, recommend one of:
- keep as is
- tighten the rubric definition
- treat as not ready for operational use

### Task 3. Rewrite two weak rubric items

Select the 2 items you think need the most tightening.

For each, provide:
- A clearer definition
- COUNT ONLY IF (specific conditions)
- DO NOT COUNT (explicit exclusions)
- One example of acceptable evidence from the transcripts

---

## Block 2 — Predictive Usefulness

> Even if a signal is measurable, is it useful for predicting outcomes?

### Task 4. Identify and interpret promising signals

Using the outcomes file:
1. Calculate the relationship between each rubric item and `next_lesson_attended` / `m1_retained`. Show your work.
2. Identify 1–2 items that look most promising. Explain why.

### Task 5. So what?

In 3–5 sentences: if you found 1–2 signals that reliably predict next lesson attendance or M1 retention — what would you actually do with that in practice?

---

## Deliverables

1. **A short memo** with your conclusions (max 2 pages or 5 slides)
2. **A working analysis file** — spreadsheet, Python notebook, or equivalent showing your Block 2 analysis
3. **Rewritten rubric section** for the 2 items you selected in Task 3

---

## Notes

- Please aim for **3–4 hours** total.
- We are not looking for production-ready code.
- We are looking for **rigor, metric literacy, rubric thinking, and sound interpretation of data**.
- If time is limited, prioritise depth over coverage.
