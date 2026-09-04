# Spec: Standalone Grievance Redressal (EPFiGMS) screen for the Revamped Portal

*Source: `epfo-portal-clone.html`, the local-only design-study clone of EPFO Member e-Sewa with a Current Portal / Revamped Portal toggle. This spec closes one gap surfaced by comparing the live EPFO homepage (epfo.gov.in) against the prototype: the live site advertises "Grievance Redressal (EPFiGMS)" as a top-level member service, but the prototype only surfaces a grievance draft buried inside one claim's detail view in Track Claim Status.*

> **Note on process:** this workspace has no issue tracker or triage-label vocabulary configured (it is not a git repository), so this spec is delivered as a standalone document rather than filed to a tracker, per `/to-spec`'s fallback. If a tracker is configured later via `/setup-matt-pocock-skills`, this content can be filed as one epic and the User Stories split into individual tickets. Scope and testing seam were confirmed with the user before writing: **scope is the Grievance screen only** (accessibility and pension-lifecycle gaps are explicitly deferred), and **testing reuses the existing screen seam** (no new test infrastructure).

## Problem Statement

When Rahul's Form-19 is rejected or his Form-10C stalls past the service standard, he has no first-class place in the portal to report it, track it, and escalate. The only grievance path the Revamped Portal offers today is buried: he must open the specific rejected claim in Track Claim Status, click "I believe this rejection is wrong," and copy a generated EPFiGMS draft out to a separate system. He has to already know EPFiGMS exists, know that a "Poor" rating is what unlocks a formal appeal, hold his own reference number, and track the 21-day reply clock himself. The live EPFO site promotes "Grievance Redressal (EPFiGMS)" as a headline service, yet a member who lands on the portal after a false closure (a grievance marked "resolved" without the money arriving) has nowhere to go that treats reporting, tracking, and escalation as one legible flow.

## Solution

A standalone Grievance Redressal screen, Revamped-only, that promotes the EPFiGMS draft and verified-closure logic already prototyped inside Track Claim Status into a first-class, navigable screen. From the member's perspective it does five things the buried flow does not: (1) a plain-language "what went wrong" picker that routes the grievance to the right EPFO office instead of a raw department tree; (2) a grievance composer that structures the complaint into what happened, which rule applies, and the outcome sought; (3) a timestamped local record showing the filed date, the 21-day reply due date, and a visible countdown, so waiting is distinguishable from stuck; (4) a verified-closure question ("was your problem actually resolved? Yes / No / Partly") that surfaces the appeal path on a No or Partly instead of letting a false closure be passively accepted; and (5) a pre-filled appeal with the escalation ladder shown (EPFiGMS to CPGRAMS with the 21-day clock, then RTI or the relevant ombudsman). The Current Portal keeps its byte-faithful behavior: its grievance control links out to EPFiGMS exactly as the live site does, with no in-app grievance screen.

## User Stories

1. As a member whose claim was rejected, I want a "Report a problem" entry point in the main navigation, so that I do not have to know EPFiGMS exists to find the grievance path.
2. As a member, I want to pick what went wrong in plain language, so that my grievance routes to the correct EPFO office instead of being closed as "does not pertain to us."
3. As a member, I want the grievance text structured into what happened, which rule or entitlement applies, and the specific outcome I want, so that a vague grievance cannot invite a vague closure.
4. As a member disputing a specific claim, I want the grievance pre-filled from that claim (claim ID, rejection code, filed and rejected dates), so that I do not retype details already on file.
5. As a member, I want a completeness and evidence prompt before I submit, so that nothing is missing that the office could later use to close the grievance.
6. As a member, I want a timestamped record of my grievance (filed date, 21-day due date, each update, closure date), so that I never lose the reference number and can see the clock.
7. As a member, I want a visible countdown to the 21-day reply deadline, so that I can tell a normal wait from a stall.
8. As a member, I want a one-tap, pre-written reminder the moment the 21-day clock lapses, so that I can chase the office without composing anything.
9. As a member whose grievance was closed, I want to be asked plainly "was your problem actually resolved? Yes / No / Partly," so that a false closure surfaces the appeal path rather than being passively accepted.
10. As a member, I want a No or Partly answer to make the appeal one tap with the 30-day appeal clock shown, so that I know the escalation exists and do not miss the window.
11. As a member, I want the appeal pre-filled with my original grievance text and the closure note verbatim, so that I do not start over.
12. As a member, I want the escalation ladder shown (EPFiGMS, then CPGRAMS with its 21-day reply norm, then RTI or the relevant ombudsman), so that I know where to go if the appeal also fails.
13. As a member reading a rejected or stalled claim in Track Claim Status, I want a one-step link into this grievance screen carrying that claim's context, so that the loop from "my claim bounced" to "I am reporting it" is a single move.
14. As a member on the Current Portal, I want the grievance control to behave exactly as the live site does (a link out to EPFiGMS, no in-app screen), so that the Current replica stays byte-faithful.
15. As a member, I want the screen to mark clearly which parts are illustrative demo data, so that I do not mistake invented reference numbers or resolution-time figures for real EPFO data.
16. As a member who wants context before starting, I want a "typical resolution time for this grievance type" figure shown (illustrative), so that I know what normal looks like before I file.
17. As a member interrupted mid-grievance, I want an unfinished grievance held as a draft for this session, so that I can come back to it without retyping.
18. As a member using a screen reader, I want the grievance form, status timeline, and appeal reveal announced and keyboard-navigable, so that the accessibility baseline holds on this screen too.
19. As a member re-entering the grievance screen, I want it reset to a clean state, so that a previous demo interaction does not leak into a fresh view.
20. As a member who switches from Revamped to Current mid-grievance, I want any simulated grievance state cleared, so that the Current replica never shows Revamped-only demo state.
21. As a reviewer, I want every illustrative statistic on the screen tagged inline, so that invented figures are never read as real EPFO data.
22. As a reviewer, I want this screen to reuse the prototype's existing visual and interaction language (the PROPOSED panel, the action-card feed, the disclosure-toggle pattern, the status-steps timeline), so that it reads as one coherent product rather than a bolted-on demo.
23. As a member, I want the "was it resolved?" question to record my answer against the grievance record, so that a No or Partly is what drives the appeal, not a separate satisfaction rating divorced from escalation.
24. As a member, I want the appeal draft to cite the specific rule the office broke and the outcome I seek, so that the appeal is harder to close falsely than a generic re-complaint.

## Implementation Decisions

- **One new Revamped-only screen.** Add a `grievance` screen section, registered in the screen-title map and the hash router, reachable via the existing `go('grievance')` navigation helper. It is added to the Revamped sidebar navigation near Track Claim Status (Online Services group). No new routing primitive is introduced; it rides the existing hash-router seam (`render` / `applyRoute` / `navigate`).
- **Mode gating is absolute.** Every new element lives inside `.prop-only` scope. The Current Portal keeps a byte-faithful grievance control: in Current mode the grievance nav item links out to EPFiGMS exactly as the live site does (its existing inert/link-out behavior), never the in-app screen. The Current replica is not otherwise touched.
- **Promote, do not duplicate.** The EPFiGMS draft generation and copy-to-clipboard, the intent-gated dispute path ("I believe this rejection is wrong"), and the verified-closure check already prototyped inside Track Claim Status become the building blocks of this screen. Track Claim Status keeps its per-claim dispute entry, which now links into this screen carrying the claim's context, rather than holding a parallel grievance surface.
- **Reuse existing UI patterns, add no new primitives.** The screen is built from the established `.prop-panel` / `.prop-tag` PROPOSED block, the `.action-card` feed (default / warn / info / ok) for status and reminders, the disclosure-toggle micro-pattern (`toggleX()` with `aria-expanded` and a paired `id` block), and the `.status-steps` timeline (with the existing `done` / `warn` / `bad` states) for the 21-day-clock stages.
- **Symptom-based guided routing, deterministic.** A small set of plain-language "what went wrong" options maps to the correct EPFO office or queue, replacing a raw department tree. The mapping is deterministic (fixed option-to-route table), consistent with this project's standing preference for deterministic behavior until real usage data exists; no adaptive scoring is built.
- **Local, session-scoped grievance record; no backend.** The grievance is simulated in memory, consistent with how `submitClaim` and `verifyClose` already simulate outcomes. The record shape, from prototyping, is minimal:

  ```
  { ref, filedOn, dueOn /* filedOn + 21 days */, stage, atr, verifiedResolved: 'yes' | 'no' | 'partly' | null }
  ```

  The clock is computed at runtime in the browser from a fixed illustrative `filedOn`, so the countdown is demonstrable without any real submission. No `sessionStorage`-backed persistence is required unless a draft needs to survive navigation within the session.
- **Verified closure is the anti-false-closure core.** The closure step asks "was your problem actually resolved? Yes / No / Partly." A No or Partly reveals the pre-filled appeal with the 30-day appeal clock shown, matching the CPGRAMS research's central move (rating that unlocks appeal, made plain and one-tap). The answer is recorded against the grievance record.
- **Escalation ladder shown explicitly.** EPFiGMS, then CPGRAMS with its 21-day reply norm, then RTI or the relevant ombudsman, tilted toward a forum independent of the closing office. The appeal draft cites the specific rule broken and the outcome sought.
- **Illustrative-data labeling is a copy convention.** Every invented figure (resolution-time medians, demo reference numbers) carries an inline "(illustrative)" tag, per the standing project convention; this is a text-level change, not a new component.
- **Mode-switch and navigation reset.** A reset function returns the screen to a clean state, called both from the screen's route hook (`if(route.screen === 'grievance'){ ... }` in `applyRoute`) and from the mode-switch reset block, following the established `lastAppliedMode`-gated pattern used for Passbook, Modify Basic Details, Track Application Status, and Needs-attention, so Revamped demo state never leaks into the Current replica.
- **No real integration.** No actual EPFiGMS, CPGRAMS, or RTI submission; the flow simulates outcomes in-memory. This is the one category the spec does not implement, consistent with the prototype's honest "illustrative" framing elsewhere.
- **Zero em-dash rule holds for all new copy**, verified by grep after every edit, consistent with the project-wide standing rule for the prototype and its companion scorecard.

## Testing Decisions

- **No automated test suite exists in this project, and adding one is out of scope** (confirmed with the user). Verification reuses the existing screen seam, the same methodology used to verify every screen this project: serve the file locally and drive it with browser automation.
- **What a good test checks here** is the visible behavior a member or reviewer would actually see, not internal class names (except where a class is a load-bearing seam another feature relies on): does the symptom picker route, does the composer structure the text, does the 21-day clock render, does the appeal reveal on a No or Partly, does the Current Portal stay byte-faithful.
- **Modules exercised:** the new grievance screen and its interactions, plus the cross-link from a Track Claim Status claim detail.
- **The specific checks to run for this screen:**
  - Confirm the grievance screen and every new element appear only in Revamped mode (`body.v2` / `body.proposed`) and never in Current, by toggling `setMode('cur')` / `setMode('prop')` and checking `offsetParent` / computed `display`.
  - For each toggle or disclosure, confirm `aria-expanded` flips and the panel's `display` matches the button label.
  - Drive the full flow end to end: symptom pick, composer, submit, status and 21-day clock, verified-closure answer of No, appeal reveal; assert DOM state at each step.
  - Confirm the mode-switch and navigation reset returns the screen to a clean state, and that switching to Current mid-grievance clears simulated state.
  - Read the browser console for thrown errors after interacting.
  - Grep the file for em-dashes (expect zero) and run `node --check` on the extracted script after every edit.
- **Prior art:** this session's verification of the Track Claim Status dispute and verified-closure flow, and the Home, KYC, and Passbook in-browser checks (screenshot before and after, `aria-expanded` and computed-style checks, a full mode-switch check, and a console-error read) are the reference pattern to repeat.

## Out of Scope

- **Accessibility features** (Text-to-Speech, Dyslexia-friendly mode) surfaced by the same gap analysis. These are tier 2 and belong to a later spec.
- **Pension-lifecycle screens** (Apply for Pension, View PPO Details, Submit DLC / Jeevan Pramaan), also surfaced by the gap analysis. These are tier 3, lower-fit for this exiting-employee persona, and belong to a later spec.
- **Any real EPFiGMS, CPGRAMS, or RTI submission or backend integration.** The prototype has no backend; connecting one is a separate initiative, not a frontend fix.
- **The public department or ministry scoreboard and the cross-user accountability layer** described in the CPGRAMS research (aggregated resolution-time and false-closure metrics). The prototype is single-persona, the Office Scoreboard was deliberately removed earlier in this project, and the accountability research's two hard rules (never rank on a metric an office can improve by suppressing complaints; never expose a complainant, since CPGRAMS discloses identity) make a public scoreboard unsafe to model from one fictional member. Not reintroduced here.
- **Any change to the Current Portal replica** beyond keeping its existing byte-faithful grievance link-out.
- **Publishing or deploying the prototype anywhere.** It remains local-only.
- **Filing this spec into an actual issue tracker.** None is configured; that setup is a separate, explicit action for the user.

## Further Notes

- **Why this was the highest-priority gap.** Of the three tiers the live-site comparison surfaced, the Grievance screen lands most directly on the case study's core thesis (status legibility and verified closure), which is why it was chosen over accessibility (tier 2) and pension-lifecycle (tier 3).
- **Design grounding.** The screen is grounded in two existing project research files: `cpgrams-screen-redesign-2026-08-29.md` (screen-by-screen, with each change tagged `[Portal]` for a government-side lever or `[App]` for a citizen-side companion change) and `cpgrams-accountability-models-2026-08-29.md`. The `[App]`-tagged changes are the buildable ones and map directly onto this screen: guided symptom routing, the grievance composer, evidence and completeness prompts, the local timestamped record, the verified-closure question, the pre-filled appeal, and the escalation ladder.
- **Relationship to Track Claim Status.** This screen consolidates and promotes the EPFiGMS draft and verified-closure logic already prototyped there; it is a promotion of existing behavior into a first-class surface, not a new parallel system. That is deliberately what keeps the prototype internally coherent as it grows.
- **CPGRAMS versus EPFiGMS.** EPFiGMS is EPFO's own grievance system and the first rung; CPGRAMS is the central portal and the escalation target with its own 21-day reply norm. The screen names both correctly and does not conflate them.
- **If a tracker is configured later,** the natural split is one ticket per numbered user story above, with the Track Claim Status cross-link (story 13) flagged as touching an existing screen and the verified-closure and appeal stories (9 to 12, 23, 24) grouped as the anti-false-closure core.
