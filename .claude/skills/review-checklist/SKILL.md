---
name: review-checklist
description: Review a product brief for a clear owner, a way to measure success, consistent scope, and a problem statement that comes before the proposed fix. Use when asked to check, review, or assess a brief.
---

# Review Checklist

Review the brief the user points to. If they provide the brief in the conversation, use that; otherwise, read the named file. Do not edit or rewrite the brief unless the user explicitly asks.

Assess only these four criteria:

1. **Owner:** Does the brief identify a person or role accountable for the work? A team alone is insufficient unless accountability within that team is clear.
2. **Success measure:** Does it say how the team will know the work succeeded? Look for an observable outcome and, where appropriate, a metric, target, or timeframe. Do not treat a list of aspirations as a measurable success definition.
3. **Consistent scope:** Does the proposed work stay within the scope described at the start? Compare the problem and core ask with the proposal, details, scope exclusions, and next steps. Flag additions that materially broaden the work, even if they are framed as optional or future possibilities. Do not flag implementation detail that is necessary to deliver the stated ask.
4. **Problem before fix:** Does the brief explain the user or business problem and why it matters before presenting the proposed solution? A solution appearing first, or a problem stated only as a restatement of the feature request, does not meet this criterion.

For each criterion, return **Pass**, **Needs work**, or **Not stated**. Base the status on the brief's actual text: quote a short phrase or name the relevant section as evidence. Use **Needs work** when there is some relevant content but it is unclear, incomplete, or contradictory; use **Not stated** when the brief gives no evidence for the criterion. Do not infer missing owners, targets, or rationale.

Use this format:

## Brief review

| Check | Status | Evidence and issue |
|---|---|---|
| Owner | ... | ... |
| Success measure | ... | ... |
| Consistent scope | ... | ... |
| Problem before fix | ... | ... |

**Overall:** State whether the brief is ready against these checks, then give the one or two highest-value changes to make. Keep recommendations specific to the gaps found. If all checks pass, say so without inventing extra review criteria. Do not broaden this into a general product, writing, or feasibility review.