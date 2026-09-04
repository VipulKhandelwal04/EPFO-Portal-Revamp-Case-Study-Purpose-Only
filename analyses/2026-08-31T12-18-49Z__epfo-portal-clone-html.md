---
target: the revamped version
total_score: 30
max_score: 40
na_heuristics: 
p0_count: 1
p1_count: 2
timestamp: 2026-08-31T12-18-49Z
slug: epfo-portal-clone-html
---
Method: dual-agent (A: design-review agent · B: detector/browser-evidence agent)

# Design Health Score — Revamped Portal mode

| # | Heuristic | Score | Key Issue |
|---|-----------|-------|-----------|
| 1 | Visibility of System Status | 3 | Day counts/stage tables strong; screen changes and revealed panels give no signal they happened |
| 2 | Match System / Real World | 4 | Codes decoded into member language; residue: "re-seed" jargon undefined |
| 3 | User Control and Freedom | 2 | No routing/history; refresh dumps to login + re-armed popup; details can't collapse |
| 4 | Consistency and Standards | 3 | Green VERIFIED on the bank row contradicts the panel saying that row bounces claims |
| 5 | Error Prevention | 4 | Pre-flight check with Fix-first vs File-anyway is the heuristic done properly |
| 6 | Recognition Rather Than Recall | 3 | Deep links land off-viewport; cure must be carried in memory to a screen with no matching control |
| 7 | Flexibility and Efficiency | 2 | No bookmarkable state, no shortcuts, stat cards inert |
| 8 | Aesthetic and Minimalist Design | 3 | Clean grammar; case-study voice bloats citizen panels |
| 9 | Error Recovery | 4 | The structured rejection is the thesis screen and genuinely excellent |
| 10 | Help and Documentation | 2 | No help centre/glossary; footer Contact Us dead; jargon never expandable |
| **Total** | | **30/40** | **Good** |

# Design Specificity Verdict
LLM assessment: unmistakably authored for an Indian provident-fund portal, not a template — Indian digit grouping (₹ 4,82,915), real form taxonomy (Form-19/10C/31, Annexure K, joint declaration), plausible R-code system, EPFiGMS→CPGRAMS ladder with the 21-day norm, believable member IDs. The visual system is closer to generic admin-SaaS; the IA and copy carry the authorship.
Deterministic scan: CLI = 1 finding, judged false positive (offset 12%-alpha tinted shadow on a light page misread as glow-on-dark). In-page detector (injection succeeded; console read; no visible overlay claimed — tab group closed before overlay verification): 37 findings ≈ 30 real after removing the same dark-glow FP, the automation extension's own banner, and 2 unverified hidden-layer occlusion artifacts. Real clusters: PROPOSED chip at 10.5px (×10, one root cause), status pills at 4.46:1 and 4.0:1 (just under AA), 168–174-char line lengths in wide panels, 11.5px strings, all-caps breadcrumbs (intentional label styling), single-family font (expected for the brand).

# Priority Issues
1. [P0] The hero flow's cure step has no executable action: "re-seed the bank KYC" but the KYC screen has no update/re-verify control, and the bank row still shows unqualified green VERIFIED. Fix: add a Replace/re-verify action on the BANK row + caveat status (VERIFIED (SOFT MATCH) class of state) in revamped mode.
2. [P1] Dashboard deep links (See fix path / View and escalate) land at scrollTop 0 with the detail below the fold, and no focus move or announcement. Fix: scrollIntoView + focus the detail heading.
3. [P1] No routing/history/state persistence: refresh = logout + re-armed security popup + mode reset; Back exits. Fix: hash routes + pushState; arm popup once per session.
4. [P2] Keyboard dead weight: 4 focusable no-op sidebar group headers; go() never moves focus or updates title; stale Show/Hide aria-label; A-/A/A+ accessibility controls are dead.
5. [P2] Case-study voice leaks into citizen UI (illustrative tags, Japan/DARPG citations, "No new data pipe is needed", seeded-defects note on Home). Fix: distinct annotation layer.
6. [P2] Typographic floors (detector): 10.5px chip, pills just under AA contrast, over-long line lengths, 11.5px strings.

# Persona Red Flags
Alex: deep links show a table not the fix; F5 costs three interactions; inert Claims stat card; dead() demo buttons give zero feedback.
Jordan: VERIFIED pill wins over the warning text; "seed" never defined; fix-vs-contest compressed into one card line; EPFiGMS/CPGRAMS/UAN/TDS unexpanded.
Sam: four dead focusable headers per pass; no announcement on navigation; stale password-toggle label; dead Screen Reader Access controls; no skip link. (Working: focus-trapped dialog, aria-live results, scoped tables.)

# Emotional Journey
Entry valley: security-threat popup precedes value, re-arms each refresh. Peak: "Nothing else is wrong with this claim" + 34% reversal stat converts shame into agency. Unframed valley: raw all-caps rejection block renders uncaptioned in revamp (its explainer is cur-only). End: rejected flow ends at a readonly textarea (no copy/open/submit); settled flow's verified-closure ending is the trust high-point.

# Minor Observations
Office Scoreboard orphaned last in sidebar without group label; hero CTA is File-a-claim while the member's defining problem is the rejection; det-c timeline order (undated grey step last); replica leftovers in revamp (social letter-circles, login badge, popup); strengths: tabular-nums, consistent PROPOSED chips, row-you scoreboard highlight.

# Questions to Consider
1. If seeding is soft-match and scrutiny exact-match, why keep a single binary VERIFIED vocabulary — shouldn't status express "verified for claims" vs "verified for seeding"?
2. The 34% contest stat shows on a correctly-rejected claim; does it recruit the 66% into losing grievances, and should the contest block be gated on "I dispute the facts"?
3. If every PROPOSED chip and feasibility footnote were stripped tonight, would each screen still stand as a product a citizen would trust — and if yes, why aren't they stripped?
