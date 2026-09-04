# CPGRAMS accountability: what to borrow from China, Japan, and others

**Date: 2026-08-29.** For the CPGRAMS candidate (ledger #4, the false-closure appeal kit). Research by two verified agents (China; Japan + Korea + Taiwan + Brazil). This file records the foreign accountability mechanisms and, for each, the change a citizen-side app can actually make. Companion to `international-analogues-per-candidate.md`.

## The reframe that decides everything

There are two layers, and they are not the same job:

- **State-side reforms** = what the government would have to change inside CPGRAMS itself (publish rankings, add deemed-escalation, fund an independent ombudsman). These are the real accountability levers, but you cannot ship them. They are a north star and a policy narrative, not your product.
- **Tool-side features** = what your citizen-side app can build with no government cooperation and no API (the board's standing rule). This is what you can actually launch.

The one-line thesis: **your app cannot rank the government by fiat, but it can become the scoreboard the government refuses to publish** — built from your own users' data. And the load-bearing lesson, learned from China's failure, is to score **verified resolution and citizen-confirmed satisfaction, never complaint volume** — because ranking on volume rewards suppressing complaints, not fixing them.

CPGRAMS already has: the 21-day clock, the interim-reply right, rate-"Poor"-unlocks-appeal (30 days), and the Samadhan Didi chatbot. So the accountability your app adds must be the things CPGRAMS does *not* do: a cross-citizen scoreboard, independently verified closure, collective escalation, and a recurring-failure report.

---

## China — the strongest mechanism logic, the darkest caveats

**12345 hotline + Beijing's 接诉即办 ("respond to complaints immediately").** A single non-emergency number turns every call into a tracked work order with a deadline, and the key move: a **public monthly leaderboard** ranking all districts and departments on three *separate* rates — acknowledgment speed, resolution, and **satisfaction measured by calling the citizen back** (not the department self-marking the ticket closed). Bottom-ranked leaders get summoned for "admonishing talks." Beijing reports ~25M cases in 2025 and 95%+ satisfaction (state self-reported, unaudited). A "monthly topic" process mines recurring complaint clusters into policy fixes.
- **Transplant:** the public, multi-rate, department-ranked scoreboard, with satisfaction verified by contacting the citizen, not by the closer.

**People's Daily 领导留言板 ("Leaders' Message Board").** Citizens post to *named* leaders, whose offices reply publicly on a visible thread; other users can see and comment.
- **Transplant:** named-owner public response with a visible open/closed status and response time — non-response becomes socially costly.

**信访 (xinfang / "letters and visits") + cadre KPIs.** A parallel petition system separate from line departments, where grievance performance rolls into officials' evaluations.
- **Transplant:** a parallel escalation ledger that gives the top independent visibility into whether local units actually closed cases, instead of trusting departments to grade themselves.

**The hard caveats (why China is not a model to copy whole).** The same KPI pressure that makes the mechanics "work" also produced petitioner **interception and "black jails"** (unlawful secret detention of petitioners; HRW 2009), because officials are rewarded for *stopping* petitioners who reach Beijing, not satisfying them. And self-closed metrics get gamed: researchers document "mechanical responsiveness" — perfunctory replies that hit the deadline and close the ticket while the problem stands (China Quarterly). The design inversions this hands you:
1. Never rank on a metric an official can improve by suppressing complaints. Rank on verified resolution, never complaint count.
2. Satisfaction must be citizen-verified, never self-closed.
3. Protect the complainant — accountability-by-visibility needs anti-retaliation design.
4. Curation is not transparency — a public thread only builds trust if what is shown is not pre-filtered.

---

## Japan — the closure loop and the human last mile

**行政相談 (administrative counseling), MIC Administrative Evaluation Bureau.** A free non-judicial channel that *mediates* with the responsible body and runs a **follow-up review to confirm a real change happened**; because the same bureau also evaluates policy, recurring complaints feed system redesign.
- **Transplant:** verifiable closure — never let "disposed" mean "resolved"; require a "did the fix actually happen?" check. And turn complaint *patterns* into process fixes, not just closed tickets.

**~5,000 volunteer administrative counselors (行政相談委員).** Statutorily appointed local civilians who take a citizen's complaint, advise, notify the agency, track escalation, and report the outcome back.
- **Transplant (the most India-relevant human idea):** a named, local, trusted last-mile helper layer for people who will never use a portal — assisted filing plus personal follow-through.

**行政不服審査 (administrative appeal), 2016 reform.** An appeal reviewed by an **examiner independent of the original decision-maker**, an independent review board inside MIC, and **published "standard review periods."**
- **Transplant:** a structured appeal reviewed by someone outside the original handler, against a published clock — the legible second look.

**Local ombudsmen (Kawasaki, 1990).** Independent, locally-legislated grievance investigators outside the responsible department.
- **Transplant:** an independent second channel at the local tier.

---

## South Korea — the published, ranked KPI (best fit for India)

**e-People / Sinmungo under the ACRC** (one agency merging the ombudsman, anti-corruption, and administrative-appeals bodies). A single portal with **statutory per-type clocks** (extension only with notice), **published citizen-satisfaction as a standing, agency-ranked KPI**, and an **independent ombudsman** second channel.
- **Transplant:** India already has timelines; the behavior-changing move is publishing *comparative* timeliness and satisfaction across departments. This is the exact thing your app can manufacture from user data.

## Taiwan — the guaranteed response and single intake

**JOIN (join.gov.tw).** A petition that gathers **5,000 endorsements in 60 days** becomes a formal case, and the responsible agency **must give a substantive, dated, on-the-record response within 2 months**.
- **Transplant:** threshold-triggered guaranteed response — cross a public bar and a named agency owes a visible, time-bound answer. The response is not a resolution, but it is mandatory and dated.

**1999 hotline.** One memorable number that guarantees routing plus a tracking ID.
- **Transplant:** single guided intake that always yields a case handle — the offline access fix.

## Brazil — unified, typed intake with deadlines

**Fala.BR (CGU).** One platform unifying grievances (ouvidoria) and information requests (their RTI), with **typed manifestations** (complaint, denunciation, request, suggestion, praise) routed differently, each with a **statutory deadline** (~30 days), under central oversight. The *ouvidoria* is framed as a "public defender of services."
- **Transplant:** guide the citizen to the right complaint type and the right statutory clock, and pair a grievance with an RTI in one flow.

---

## What to build into the CPGRAMS app (prioritized, tool-side)

1. **The scoreboard you build yourself (highest value).** Aggregate your users' outcomes into a public league table of departments/ministries by median resolution time, false-closure rate, and citizen-confirmed satisfaction. This is Korea's published KPI + Beijing's ranking + NYC open data, manufactured citizen-side because the state will not publish it. Rank on verified resolution, never on complaint count.
2. **Independently verified closure.** When a grievance is marked "disposed," ask the citizen "was it actually fixed?" and record that. That answer, not the portal's status, is what feeds the scoreboard. This is Japan's follow-up review and the direct antidote to China's metric-gaming.
3. **The automated escalation ladder with an independent tilt.** Rate-"Poor" → appeal (30-day clock) → RTI → Lokpal/CVC/relevant ombudsman, drafted for the user, always pointing to a forum outside the office that failed (Japan's examiner-independence; Korea's ombudsman).
4. **Collective / threshold escalation.** When N users report the same false-closure pattern at one department, package a joint, media- and RTI-ready dossier (Taiwan JOIN's threshold logic, citizen-side).
5. **The recurring-failure report.** Publish a periodic "top recurring grievance failures" summary from aggregated data (Japan's pattern-to-policy loop; Beijing's "monthly topic") — the app as watchdog input.
6. **Privacy-safe public posting.** A named-owner public thread (Leaders' Message Board logic) only if it can be anonymized, because CPGRAMS discloses complainant identity and retaliation is a real, documented risk. Privacy is the user's hard constraint; this feature must not endanger anyone.
7. **Guided, typed intake with the right clock.** Route the citizen to the correct category and compute the correct statutory deadline, and pair grievance with RTI (Brazil Fala.BR; Korea per-type clocks).
8. **A human last-mile option.** Assisted filing and, longer term, a helper network (Japan's volunteer counselors) for offline and low-literacy citizens.

## The honest ceiling

A citizen-side app manufactures **transparency and pressure**; it cannot **compel**. The levers that truly bite — real deemed-escalation, a binding independent ombudsman, published official rankings — are state-side. Two guardrails carry over from the research: never build a metric that rewards suppressing complaints (China's core failure), and never expose a complainant who can be retaliated against (China's black jails; CPGRAMS's identity disclosure). Within those limits, the scoreboard-plus-verified-closure model is the strongest, safest accountability a citizen-side tool can add.

Confidence note: foreign *mechanism designs and thresholds* are high-confidence; China's self-reported effectiveness rates are unaudited; a few scale numbers (Message Board counts, exact ranking formulas, Korea per-type day counts) were flagged unverified and should be confirmed before external citation.
