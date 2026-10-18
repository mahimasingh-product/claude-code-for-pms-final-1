# Quiet Responder Re-entry
Dispatch product brief · Draft · 18 October 2026

## Problem

A decline or timeout lowers a responder's recent-acceptance score; only
accepting a callout raises it, and the score does not recover with time.
If ranking then stops offering them work, they cannot accept their way
back in. A timeout also does not tell us whether the responder saw the
alert. A prompt triggered only by a missed or declined callout will miss
the person who is no longer being offered calls.

## Who this is for

Primarily, responders who remain marked available but receive no offer
across repeated callouts they could have been considered for. We should
not assume they are unwilling or unavailable. Their handler needs a
clear, actionable signal too: Kip described watching two coverage cards
where one responder had no offers while the other was overwhelmed, with
no explanation to give either of them.

## What we would build

After repeated callouts in the responder's region occur while they are
marked available, but no offer is sent to them, create a check-in outside
the callout queue. Set the threshold from a pilot; do not trigger on a
quiet calendar period alone. Send a separate, non-work notification and
keep the check-in visible in Dispatch: “You're marked available, but
haven't received a callout offer recently. Are you still available,
taking a break, or having trouble with alerts?” If it is not seen, the
handler sees it as pending and can follow up through existing contact
channels; silence is not treated as a decline.

- **Available and reachable:** confirm availability and alert readiness;
  return to the neutral acceptance baseline and normal ranking, not the
  top of the list.
- **Taking a break:** pause their availability until they choose to
  return, without another score penalty.
- **Alert trouble:** pause callout offers until the responder confirms
  they can receive alerts; show a clear help path, with no score penalty.
  Track whether the check-in was sent, delivered, seen, and answered.

The handler sees “check-in needed” and its status on the responder's
coverage card, not a hidden score. If there is no response, the status
stays unresolved; the system does not infer consent or silently boost
their ranking.

## Deliberately out of scope

This is not a routing redesign, a handler-controlled ranking setting, or
a guarantee of future work. It does not automatically raise priority,
equate a timeout with a deliberate decline, or collect legal identity
information. It does not claim to fix push delivery; delivery and seeing
the check-in must be measured separately from acceptance.

## How we will judge it

Measure check-in delivery, seen and response rates; time to an explicit
availability decision; and whether re-confirmed responders return to
normal ranking without increasing coverage gaps. Validate the trigger
threshold and the alert path with Dispatch engineering, Support, and a
small group of handlers and responders before rollout.
