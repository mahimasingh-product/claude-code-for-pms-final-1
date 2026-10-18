---
name: meeting-recap
description: 'Extract decisions and action items with their owners from meeting notes, transcripts, or minutes. Use when asked for a meeting recap, decisions made, follow-ups, action items, or owners from notes.'
argument-hint: '[meeting notes or file path]'
---

# Meeting Recap

Turn meeting notes into a concise record of decisions and follow-ups. Work from notes provided in the conversation or from the file or files the user names. Do not edit the source notes.

## Procedure

1. Read all provided or named meeting notes before summarizing.
2. Record a decision only when the notes show that the group agreed to it. Keep proposals, options, and unresolved discussion out of the decisions list.
3. Record a follow-up only when the notes state an action someone agreed or was asked to take. Capture the action, its owner, and due date when stated.
4. Use the person's or role's name exactly as given. If an action has no clear owner, write `Not stated`; do not infer an owner from attendance, job title, or surrounding context.
5. Preserve uncertainty. Mark unclear or conflicting details as `Unclear` and briefly say what needs confirmation. Do not invent decisions, assignments, or deadlines.
6. Include a short phrase or note location as evidence for each item when available. Keep wording concise and faithful to the notes.

## Output

# Meeting Recap

## Decisions

| Decision | Evidence |
|---|---|

If no explicit decisions appear, say `No explicit decisions recorded.`

## Follow-ups

| Action | Owner | Due | Evidence |
|---|---|---|---|

If no explicit follow-ups appear, say `No explicit follow-ups recorded.` Use `Not stated` for a missing owner or due date. Do not add general discussion summaries, inferred tasks, or recommendations.
