# Problem discovery ledger — govt case study

**Status: DISCOVERY PHASE (open as of 2026-08-28). No problem is final.** Each candidate is scored on the same lens; new candidates get added as they're explored. Lens:
- **Pain evidence** — documented, recurring, mass complaints (social data, court records, official stats)
- **Failure type** — information / process-design failure (solvable by our kind of product) vs enforcement / record-writing failure (not solvable API-free)
- **Correctness** — can the fix knowledge be verified against primary sources (misinformation guardrail)
- **Uniformity** — central & uniform vs state/city-fragmented
- **Success metric** — can we measure that the problem actually got solved
- **Crowding** — who already serves it (tools vs static content)

Standing design principle: system design that removes the leverage, never anti-bribery. AI-built, so build cost is not a filter; validation and correctness are.

## 2026-08-29 re-rank: complaint-evidence × buildability
Full X+Reddit per-candidate scan in `candidate-complaint-scan-2026-08-29.md` (essence of discomfort + quotes + buildability per candidate). Criterion: can a product be built around the expressed complaint. New order:
**1** EPF decoder (#1) · **2** GST SCN (#16) · **3** Insurance ombudsman (#12) · **4** CPGRAMS appeal (#5) · **5** Aadhaar loop (#3) · **6** ITR refunds (#9) · **7** NSP scholarships (#7) · **8** Train-seat playbook (#2) · **9** Passport PV (#4) · **10** Municipal false closure (#6) · **11** Pensions (#8) · **12** UDID (#14) · **13** Footpath router (#11) · **14** Pothole kit (#10) · **15** PM-JAY (#15) · **16** ESIC (#13) · **17** FSSAI (#17) · **18** Trade licences (#18).
Biggest moves: GST SCN up (knowledge flips outcomes in hours — Rule 14A → GSTIN in 1 hour); NSP validated up (148-comment status threads, peer-written guides); pothole kit down (mass injury rage, zero claim attempts — demand is latent, needs distribution); ESIC down (audience absent from English social channels — visibility fact, not proof of no pain). Nuance correction: RailMadad is NOT a dead channel for seat complaints; the gap is rules know-how + evidence discipline.

**2026-08-29 international analogues:** per-candidate foreign mechanisms + pitfalls + smallest India transplant (state-side and tool-side) in `international-analogues-per-candidate.md`. Key patterns: closed lists beat discretion; the clock is the right but silence must leave a receipt (Italy's deemed-approval attestation); published norms/league tables are spreadsheet-cost accountability; rights that require claims go unclaimed everywhere (<1% US health-claim appeals despite ~50% overturn — the global gap our tools occupy); every mechanism has a documented counterattack (threat model). Best single stat: UK PIP — 91% of successful disability appeals present no new evidence; the appeal itself is the intervention.

---

## Candidate board

### 1. EPF claim rejection decoder — Employment · EPFO
Remark in → plain meaning (EN/HI) → complete ordered fix path (you/employer/EPFO) → escalation draft (EPFiGMS → CPGRAMS 21-day clock) when fault isn't the user's.
- Pain: ~34% final-settlement rejection rate FY22-23 (~25 lakh/yr); ~21.6% combined reject+return late 2024. Own money locked at worst moments.
- Failure type: pure rejection-loop information failure. Fix path actually resolves the problem.
- Correctness: verifiable (EPFO circulars, joint declaration rules). Uniformity: fully central. Success: binary (claim settles).
- Crowding: static SEO guides only (epfo.app, kustodian.life); no interactive decoder.
- Status: **deep-dived; strongest candidate so far.** Open question: enumerate the actual remark list (KB feasibility check).

### 2. Reserved-seat occupation → in-journey evidence/compensation playbook — Transport · Railways
Timestamped RailMadad filing during journey = the evidence that wins compensation later (Palakkad Consumer Commission: ₹50k + ₹25k for a family whose confirmed sleeper berths were overrun, complaint filed 8:12pm in-journey).
- Pain: massive, constant genre; our sweep caught a RailMadad complaint closed by the accused TTE himself.
- Failure type: ⚠️ core problem is ENFORCEMENT (no info layer recovers the seat in the moment). Only the after-the-fact compensation slice is an information failure.
- Correctness: good (consumer-court precedents, refund rules). Uniformity: central. Success: measurable but delayed (compensation, months).
- Status: explored 2026-08-28. Viable only as narrow "evidence pack + claim playbook" tool; does not solve the lived moment.

### 3. Aadhaar update rejection loop — Identity · UIDAI
Same decoder pattern as EPF: which document combo passes, why rejections happen, HOF route, escalation.
- Pain: enormous & continuous (X reply firehose to @UIDAI; 6+ Reddit threads/yr; fee lost per attempt).
- Failure type: rejection-loop information failure — but UIDAI behavior is inconsistent/opaque.
- Correctness: ⚠️ weakest point — advice risks being confidently wrong (folklore-based). Liability guardrail strained.
- Status: explored; parked pending a feasibility check on how deterministic rejection causes really are.

### 4. Passport police-verification stall triage — Documentation · MEA/police
Dates in → "normal wait vs stuck" verdict → escalation drafts (RPO grievance, CPGRAMS, tweet template).
- Pain: high, visible (X reply firehose; 5,215-upvote tweet-instead-of-bribe thread).
- Failure type: silent-stall information failure + the offline bribe chokepoint (which we don't touch).
- Correctness/cold-start: ⚠️ "normal timeline" data doesn't exist day one — needs crowdsourcing before it's honest.
- Status: explored; parked on cold-start problem.

### 5. CPGRAMS false-closure appeal copilot — cross-sector meta
"Closed without being fixed" → check 21-day/interim-reply rules → rate-"Poor"-to-unlock-appeal → appeal draft.
- Pain: false closure = the #1 meta-complaint in all our social data.
- Crowding note: filing side now crowded (paid RTI services; govt's Samadhan Didi AI since May 2026). Follow-through side empty.
- Status: deep-dived as broad direction; superseded by go-narrow instruction, but its DNA (escalation module) lives inside candidates 1-4. Could return as the umbrella later, assembled bottom-up.

### 6. Municipal complaint false closure — Municipal · MCD 311/BBMP etc.
- Pain: severe (fake-photo closures, jurisdiction ping-pong; 410-upvote threads).
- ⚠️ City-fragmented (jurisdiction mapping is the hard unsolved part); verifiable-closure needs network effects.
- 2026-08-28 update: the official Swachhata/ichangemycity stack (Janaagraha-built, MoHUA-official) already mandates per-category SLAs of 12 hours to 1 week and has citizen reopen/vote buttons — yet fake-photo closure persists per user reviews. So the "expect + escalate" slice (SLA clocks + what to do on false closure) is verifiable against official SLAs — a narrow slice that doesn't require jurisdiction mapping.
- Status: explored; weak fit standalone, but the SLA-clock slice upgrades it slightly.

### 7. Scholarship/NSP disbursement black hole — Education/Welfare
- Pain: real and cruel (exam forms blocked over unpaid fees; 10-month verification black holes); mostly low-visibility help posts, moderators remove some.
- ⚠️ NSP internals opaque; seasonal; users hard to reach.
- Status: surfaced in sweep; not yet drilled.

### 8. Pension / family-pension stalls — Welfare · EPS/banks/treasuries
- Pain: stuck 7-11 months; invented requirements ("no guidelines for adopted children"); users are elderly, posts filed by adult children.
- Adjacent to candidate 1 (same EPFO machinery for EPS); could be its ring-2 expansion rather than standalone.
- Status: surfaced in sweep; not yet drilled.

### 9. ITR refund holds — Taxes · CBDT
- Surfaced in X sweep: "26AS/AIS fully matching, yet processing/refund pending; multiple CPGRAMS complaints closed without resolution."
- Not yet drilled. Crowding check needed (CA ecosystem, ClearTax etc. serve the filing side; the stuck-refund side unknown).

### 10. Pothole/bad-road injury compensation claim kit — Public infrastructure · civic bodies
An unknown, time-bound legal entitlement: Bombay HC (Oct 2025) mandates ₹6 lakh for pothole/open-manhole deaths, ₹50k-2.5L for injuries, payable within 6-8 WEEKS with interest on delay, recoverable from negligent officers/contractors; right to safe roads = Article 21. BBMP has its own claim process. Tool: in-the-moment evidence checklist (photos, medical records, spot details) + claim drafting + the deadline clock + escalation (MACT S.166 / civil suit routes).
- Pain: pedestrians = ~28% of Bengaluru road deaths, 200+ walkers killed/yr; pothole deaths are a national genre.
- Failure type: pure information failure ON TOP of the enforcement failure — the entitlement exists and almost nobody claims it. Same DNA as the train-seat Palakkad playbook but with a standing HC-ordered scheme and fixed amounts.
- Correctness: verifiable (HC orders, BBMP scheme). ⚠️ Uniformity: state/city-scoped (Maharashtra order freshest; Karnataka/BBMP has a process) — scope to one state.
- Success: measurable (claims filed → paid). Crowding: legal blogs only; no tool.
- Status: added 2026-08-28 from everyday-services drill. Strong candidate; the "evidence + entitlement + clock" pattern generalizes (train seats, tree falls, open drains, electrocution by hanging wires).

### 11. Footpath obstruction correct-channel router — Public infrastructure · corporation/traffic police
The routing insight: broken slabs = corporation; VEHICLES parked/driving on footpaths = TRAFFIC POLICE, and that channel works at industrial scale (Bengaluru traffic police booked ~83,000 footpath-parking + 14,700 footpath-driving cases in one year); vendor encroachment = a third route. Citizens file everything with the municipality and hit the false-closure wall.
- Pain: daily, universal, deadly (see #10 stats); "Footpathakon" citizen campaigns exist.
- Failure type: ⚠️ mostly enforcement (cleared encroachments return); only the routing slice is an information failure, and it's thin.
- Crowding: generic reporting occupied by official Swachhata/city 311 apps.
- Status: explored 2026-08-28; weak-medium. Routing knowledge could fold into other tools rather than standalone.

### 12. Health insurance claim rejection → ombudsman kit — Healthcare-adjacent · IRDAI machinery
Repudiation-letter decoder + escalation kit: insurer GRO (30-day clock) → Bima Bharosa → Insurance Ombudsman (free, award BINDING on insurer, file within 1 year).
- Pain: ₹26,000 crore disallowed/repudiated FY24 (+19% YoY), ~11% of health claims rejected; 52,575 ombudsman complaints FY23-24; health-insurer complaints +21.7% YoY. Our own sweep: the ₹1.6L cardiac claim settled in 4 weeks via IRDAI+CPGRAMS was a top success-guide thread.
- Failure type: rejection-loop + unknown-entitlement information failure. Correctness: verifiable (Ombudsman Rules 2017, IRDAI regs). Uniformity: fully central. Success: binary, monetary. One blog claims ~70% of entertained ombudsman cases favor the policyholder — verify before citing.
- ⚠️ Crowding: Insurance Samadhan (est. 2018, Shark Tank alum): ₹999 registration + 12-15% success fee, 18,000+ complaints resolved, ₹160+ crore recovered — validates demand AND leaves the free self-serve lane open (their fee on a ₹5L claim is ₹60-75k).
- ⚠️ Framing: regulated-private sector, not a government service — fits the case study only if framed as "public grievance machinery" (ombudsman/IRDAI are statutory).
- Status: added 2026-08-28 (healthcare drill). Best pure lens-fit in healthcare.

### 13. ESIC unknown entitlements + stuck claims — Healthcare · ESIC
The unknown entitlement: medicines out of stock at the ESI dispensary bought from the market ARE reimbursable per ESIC's own policy — near-zero awareness. Plus: 21-day grievance-resolution norm, RTI as the documented unsticker for denied referrals/reimbursements.
- Pain: 13+ crore beneficiaries; standing complaints of no medicines, slow referrals, stalled reimbursements, delayed cash benefits.
- Failure type: unknown-entitlement information failure + silent stalls. Correctness: verifiable (ESIC circulars/reimbursement policy). Uniformity: central rules, fragmented facility quality.
- Strategic note: same B2B2C buyer as candidate #1 (staffing firms/HR platforms handle both EPF AND ESI for the same workers) — natural portfolio pairing.
- Status: added 2026-08-28. Squarely "government"; strong.

### 14. UDID / disability certificate delays & appeals — Healthcare/Welfare · DEPwD + state medical boards
Statutory clocks nobody invokes: certificate must be issued within 3 months, rejection reasons must be conveyed within 1 month; appeal routes = reassessment by a different medical board or State Commissioner under S.82 RPwD Act.
- Pain: 253-day average waits in MP; 12,000+ applications pending >6 months in one state alone; arbitrary sub-40% assessments (Karnataka had to direct boards to stop denying cards below 40%).
- Failure type: stall + rejection loop + unknown appeal rights — our exact pattern. Users sympathetic; digital reach via caregivers/NGOs (nayi-disha etc. already produce guides — partner channel).
- ⚠️ Execution fragmented across state boards; central law uniform.
- Status: added 2026-08-28. Strong pattern-fit, softer reach.

### 15. PM-JAY denial at the hospital desk — Healthcare · NHA/State Health Agencies
In-the-moment rights card: denial of treatment or demanding money from an Ayushman beneficiary is a scheme violation; channels = 14555 helpline + CGRMS portal; enforcement is real (1,114 hospitals de-empanelled, 549 suspended).
- Pain: mass denial episodes documented (Punjab: private hospitals refused admissions for a month over unpaid claims).
- ⚠️ Failure type: split — the desk-level denial is an information failure, but the root cause is often systemic (insurer-hospital payment disputes) which no citizen tool fixes.
- ⚠️ Reach: beneficiaries are the poorest/least digital — the Haqdarshak offline-intermediary warning applies at full strength.
- Status: added 2026-08-28. Highest social value, hardest delivery.

### 16. GST registration SCN decoder — Licences/Taxes · CBIC/GSTN
The rejection loop with a 7-day clock: officer issues Show Cause Notice (REG-03) listing deficiencies → applicant must reply in REG-04 within 7 WORKING DAYS or it converts to rejection → re-apply or appeal. The invocable right: CBIC Instruction No. 03/2025-GST (Apr 2025) — issued BECAUSE of mass grievances — prohibits officers from demanding documents beyond the FORM GST REG-01 list (lessor's PAN/Aadhaar, photos etc. explicitly named as illegitimate), bans notices on "presumptive grounds or minor discrepancies," requires Deputy/Assistant Commissioner approval for any extra demand, and mandates strict action against deviating officers.
- Tool shape: SCN-reason decoder + REG-04 response drafter + "this demand violates Instruction 03/2025" citation generator + the 7-day clock.
- Pain: mass (every freelancer/small seller; the instruction's own existence is the official admission). Failure type: rejection loop + illegitimate-demand information failure. Correctness: fully verifiable (Rule 9, REG forms, the Instruction PDF). Uniformity: central portal, though state-officer behavior varies. Success: binary (GSTIN granted).
- Crowding: paid CA ecosystem + content sites; no free interactive decoder.
- Status: added 2026-08-28 (licences drill). Strong; same DNA as EPF decoder (#1).

### 17. FSSAI tier + renewal-clock tool — Licences · FSSAI/FoSCoS
Two traps: (a) tier confusion — basic registration vs state vs central licence by turnover; wrong tier = rejection/penalty; (b) the renewal cliff — renew 30 days pre-expiry; late fee ₹100/day; renewal possible up to 3 months post-expiry (little-known newer policy); after 180 days NO renewal, fresh application only; operating unlicensed = ₹2-5 lakh fine + up to 6 months imprisonment (S.63 FSS Act).
- Tool shape: 3-question tier picker + exact document list + renewal deadline reminders + lapse-rescue path (the 3-month window).
- Audience: home bakers, cloud kitchens, tiny food businesses — highly reachable (Instagram/Reddit food-entrepreneur communities); agents charge thousands for a ₹100/yr registration.
- Correctness: verifiable (FSS Act, FSSAI orders). Uniformity: central law + national FoSCoS portal. Success: measurable (registered right-tier, renewals on time).
- Crowding: consultant content farms (IndiaFilings etc.) monetizing confusion; no free tool.
- Status: added 2026-08-28. Solid; smaller stakes than #16 but cleanest build.

### 18. Municipal trade licence renewals — Licences · city corporations
- Pain real but the documented failure is inspector discretion + bribery (BBMP health-inspector sting; Lokayukta arrests; complaints against officials see no action) = corruption/enforcement failure our design principle rules out as a target; city-fragmented rules.
- Status: explored 2026-08-28; weak fit. Only slice: per-city renewal deadline/penalty info — thin and fragmented.

## Unexplored sectors from the 13 (discovery targets)
- **Housing**: RERA complaint follow-through, society registration, occupancy certificates.
- **Safety**: FIR refusal (surfaced in sweep — police refuse to register; e-FIR routes exist in some states), women's helpline follow-through.
- Drilled so far: Employment (#1, #8), Transport (#2), Identity (#3), Documentation (#4), cross-sector grievance (#5), Municipal (#6), Education/Welfare (#7), Taxes (#9, #16), Public infrastructure (#10, #11), Healthcare (#12-15), Licences (#16-18).

## Method note
Candidates 1-9 all trace to primary evidence: the X/Reddit extraction (`social-listening-govt-complaints.md`), the Last-Mile Ledger artifact, consumer-court records, and official stats. New candidates should enter with the same lens filled in, not vibes.
