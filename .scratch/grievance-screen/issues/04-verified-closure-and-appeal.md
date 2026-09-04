# 04: Verified closure, appeal, and escalation ladder

**What to build:** When a grievance is closed (illustrative), the member is asked plainly whether it was actually resolved. A No or Partly answer reveals a pre-filled appeal with the 30-day appeal clock and the escalation ladder, so a false closure surfaces the appeal path instead of being passively accepted. This is the anti-false-closure core of the screen.

**Blocked by:** 03.

**Status:** done

- [x] On closure, a verified-closure question offers Yes / No / Partly and records the answer against the grievance record. *(`#grv-closure` sub-panel appears when the demo control moves the grievance to the closed stage; `verifyGrievanceClosure('yes'|'no'|'partly')` sets `GRV.verifiedResolved` and adds a member-verdict step to the timeline. Reuses the Track Claim Status verified-closure framing, Japan follow-up / DARPG feedback-call precedent.)*
- [x] A No or Partly answer reveals the appeal, pre-filled with the original grievance text and the closure note verbatim, and citing the specific rule the office broke and the outcome sought. *(`GRV.what` / `GRV.outcome` / `GRV.rule` are captured at submit; the readonly appeal draft interpolates them plus the closure note verbatim and addresses an appellate authority independent of the closing office.)*
- [x] The appeal shows the 30-day appeal clock and the escalation ladder: EPFiGMS, then CPGRAMS with its 21-day reply norm, then RTI or the relevant ombudsman, tilted toward a forum independent of the closing office. *(`grvAddDays(closureOn, 30)` computes the appeal-window date at runtime, e.g. closure 26-09-2026 to 26-10-2026 (illustrative); the ordered ladder ends with a note that a forum independent of the closing office is the strongest.)*
- [x] A Yes answer closes the loop without surfacing the appeal. *(Yes records citizen-verified resolved and keeps `#grv-appeal` hidden; verified on-screen via offsetParent.)*
- [x] Verified in-browser on both the Yes path and the No/Partly path, mode-gated, with reset clearing the recorded answer. Zero em-dashes; `node --check` passes. *(Both paths asserted with genuine navigation (real hashchange) and offsetParent visibility, not just direct calls. Reset (route hook + mode-switch block) returns stage to 'open', clears the verdict, and hides the closure and appeal blocks. In Current mode the screen redirects to home and `setGrievanceClock`/`verifyGrievanceClosure` fall through to `dead()` without mutating `GRV`. No console errors; full lifecycle flow ran without a thrown exception.)*
