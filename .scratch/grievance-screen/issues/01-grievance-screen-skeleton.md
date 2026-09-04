# 01: Grievance screen skeleton

**What to build:** A member can reach a new Grievance Redressal screen in the Revamped Portal, from the sidebar navigation (Online Services group, near Track Claim Status) and via its hash route, and it shows a minimal PROPOSED shell. The screen appears only in Revamped mode and never in Current; in Current mode the grievance control stays byte-faithful to the live site (a link out to EPFiGMS, no in-app screen). Re-entering the screen or switching modes returns it to a clean state. This is the walking skeleton the report, track, closure, and cross-link tickets build on.

**Blocked by:** None (can start immediately).

**Status:** done

- [x] A `grievance` screen is registered in the hash router and the screen-title map; both `go('grievance')` and the `#/revamped/grievance` route open it.
- [x] The screen appears in the Revamped sidebar navigation (Online Services group) and only in Revamped mode.
- [x] All new screen content is `.prop-only`; toggling to Current mode hides the screen entirely, and the Current grievance control keeps its existing byte-faithful link-out behavior, never the in-app screen. *(Implemented Revamped-only, like the Profile screen: the nav item is `.prop-only` and a Current-mode route redirects to home. No control was added to the Current replica, since it has no grievance item today and adding one could not be justified as byte-faithful without a verified source. See completion note.)*
- [x] A reset function is wired into the screen's route hook and the mode-switch reset block, following the established lastAppliedMode-gated pattern, so no Revamped demo state can leak into the Current replica. *(Placeholder `resetGrievance()` in place; tickets 02-04 hang their state on it.)*
- [x] Verified in-browser: opens from both the nav and the route, is mode-gated in both directions, leaves the Current replica untouched, and logs no console errors. Zero em-dashes; `node --check` passes on the extracted script.
