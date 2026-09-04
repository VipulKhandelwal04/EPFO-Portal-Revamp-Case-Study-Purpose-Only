# Social listening: what Indians complain about in government processes

**Method:** X searched live through the browser (including the reply firehose to official handles like @UIDAI, @passportsevamea, @MCD_Delhi, plus keyword searches on CPGRAMS, sub-registrar, Parivahan, PM Kisan). Reddit swept by a 4-agent workflow (transport/passport, identity/welfare, municipal/police/property, grievance/RTI/general) via the Arctic Shift archive API, since Reddit blocks direct crawlers; coverage through Aug 2026 across r/india, r/AskIndia, r/LegalAdviceIndia, r/bangalore, r/mumbai, r/Chennai and more. Roughly 40+ distinct threads plus live X replies. Date: 2026-08-28.

---

## The ranked complaint patterns (cross-platform)

### 1. False closure: complaints marked "resolved" without anything being done
The single most repeated pattern on both platforms.
- X: "I have reopened Complaint No 260822163977556794 because it was marked resolved without any sweeping... take actual action instead of closing complaints without work" (to @MCD_Delhi); "False resolution alert. @socialepfo has closed my grievance without solving the problem"; "Multiple grievances and CPGRAMS complaints closed without resolution" (income tax refund).
- Reddit: MCD 311 closes garbage complaints with a random blurry photo of a different spot, twice after reopening (410 upvotes); BBMP marks complaints "Not Relevant"; a RailMadad complaint about an overcrowded coach was closed by the very TTE it was about.
- Sources: reddit.com/r/india/comments/1tjpb7p, r/LegalAdviceIndia/comments/1vn4exh

### 2. The rejection loop: rejected repeatedly, no reason given, fee charged per attempt
- X (replies to @UIDAI): "address update has been rejected again and again despite having registered lease and licence agreement"; "same document was accepted previously and again rejected for 2nd time? My ₹2x75 is already gone"; "many applications get rejected after a fee is charged... can UIDAI clarify the refund policy?"
- Reddit: 6+ threads in 2025-26 alone on Aadhaar update rejections with vague/no reasons; the office variant is the "one error per visit" loop, each visit surfaces exactly one new defect, guaranteeing another visit (surviving-member certificate: 3 visits over 4 months, the rejection order itself took 2 months).
- Sources: r/india/comments/1tc7t7u, r/LegalAdviceIndia/comments/1vuhaxb

### 3. Silent stalls: application submitted, then nothing, no status, no timeline
- X (replies to @passportsevamea): tatkal passport pending police verification a month after documents submitted; "verification done 3 days back... website still showing pending"; "police verification completed 19 August, status still 'Under review'"; people post file numbers publicly begging for status.
- Reddit: RC ownership transfers stuck a year; teacher's pension stuck 11 months "for vague reason"; BBMP e-khata blocking a property sale 4+ months; UP electricity: filed on 3 portals with 26 signatures and photos, got an estimate but no timeline.
- Sources: r/bangalore/comments/1ikojje, r/india/comments/1u7csu8

### 4. The agent/bribe economy is the default path, and it is priced like a market
- X: dealer openly billed ₹1,900 extra "paying this fees to RTO agent as a BRIBE for registration"; "I am asked a bribe of 30000/- by a sub registrar"; "All over india... registrar and sub registrar offices are bribe centres or your files will be moved under the table."
- Reddit: sub-registrar bribes ₹15k-35k routed through builders/lawyers so they're untraceable (2,561 upvotes); passport police verification ₹300-3,000 framed as "fees/petrol charges", refusers get silently parked (5,215-upvote thread); patwari wants ₹1L for a witness statement; DL via agent = one call + WhatsApp vs 7 visits legally. "How I did it without an agent" guides are their own genre, doing it agent-free is treated as an achievement.
- Sources: r/bangalore/comments/1qb2b7r, r/indianbikes/comments/1nqwzh4, r/AskIndia/comments/1tz3pkz

### 5. Catch-22 deadlocks and impossible document demands
- Reddit's highest-engagement complaints are deadlocks, not delays: unlocking a locked Aadhaar needs an OTP to a SIM that is blocked, and reissuing the SIM needs Aadhaar biometric auth (779 upvotes); EPFO demanded an "Aadhaar Biometric Verification Report" that does not exist as a document, holding a 75-year-old's pension hostage; passport officers demanding parents' birth certificates from an era when birth registration wasn't mandatory; Aadhaar DOB-change limit (once, ever) already exhausted with documents still mismatched.
- Sources: r/LegalAdviceIndia/comments/1vitpdl, r/mumbai/comments/1vyxmhg

### 6. Portal breakage mid-transaction
- X: Parivahan down for 24+ hours; DL "Smart Locker" not working since download; state portals only serving some vehicle categories.
- Reddit: paid ₹450 on Parivahan then "HTTP 404" on the final upload step, weeks later still "pending at RTO"; the online learner-licence test never generates its password, or its blink-detection rejects applicants for hours (a driving school "got it in one go", 286 upvotes); DigiLocker showing old Aadhaar 8+ days after an approved update; NSP scholarship portal showing "no schemes found" to eligible students.
- Sources: r/bangalore/comments/1unvcev, r/andhra_pradesh/comments/1sbgvrp

### 7. Jurisdiction ping-pong
One physical problem, 3-4 agencies each saying it's the other's job: solid waste blames sewage blames stormwater blames public health; MCD closes complaints saying the land is DDA's; helplines relay callers through chains of numbers with no owner. (410-upvote thread documenting 4 departments blaming each other over one sewage swamp.)

### 8. Welfare payment failures at the last mile
- X/media: an entire news genre exists around "PM Kisan instalment not received? How to file a complaint" (8.6K views on one such post); Dainik Jagran headline: "e-KYC and farmer ID all updated, why no money and where to complain."
- Reddit: scholarship disbursement black holes (verification errors surfacing after a 10-month wait; a final-semester exam form blocked because the delayed OBC scholarship left fees unpaid); ration dealer charging ₹10/month extra "for biometric" while delivering 1 kg short; system showing next month's ration as already distributed.
- Sources: r/Indian_Academia threads, r/india/comments/58-upvote ration thread

### 9. Complaining is feared: identity disclosure and retaliation
CPGRAMS reveals the complainant's name, number and address to the accused: an LPG agency called three times and visited the complainant's home to make him withdraw; a villager who reported a road contractor got a direct call from him; top advice on patwari bribes was to negotiate the amount down because complaining makes the replacement officer stall your file for years. This is the empirical backbone of the survey's Section 4.

### 10. What actually works: escalation by public shaming
The community's shared, codified ladder: portal → CPGRAMS → RTI → Twitter-shaming → Lokayukta/Ombudsman/court. The 5,215-upvote r/bangalore thread advises skipping the police-verification bribe and tweeting at senior officials instead (approval came 5 hours after tweeting, after 8 days of silence). CPGRAMS has a double life: it reliably works against central PSUs with accountable chains (India Post, oil companies, insurers via IRDAI) and reliably bounces off anything requiring state-level action. RTI is repeatedly the thing that finally forces UIDAI to act, even as RTI's own deadlines are ignored at all three tiers (5 months, zero responses).

## Positive outliers (what "solved" feels like to citizens)
- Passport Seva's online + PSK leg: "My passport application was actually... pleasant? 6 days from PSK to passport", "without any Chai Paani." The chokepoint that survives is the offline human step (police verification, postman).
- DigiLocker: treated as legitimate and useful, complaints are sync-gap, not concept.
- The precise boundary: digitized, appointment-based, centrally-owned steps get praised; the residual offline human step is where the bribe economy survives.

## Implications for the case study

**Standing design principle (decided 2026-08-28):** the product does not target bribery or corruption directly. Bribery in this data is a symptom and a price signal, not the problem to solve. Every bribe pattern sits on a design failure that creates the leverage (discretionary handover, invisible queues, unverifiable stalls). The evidence: Passport Seva's redesigned PSK step is bribe-free not because corruption was fought but because the step became appointment-based, legible, and trackable. The product designs the official path to work; bribery decline is a byproduct. Agents sell certainty, so a product that delivers certainty legally competes with the agent economy without ever mentioning bribes.

Each complaint pattern, translated into the system-design problem the product should attack:
1. **Rejection loop ("one error per visit")** → completeness-first design: the full requirement/defect checklist validated before the visit, so extra visits cannot be manufactured.
2. **Silent stalls** → status legibility: what happens next and what a normal wait looks like (crowdsourced timelines, the Lawfully pattern), so people can tell waiting from stuck.
3. **Jurisdiction ping-pong** → ownership routing: location + problem type → the one accountable office (the FixMyStreet pattern).
4. **False closure** → evidence-backed, publicly visible complaint records so "resolved" can be verified.
5. **Catch-22 deadlocks** → escalation routing: systematize the side doors the community already found (RTI, CPGRAMS routing paths, head-of-family route).
6. **Retaliation fear** → hard constraint: aggregate and anonymize; never make one citizen the visible accuser.

Supporting observations:
- The sharpest cross-cutting pains are the two meta-failures (false closure, rejection loop), not any single department.
- The agent-economy price benchmarks (₹500 verification, ₹15k-35k registration, ₹5k DL) are willingness-to-pay data for certainty; keep the survey's bribe questions as diagnostic instrumentation.
- This framing also keeps the product inside the artifact's guardrails (DPDP, misinformation liability, no vigilante/anti-corruption positioning).
- State-to-state variance is wild (Kerala fails DL applicants 20+ times; Bengaluru passes agent clients who never drove). Any navigator must be state-scoped: one process, one state, go deep.
