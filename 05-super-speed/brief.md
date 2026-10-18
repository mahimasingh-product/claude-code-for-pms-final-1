Quiet Responder Recovery — one-pager
Product, Dispatch
5 October 2026

Problem

Right now, the system quietly lowers a responder's recent-acceptance
score after they decline or miss a callout. The problem is not just the
penalty itself; it's that the system does not explain what happened, and
it does not give the responder a clear path back in.

From the responder's point of view, it can feel like they have been
silently passed over or forgotten. From the handler's point of view,
there is no obvious signal that a responder has gone quiet and no clear
re-entry step once that happens.

Proposal

Build a re-engagement flow for responders who have gone quiet, instead
of a hidden score-only penalty.

The idea is simple: when a responder misses or declines enough callouts
that their recent-acceptance signal drops, the system does two things:

1. Flags them as in a quiet-responder recovery state.
2. Gives them a direct, visible chance to re-confirm availability
   and device readiness before we send them more work.

This is not a setting that handlers or engineers toggle. This is a
product flow that the person affected can see and act on.

What it looks like

For the responder

- A quiet responder sees a short in-app prompt after a missed or
  declined callout: "We noticed you haven't been answering recent
  callouts. Want to confirm you're available?"
- They can choose one of three states:
  - I am available now
  - I am temporarily unavailable
  - I want fewer pings / slower routing
- If they pick "available," their ranking returns to normal after a
  quick confirmation.
- If they pick "temporarily unavailable," the system pauses routing to
  them for a defined period instead of quietly continuing to ping them.
- If they pick "fewer pings," the system reduces their routing volume
  and asks them to update their alert preferences.

For the handler

- In the console, a quiet responder shows a badge or status like
  "recovery" or "availability check needed."
- That status is visible next to their record and on the incident
  activity for the callout that triggered it.
- The handler can see the system is intentionally holding back on them,
  not that they're just falling below the line by accident.

This matters because it turns an invisible scoring problem into a
visible operational state.

Why this is better than a raw score change

- It explains what happened in plain language.
- It gives the responder a way to recover without feeling ignored.
- It gives the handler a reason when a previously active responder is no
  longer being offered work.
- It avoids a silent penalty loop in which a person disappears from the
  queue without incident and nobody notices until a complaint arrives.

Scope

Not a full routing redesign. Not a new configuration page. Not a brand
new feature area.

This is limited to the quiet-responder flow:

- detect the threshold
- surface the state in-app and in the console
- ask for re-confirmation or temporary pause
- allow a clear return to normal once they engage again

That is a contained product experience, not a systems overhaul.

Owner

Product and Design together with Dispatch engineering. Marcus can help
with feasibility, Sofia can shape the flow, and this is a good fit for
an iteration on the existing mobile/console experience.

Success measures

- fewer silent misses reported by responders
- reduction in complaint volume tied to quiet responders
- fewer handlers reporting they were surprised by a responder being
  unavailable without explanation
- faster recovery for responders who do want to come back online
- no increase in coverage gaps after re-engagement flow is launched

Prototype flow

1. Responder misses or declines a callout.
2. App shows: "We noticed a pattern. Confirm you're available."
3. Responder taps one of three options.
4. System updates routing and visibility accordingly.
5. If they confirm, they return to regular ranking within the next
   cycle.

This is the kind of flow we can show in a click-through and it gives
Helen a real product concept instead of a number change dressed up as a
fix.

Next steps

- Confirm the threshold for triggering recovery mode.
- Decide whether a handler sees the same state in the console.
- Prototype the mobile prompt and console status treatment.
- Test with a few real responder stories before launch.

This would be a product decision, not just a code tweak — and that is
what Helen is asking for.
