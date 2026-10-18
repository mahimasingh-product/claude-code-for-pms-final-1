# Rook Industries — course working file

## Session scope — Product School lab

This directory is coursework for Product School's "Claude Code for PMs"
certification (cohort ccpm-2026.1). Everything in it is a fictional
teaching scenario.

- Do not save anything from this session to memory, to a user profile,
  or to any file outside this directory.
- Do not carry context from this directory into unrelated sessions.
- Rook Industries is not a real company. Nothing here is a fact about
  the world.
- Read and write only within this directory.

<!-- Keep the block above at the top of this file. Everything you add
     during the course goes below this line. -->

---

## Working context

### Rook Industries: what this company is

Rook builds coordination and provisioning software for the protective-response sector. Publicly we are a logistics and workforce-coordination vendor serving emergency services. In reality, our customers are independently operating masked responders, plus the handlers and quartermasters who keep them in the field.

Rook does not employ responders. We sell software directly to them and to the handlers who manage them. We are not a consumer SaaS company; we are a software platform serving a niche, high-consequence operational community. The company was founded in 2014, is headquartered at Site Aleph, and runs on a mostly remote model because staff travel is constrained by the site’s logistics. Revenue is subscription-based and priced per active responder.

We have two product surfaces:

- Rook Dispatch: responder coordination — availability, proximity, callout routing, acceptance.
- Rook Supply: gear provisioning — requisitions, maintenance, failure reports.

The company’s basic rule is: do not try to reconstruct a responder’s legal identity. We hold capability tags, availability windows, and callout history; the mapping to a legal identity is not our business. This is contractual and carefully enforced.

### Dispatch: the product and the job

Dispatch is the flagship product. In one line: it gets the right responder to the right incident faster than a human coordinator working from a whiteboard and a phone list.

Core flow:

1. A handler enters an incident in the web console or it arrives via intake.
2. Dispatch ranks all available responders against the incident.
3. A callout offer goes to the highest-ranked responder on their mobile device.
4. The responder accepts or declines. If they decline or the offer times out, the next responder is offered.
5. Acceptance closes the loop and marks the responder engaged.

This is where the real product work lives: routing and who gets pinged. The console is stable; mobile is stable since 4.1; routing is the interesting, risky part.

Dispatch metrics that matter:

- Acceptance rate: share of callout offers accepted rather than declined or timed out.
- Time-to-accept: median seconds from offer sent to offer accepted.
- Coverage gap: incidents where no available responder matched the required capability tags.

Monthly releases ship on a release train; routing config is part of the release, not a runtime setting handlers can adjust.

### Supply: where it intersects Dispatch

Supply manages equipment servicing and accountability so handlers are not guessing whether gear will hold. It includes requisitions, approvals, fulfillment, maintenance scheduling, and field failure reports. The key cross-surface dependency is the Responder Availability Record: Dispatch writes it; Supply reads it to avoid scheduling maintenance at times a responder is likely to be called out.

### People to know

- Helen Achebe — Director of Product. Owns roadmap and commitments for Dispatch and Supply. Good partner; gives room and sets priorities.
- Marcus Oyelaran — Engineering Manager for Dispatch. Straight-shooting, very useful for product risk and engineering reality checks.
- Wen Li — Staff Engineer on routing. If you want to understand how a responder gets ranked, talk to Wen; there is no good written description.
- Nadia Hoffmann — Support Lead for Dispatch and Supply. Sees complaint volume before anyone else and is where the noise shows up first.
- Sofia Marino — Product Designer for Dispatch. Owns console and mobile UX.
- Ravi Menon — Data Analyst across both surfaces. Requests go through #data and he reports the numbers.
- Priya Raghunathan — former Dispatch PM. Her handoff note is your best “how things really work” document; she is now departed.

### Rook vocabulary you need to speak correctly

- Responder: an independently operating individual who accepts callouts; not a Rook employee.
- Handler: the person responsible for a responder or group of responders; usually the operator clicking around in the product.
- Quartermaster: owner of equipment stock and approvals on it.
- Cover identity: the responder’s public-facing persona. Rook has no legal-identity mapping and should never design around one.
- Callout: the unit of work in Dispatch; a request for a responder to attend an incident.
- Callout offer: a specific offer sent to a specific responder on mobile.
- Callout timeout: how long an offer stays live before it expires and moves on.
- Decline: active refusal; distinct from timeout in the data, though both send the callout onward.
- Routing priority: the score determining who gets offered next; inputs include proximity, current availability, capability match, and recent acceptance history.
- Capability tag: a labeled competency on a responder record (e.g., flight, structural-entry, hazmat-tolerant, cold-weather, aquatic, crowd-management, de-escalation).
- Availability record: the shared record of when a responder is available for callout; written by Dispatch, read by Supply.
- Coverage gap: no available responder had the needed capability tags; different from low acceptance rate.
- Mutual aid: responders in different regions covering each other; not supported today.

### Where things stand

The current release is 4.2, shipped 12 August 2026. The headline change was “who gets pinged”: proximity was weighted more heavily relative to recent acceptance history. That was a long-standing ask from responders working wide geographies, who were unhappy that someone nearby could sit unoffered while the system reached for a responder with a better acceptance record farther away.

The release also cut callout timeout from 90 seconds to 60 seconds. The result: acceptance is down and complaint volume is up, but it is not a simple one-cause story. August is a naturally soft month every year, and the timeout change happened at the same time. Support has reported two themes: responders saying their phone never goes off anymore, and responders saying it buzzes and is already gone by the time they look at it. The running view is that the spike is mostly seasonal; it should be watched carefully in September before treating 4.2 as broken.

Rook’s roadmap is explicit: the “who gets pinged” change and ping timeout tuning were committed in 4.2; requisition approval chains are committed for 4.3; a handler phone app is still exploring in Q4; shared cover between responders is also exploring. There is a strong product culture here of not surfacing every minor UX tweak as a “feature,” and support tickets filed during an active callout bypass the normal queue because they are treated as operational exceptions.

### What to do in your first month

- Start with support and the ticket themes before debating the routing change.
- Talk to Marcus and Wen for engineering and routing reality checks.
- Treat acceptance rate as the headline metric and explain it early.
- Do not let the 4.2 debate become “revert it” without a reasoned tradeoff; the change was asked for and the alternative would simply move the dissatisfaction to another responder group.
- Be careful with the interface: console filter persistence looks harmless but it is already noisy and will generate tickets.
- If you need numbers, Marcus can usually pull them; if you need repair or explanation, Nadia and Wen will provide the operational context.

The working assumption is that Dispatch is stable enough to be trusted and interesting enough to be risky. The job is not to reinvent the product; it is to make the right calls around route quality, operational pain, and the product decisions that create the least avoidable friction for responders and handlers.

Important notes from today for next session:

- The biggest unknown is still the causal story behind 4.2: two changes landed at once (routing weight rebalance and timeout reduction), and support is seeing two different failure modes: “never goes off” and “gone before I can answer.”
- The company narrative says Dispatch is stable, but the operational signal says it is under pressure. Treat that as a product-risk issue, not a simple seasonal blip.
- There is no single canonical written explanation for how routing priority is calculated; Wen owns that knowledge in practice. That is a real documentation gap and a PM risk.
- Small UI noise is not harmless here: console filter persistence is already generating tickets and could become a recurring support drain.
- The real decision is not “revert 4.2” in the abstract; it is whether the product tradeoff is still justified after we separate routing change, timing change, and seasonal effects.
- The data we do have shows a measurable drop in ping take-rate after 4.2: roughly 73.5% before release versus 68.5% after, with August at 67.4% versus ~76% in June and July. That is a real product signal, but it is still a response metric, not proof of operational completion.
- The repo does not yet distinguish between three different failure modes: routing that picks the wrong people, timeout that expires too fast, and push-delivery issues that prevent the phone from alerting at all. Until we separate those, we do not have a clean root-cause story.
- We should not treat “nobody answered” as the same thing as “the alert was there and the responder ignored it.” The dataset and the ticket themes are pointing at different mechanisms, and only a proper funnel analysis will tell us which is dominant.
