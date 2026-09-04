# Per-candidate complaint scan: X + Reddit vs the 18 candidates

**Date: 2026-08-29.** Purpose: for each of the 18 candidates on `problem-discovery-ledger.md`, find what people actually complain about, extract the essence of the discomfort, and re-rank the board with **"can a product be built around this complaint"** as the sole criterion.

**Method.** X: 18 live searches through the logged-in browser (reply firehoses `to:socialepfo`, `to:UIDAI`, `to:passportsevamea`, `to:RailMadad`, `to:MCD_Delhi`, `to:esichq`, `to:fssaiindia`, `to:IncomeTaxIndia` + keyword searches), captured 2026-08-29. Reddit: 4-agent workflow; the Arctic Shift archive API was down (HTTP 500 all session), so agents pivoted to old.reddit.com search via the browser, Reddit's RSS search endpoints, Wayback snapshots, and WebSearch for news that quotes threads. ~60 searches, 2024–2026 focus. Quotes lightly compressed verbatim; sources cited as subreddit + title + date (permalinks where captured).

**Ranking criterion decomposed:** (a) is there live, recurring complaint evidence; (b) is the expressed lack information-shaped (something a tool can supply: decode, checklist, route, clock, draft) vs enforcement-bound (only the state acting fixes it); (c) is the fix knowledge verifiable against primary sources; (d) is the complaining population reachable; (e) does using the product produce a measurable win.

---

## The re-ranked board

### 1. EPF claim rejection decoder (was #1 — holds)
- **Evidence:** STRONG on both channels. Aug 27 X replies to @socialepfo: claim "rejected by field office but **zero remarks/reasons shown** on portal or passbook"; EPFiGMS throwing "No record found" when they try to complain. Reddit r/epfoindia: rejected with `WARNING-520160 MULTIPLE MEMBERID FOR SAME BANK ACCOUNT`; three stacked reasons in one remark ("eps contribution not deposited…::RETURNED FOR UPLOADING READABLE BANK PASSBOOK…::RETURNED FOR SUBMITTING CORRECT FORM 15G/15H" — "I am so confused, what to do about this now, I am unemployed since 3 months"); UMANG says rejected while the portal says pending.
- **Essence:** your own money, urgently needed, held hostage by an ALL-CAPS machine remark nobody can parse — and when several reasons are stacked, no way to know which one is operative. The complaint channel itself errors or disposes without resolution.
- **Buildability:** the purest fit. Complainants lack exactly three supplyable things: remark translation, the operative-defect call, and the escalation ladder (a success post shows resolution came only after finding the buried EPFiGMS category *PF Member → Pre Pension → Non Settlement under EPS 95*, then CPGRAMS). Dedicated subreddit exists; a fintech (FinRight/CheckMyPF) already runs paid AMAs there — demand is proven. Residual tail (defunct employers, field-office backlog) is enforcement-bound.

### 2. GST registration SCN decoder (was #16 — big riser)
- **Evidence:** STRONG both channels. X Aug 28, 10K views: portal auto-picks state jurisdiction from PIN code, officer issues SCN saying "wrong jurisdiction, hence will be rejected" — a CA asking publicly how to respond. Reddit r/IndiaTax: "Every time I respond to one clarification, they come back with another petty one… I'm literally trying to register so I can pay taxes"; "rejected twice saying field visit found negative, but actually there was no field visit"; "Am I missing the 'bribe' factor?"
- **Essence:** people trying to ENTER the tax system are locked out by document demands the CBIC itself has banned (Instruction 03/2025), each rejection resets the clock, and the 7-working-day REG-04 deadline produces visible panic (cross-posting to 4 subs).
- **Buildability:** knowledge demonstrably flips outcomes fast: one poster took the Rule 14A route "as suggested" and got a GSTIN **within 1 hour**; another cited Instruction 03/2025 in REG-04 + PG Portal + RTI and moved to "pending for order". DIY guides (46-pt, 155-pt) circulate for years — the product is those guides made interactive. Officer discretion/fabricated reports remain enforcement-bound, but deemed-approval + citation leverage is real.

### 3. Health-insurance rejection → ombudsman kit (was #12 — riser)
- **Evidence:** STRONG on Reddit, moderate on X. One-line repudiations ("Possibility of pre-existing disease could not be ruled out. That's it. No evidence."); "Once Niva Bupa maintained rejection, I felt I was **left alone to fight the case**" (117 pts); ombudsman win posts evangelize ("never be afraid… they never side with these white collared cheats", 356 pts); the cardiac-claim playbook post (settled in 4 weeks via written-representation capture + IRDAI + CPGRAMS) at 51 pts.
- **Essence:** lakhs paid out of pocket on evidence-free one-liners; abandonment once the insurer digs in; the winning ladder (GRO → Bima Bharosa → Ombudsman) exists but is discovered by folklore.
- **Buildability:** high — decode + evidence discipline + drafting, all verifiable against Ombudsman Rules 2017. Honest caveats: award-enforcement gap at the ladder's end (ICICI Lombard ignoring an award, 480 pts, "no one knows who is supposed to make them accept it"); framing is regulated-private, fits the case study as statutory grievance machinery.

### 4. CPGRAMS false-closure appeal copilot (was #5 — riser)
- **Evidence:** STRONG. Reddit: "closed with saying everything is working fine, but it isn't"; escalated-next-level → "the very next day I got a call… she personally transferred the recharge amount **from her own bank account** so she could close the complaint"; the India Post win ("Local staff count on us not knowing the rules… Don't withdraw until you have your money in hand", 217 pts, 4 days old). X: grievance IDs thrown publicly at @DARPG_GoI/@PMOIndia; income-tax grievances "closed with copy paste response".
- **Essence:** disposal is a paper event, not a fix — and the counter-lever (rate Poor → appeal to Nodal Appellate Authority within 30 days) is unknown to nearly everyone. Officers fear the documented record more than the problem; closure-pressure calls prove it.
- **Buildability:** unusually high — the missing thing IS knowledge + mechanics + drafting, and the appeal lever demonstrably bites. It is also the escalation module inside candidates 1, 2, 3, 5, 6, 9. Residue: entrenched local officers (a 3-year, 8-filing case where appeals fail because the decider is the problem); retaliation anxiety needs design care.

### 5. Aadhaar update rejection loop (was #3)
- **Evidence:** STRONG, continuous, both channels. X (15 min before capture): "Update request has been **rejected 3 times**" for removing a middle name; "rejected again and again despite registered lease and licence agreement… My ₹2x75 is already gone." Reddit: domicile certificate on UIDAI's own accepted list rejected as invalid; no SMS/notification of rejection; "How I forced Aadhaar to do its work" — an RTI unblocked in days what a grievance ignored for a month (UIDAI's own pincode data was 10 years stale).
- **Essence:** a one-word "Rejected" with no reason and no code, fee lost per attempt, agents succeeding "through the backdoor" for ₹200-300 — the opacity plus the loop, framed by users as a revenue racket.
- **Buildability:** good but capped: pre-submission document check, rejection decoding, RTI/CPGRAMS drafting all match the expressed lack — but validator behavior is genuinely arbitrary (same valid document rejected twice), so the tool improves odds and shortens the loop without guaranteeing acceptance. Correctness risk is the highest of the top tier.

### 6. ITR refund holds (was #9 — riser)
- **Evidence:** STRONG both channels. X: filed 9 June, no refund, "grievances just closed with copy paste response". Reddit: 10 months pending, "checking status feels like a ritual" (21 pts); "It's literally like begging for our own money" (37 comments); the Section 245 explainer — "if you do not respond within 30 days, the system treats your **silence as consent** and the adjustment proceeds" (24 pts).
- **Essence:** randomness is half the torment (later filers paid in minutes); the money is earmarked (fees, EMIs); grievances return boilerplate.
- **Buildability:** mixed, tilting buildable — a real fraction of "delays" have discoverable causes the filer never surfaced (S.245 set-offs, Schedule FA flags, failed bank pre-validation): the upvoted explainer posts ARE the product in prose. But the largest cohort is pure CPC backlog where only honest status legibility helps. Crowded adjacency (CA/ClearTax) serves filing, not stuck-refunds.

### 7. NSP scholarship black hole (was #7 — validated upward)
- **Evidence:** STRONG on Reddit (the sweep's surprise), weak on X. "Customer care told me the Nodal officers' numbers **do not exist**… I've had to take a loan to pay my fees"; "I got selected in October, I will graduate within two months… To whom will I complaint" (148 comments); defect SMS "UPLOAD INC" with an unknown correction deadline; 90–148-comment threads form around pure status-sharing; peers hand-write pipeline guides because of DM floods.
- **Essence:** told you won, then ghosted through a five-stage pipeline (institute → state → PFMS → NPCI seeding → bank) with cryptic statuses, dead helplines, and loans bridging the promised money.
- **Buildability:** strongly info-shaped: stage map + status/defect decoding **with correction deadlines** (missable windows = forfeits) + realistic per-scheme timelines + escalation. Cannot make PFMS pay — the honest product relieves uncertainty and prevents deadline-miss forfeits. Seasonal; students highly reachable.

### 8. Reserved-seat evidence playbook (was #2)
- **Evidence:** STRONG both channels, constantly live (X, 13h before capture: "my seat is occupied by unauthorized person… he is arguing and not leaving"). Reddit nuance: RailMadad often DOES respond ("Rail madad sent the TTE and they deboarded", 55 pts) — but resolution pushes identification risk onto the passenger (203-pt thread), TTEs are a coin-flip, and fake-rule folklore ("we have RAC") beats passengers who don't know berth rules. The Palakkad ₹75k consumer-court win turned on a timestamped in-journey complaint + photos — now itself national news (BusinessToday, Aug 28, quoting a Reddit post).
- **Essence:** a confirmed berth must be personally enforced in real time; the fear is the confrontation and not knowing the rules being quoted at you.
- **Buildability:** the in-the-moment slice stays enforcement-bound, but the buildable slice is sharper than before: berth-rules card (kills fake-RAC claims), file-now-with-photos prompt (triggers on-train action AND builds the court-grade record), compensation playbook. Correction to prior framing: RailMadad is not a dead channel; the gap is know-how and evidence discipline.

### 9. Passport PV stall triage (was #4)
- **Evidence:** STRONG both channels. X (16h): "police verification completed 24 July, passport still not issued… status not progressing." Reddit: 6-month PV stalls in Kolkata; "I paid 4000 as he demanded"; constable demanded ₹1000, refusal → application stuck; post-PV "under review at RPO" black hole with RPO unreachable.
- **Essence:** two silent states (stuck at PV; stuck after PV) with no norm to compare against — "is it normal?" is the genre's title — plus a visible bribe gate where refusal is punished.
- **Buildability:** split. Status legibility + city-timeline norms + escalation sequencing (RTI/CPGRAMS/SP office) matches what posters eventually reverse-engineer. But the hardest documented case had already used every route a tool could suggest and was still stuck; the cold-start problem on "normal timelines" stands.

### 10. Municipal false closure (was #6)
- **Evidence:** STRONG both channels. X (17h): "Complaints are not even attended for weeks or months together. **Pl stop telling lies**"; reopened complaint "marked resolved without any sweeping." Reddit: closed with "a random blurry photo which isn't even the spot," twice; "Not Relevant" + black-image closures (301 pts); an Assistant Commissioner disposing after 93 days with no Action Taken Report.
- **Essence:** being lied to on the record — evidence-backed reports overwritten by official fiction, manufactured disposal statistics.
- **Buildability:** split honestly down the middle. Demand for the escalation ladder is proven (a 1,300-upvote "How I Got a Footpath Repaired Without Bribes" post is literally the manual others keep asking for; reopen + poor-rating persistence works for those who know it; an external evidence ledger has standalone value). But the closure loop is gamed by the same office that answers the reopen, and the ladder is city-specific — fragmentation caps it.

### 11. Pension / family-pension stalls (was #8)
- **Evidence:** MODERATE volume, extreme stakes, both channels (X: family of a deceased UP head constable, 29 documents, 3+ months, running a dedicated account tagging the CM). Reddit: 11 months stalled "for vague reason… without knowing where the file is stuck or which authority is responsible"; a widow's file rejected repeatedly for a Class-10 certificate lost 45 years ago; "no guidelines" invented for an adopted child.
- **Essence:** survival income plus dignity — elderly pilgrimage visits, piecemeal document demands, scam vulnerability, grief taxed by paperwork.
- **Buildability:** the expressed ask is exactly buildable ("is there a portal", "what authority", "how to escalate") and the one success story resolved days after a properly-routed CPGRAMS filing. But a real subset is enforcement-bound (treasury stalls, legally rigid demands), volume is scattered with no hub, and execution fragments across state treasuries/banks/EPS. Natural ring-2 of #1, not a standalone.

### 12. UDID clock + appeals (was #14)
- **Evidence:** MODERATE — scattered small subs, low engagement, but the purest info-gap signature relative to volume: nearly every post is literally a process question ("Do I need to take any action to advance past this stage?", "who enters the percentage?", "19 digits instead of 18… how could I proceed further?"). Nobody in any thread cites the actual appeal mechanism. X adds a cross-recognition failure (railway portal rejecting a valid UDID).
- **Essence:** opaque states where you don't know if you must act; rushed hostile assessments; cards with errors and an unknown correction/appeal path — posts end in "how do I proceed?"
- **Buildability:** the statutory clocks and S.82 RPwD appeal routes are verifiable and unknown — direct match. Capped by thin observable crowd and state-board execution variance; NGO partner channels (nayi-disha etc.) are the realistic reach.

### 13. Footpath obstruction router (was #11 — riser within the bottom half)
- **Evidence:** STRONG volume (898-pt, 236-pt, 243-pt threads), and the recurring cry is precisely routing-shaped: "**Is there anywhere I could raise a complaint against this?**"; "whom to approach first at the station… how to escalate while I am there?"; officer-roulette ("I'm not in charge", call cut). Direct confrontation risks violence (assault/chokehold thread, 243 pts).
- **Essence:** pushed into live traffic by parked vehicles and debris, with no idea which of 3+ bodies owns the pavement — misrouted complaints die as "Not Relevant."
- **Buildability:** the traffic-police photo route (BTP/Astram) demonstrably produces challans and few know it — that slice is real. But the municipal half inherits #10's false-closure enforcement problem, cleared encroachments return, and sometimes no body accepts ownership. Router knowledge is thin and city-fragmented; better as a module inside a municipal tool than standalone.

### 14. Pothole injury compensation kit (was #10 — big faller)
- **Evidence:** raw pain enormous (953–4,175-upvote death/injury threads) but **compensation is absent from the vocabulary**: in dozens of high-engagement injury threads nobody mentions the BBMP scheme, the 30-day claim window, or any HC route; a victim asked whether to sue the tyre manufacturer; top advice on a bleeding-injury post was a tetanus shot. X confirms: media "know your rights" videos exist (one posted 26 min before capture), no citizen claim-experience posts.
- **Essence:** fear plus learned fatalism — "we are paying taxes to end our lives in this way?"; the sub's satirical commandments include "Thou shalt not complain of potholes."
- **Buildability:** the awareness gap is total, which cuts both ways: the entitlement + clock + evidence checklist is fully supplyable and verifiable, but **demand is latent, not expressed** — nobody is asking for this product, so it needs moment-of-injury distribution the team doesn't have, and payouts are enforcement-bound (HC has had to pull up BBMP for not paying). A product built around this complaint has no complaining users to meet.

### 15. PM-JAY desk denial rights card (was #15 — holds, for new reasons)
- **Evidence:** MODERATE, news-skewed (1,088/1,205-pt shared videos: "government hasn't paid us in 8-10 months, pay cash or leave"). The defining first-person story: a brother scraped the NHA hospital list into Excel and cold-called dozens of empanelled hospitals for his pregnant sister — almost all said delivery isn't covered (531 pts). X (14h): heart-attack patient refused admission in Delhi. **Not one thread mentions 14555 or CGRMS**; people literally ask "is there any way to complain against such malpractice?"
- **Essence:** card in hand, desk says no — and the refusal is openly blamed on the state's own unpaid reimbursements.
- **Buildability:** the escalation-route gap is real and answerable (a small verified rights + channels card). But the root cause is fiscal (no tool makes an unpaid hospital admit a patient), the coverage-truth layer decays weekly and defeated even a maximal DIYer, and the beneficiary population is the least reachable digitally. Highest social value, weakest product traction.

### 16. ESIC entitlements decoder (was #13 — big faller)
- **Evidence:** WEAK on these channels — n≈2-3 substantive complaints (a ₹1.6L/dose injection discontinuation threat; an essentiality-certificate dead-end), drowned by esports-ESIC and medical-college noise; r/ESIC is empty; X replies to @esichq are mostly non-complaints. The 507-pt Bengaluru thread's outrage is about Hindi imposition, not claims.
- **Essence (where found):** severe and info-shaped — rights during an income inquiry, how to complete reimbursement paperwork, with nobody to ask.
- **Buildability:** the thesis (unknown reimbursement entitlement, verifiable circulars) survives, but it **cannot be validated from social channels** — the insured population (wages ≤₹21k) isn't on English Reddit/X. Validation requires unions, vernacular channels, dispensary queues. B2B2C pairing with #1 remains the strategic hook; as a complaint-anchored candidate it drops.

### 17. FSSAI tier + renewal clock (was #17 — confirmed weak)
- **Evidence:** WEAK. The hypothesized traps (wrong tier, ₹100/day late fee) produced no first-person threads in three searches. What surfaces: low-engagement "how do I even start" questions, and the one high-engagement thread (97 pts) is an officer punishing a shop for renewing online — "When it comes to me for inspection, you'll have to pay even more for disturbing me" — pure enforcement, which the design principle rules out as a target. A founder validating a renewal-tracking tool got near-zero response.
- **Buildability:** cleanest build, no complaint mass to anchor it — the confusion is real but already monetized by agents offline, invisible on these channels.

### 18. Municipal trade licences (was #18 — confirmed last)
- **Evidence:** NONE citizen-side. Search space is Dubai/UAE licences and agent adverts; X has only policy news. The scraps: a KSmart portal charging a ₹200 late fee for the corporation's own payment failure (3 pts); shop-establishment renewal as one line in a 136-pt general compliance-overload rant.
- **Buildability:** no complaint mass, audience absent from these channels, city-fragmented. Slice folds into any future compliance umbrella; dead as a standalone.

---

## What moved and why (criterion: build a product around the complaint)

**Risers:** GST SCN (#16→2: knowledge flips outcomes in hours, proven), insurance ombudsman (#12→3), CPGRAMS appeal (#5→4: the lever bites, nobody knows it), ITR (#9→6: hidden-cause decoding), NSP (#7→7: 148-comment status threads + peer-written guides = expressed demand), footpath (#11→13 within-tier).

**Fallers:** pothole kit (#10 was "strong" → 14: thousands of upvotes of rage, zero claim attempts — latent demand needs distribution we can't assume); ESIC (#13 was "strong" → 16: the audience isn't on these channels — a visibility fact, not proof of no pain).

**Cross-cutting confirmations:** the false-closure meta-pattern appears inside candidates 1, 3, 5, 6, 9, 13 (grievances disposed with boilerplate); the "escalation knowledge flips outcomes" pattern (RTI/CPGRAMS/appeal/Rule 14A) appears in every top-6 candidate — the top of this ranking is the set of places where that flip is fastest, most verifiable, and most reachable.

**Honest limits of this scan:** Reddit/X skew English, urban, salaried — ESIC, PM-JAY, trade-licence, pension audiences are structurally undercounted ("none found here" ≠ "none exists"). Engagement figures are as displayed at capture. Arctic Shift was down; agents used old.reddit search/RSS/Wayback instead and flagged where permalinks couldn't be captured.
