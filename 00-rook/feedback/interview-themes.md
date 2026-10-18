# Dispatch interview themes

## Top 5 themes from the responder and handler interviews

### 1) Callout timing feels unreliable
- The strongest pattern across the interviews was that responders were experiencing both:
  - offers arriving too quickly, such that the phone buzzes and the callout is already gone by the time they look
  - periods that feel too quiet, where no offer appears even though the responder is available
- This created a sense that Dispatch is not consistently hitting the right moment, which matters in a high-consequence operational context.

### 2) The console is not glanceable enough
- Multiple handlers called out small text, hard-to-read status badges, and poor contrast in the interface.
- Some wanted larger text and clearer visual differentiation between states such as available, engaged, and unavailable.
- For a console used while multitasking, this is not cosmetic; it affects operational speed and confidence.

### 3) The system does not explain enough of what is happening
- Handlers repeatedly described seeing mismatched coverage cards or silent periods without a clear explanation.
- The issue was not only that the system was wrong; it was that the system did not provide enough context for the user to interpret why something happened.
- This is especially important when a handler is trying to understand whether a responder was skipped, unavailable, filtered out, or simply not offered.

### 4) Filters and state persistence are trust-sensitive
- A small change such as filter persistence was treated as meaningful because it affects whether the handler can trust the console from the start of a shift.
- The interviews showed that even minor state resets create friction and reduce trust in the whole interface.
- This suggests that product stability is judged by whether the screen stays in the right state, not only by whether a feature is technically correct.

### 5) “Small” UX issues are operationally important
- The interviews repeatedly surfaced issues that were described as minor but were actually meaningful under pressure:
  - status badge legibility
  - dark mode for overnight use
  - filter trust
  - alert clarity
  - explaining why one responder was chosen and another was skipped
- The common thread is that operational trust is fragile, and small UI failures feel much larger when they occur during live callouts.

## Overall read
The interviews suggest a common issue: people do not just need better ranking; they need more confidence in the system’s live behavior. The product may be technically functional, but the user experience is undermining trust because the console and the callout flow are not transparent, consistent, or readable enough under real operational conditions.

## Follow-up questions for the next PM readout
- Are the “too fast” and “too quiet” complaints coming from the same underlying mechanism, or are they distinct failure modes?
- Is the core problem in ranking, push/offer delivery, or the clarity of the handler’s console state?
- Which of the UI concerns are immediate product risks versus longer-term quality-of-life asks?
- Are there metrics we can use to separate seasonal effects from structural changes in Dispatch behavior?
