# 05: Track Claim Status cross-link into grievance

**What to build:** From a rejected or stalled claim's detail in Track Claim Status, a one-step link takes the member to the grievance screen with the composer pre-filled from that claim's context (claim ID, rejection code, dates), so the loop from a bounced claim to a filed grievance is a single move rather than a fresh start.

**Blocked by:** 02.

**Status:** done

- [x] A rejected or stalled claim detail in Track Claim Status offers a one-step "raise a grievance about this" action, Revamped only. *(Rejected claim det-b gained a `.prop-only` "Raise a grievance about this claim" button next to the dispute toggle; stalled claim det-c's placeholder "Raise grievance (demo)" button, already inside a `.prop-only` panel, now cross-links instead of dead().)*
- [x] Following it opens the grievance screen with the composer pre-filled from that claim (claim ID, rejection code, filed and rejected dates). *(`raiseGrievanceForClaim(key)` stashes a per-claim payload in `GRV_PREFILL` and navigates; `applyGrievancePrefill()` runs on the grievance route hook AFTER resetGrievance() so the reset does not wipe it. The what-text carries the claim ID, R-07/OTHERS codes or the breach receipt, and the filed/rejected/breach dates; symptom, rule, and outcome pre-fill too, and the routed office renders.)*
- [x] The cross-link is `.prop-only`; Current mode keeps its existing per-claim behavior unchanged. *(Both buttons are inside `.prop-only`; in Current mode the claim detail still renders, the buttons are hidden, and `raiseGrievanceForClaim` guards on currentMode and returns `dead()` without navigating.)*
- [x] Verified in-browser: the link carries the claim context and the composer pre-fills; mode-gated. Zero em-dashes; `node --check` passes. *(Real clicks on both buttons landed on an active grievance screen with correct pre-fills; a plain navigation to grievance has an empty composer (no prefill leak); Current-mode buttons hidden, `raiseGrievanceForClaim` returned false and stayed on Track. No console errors; chained cross-link to submit to second cross-link ran without a thrown exception.)*
