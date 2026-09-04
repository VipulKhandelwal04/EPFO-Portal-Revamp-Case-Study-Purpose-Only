# App-store review scan across the candidate board (Play Store, 2026-08-29)

**What this is.** For each of the 18 candidates on `problem-discovery-ledger.md`, I read the Google Play reviews of the official app that sits closest to the problem. This is a third evidence lens, next to `candidate-complaint-scan-2026-08-29.md` (Reddit + X) and `international-analogues-per-candidate.md` (foreign mechanisms).

**What this lens can and cannot see.** App-store reviews measure complaints about *the app*, not about *the process*. The lens only produces a real signal when two things are both true: a consumer app exists, and that app is the actual touchpoint where the pain happens. Where the pain happens on a web portal, at a counter, or offline, the app store is structurally blind. So "no app-store signal" never means "no pain"; it means the pain lives on a channel this lens cannot read. Play Store only (Android dominates both these audiences in India; iOS would add little).

**One cross-cutting finding, stated up front.** The government's own *redressal* apps are rated far lower than its *transaction* apps. RailMadad (complaints) is 2.7 stars while RailOne and UTS (booking/ticketing) are 4.6. Swachhata (civic complaints) is 2.3. ABHA and the scholarship registration app are 4.5. Dissatisfaction concentrates in the grievance-and-closure layer, which is exactly the layer every tool on this board operates in. That is a strong confirmation of the board's core thesis.

---

## Group A: strong, on-thesis signal (the lens validates the tool)

### Rank 5 · Aadhaar update decoder — STRONGEST validation of the day
App: **Aadhaar** (UIDAI, id `in.gov.uidai.pehchaan`), 4.2 stars, 1 crore+ downloads, 63.9K reviews.
The #1 most-relevant review is our thesis, verbatim:
> "I tried to change my address, but my application was rejected five times. Each time I submitted different supporting documents, yet it was still rejected without any clear explanation... after successfully making the payment, my application was rejected within 2 days without providing any valid reason. Lack of transparency in the process." (15 helpful)
Repeat rejection, no reason, fee lost each attempt, no transparency: the exact gap the decoder fills. Other reviews are app bugs (login JSON error, downloaded PDF hidden). Net: app-store lens raises confidence in Aadhaar as a lead candidate.

### Rank 1 · EPF rejection decoder (scanned earlier, 2026-08-29)
Apps: **UMANG** (4.5 stars, 10 crore+ downloads; top and newest reviews are EPF-dominated) and third-party **PF Balance/UAN/EPF** (`com.versionsystems.pfbalancecheck`, 4.6 stars, 1 crore+ downloads).
Findings: demand is huge and EPF-anchored; every EPF app only mirrors raw portal status and none decodes a rejection or drafts the next step; the government's own reply to "PF claim not settled since June" was "we are not authorized to process claims, raise a grievance at epfigms.gov.in" — the exact path the decoder automates. Caveat: current EPF review volume is inflated by a ~3-month EPFO-on-UMANG migration outage (temporary access pain, not our structural problem).

---

## Group B: the lens confirms the board's caution (real pain, but a wall or thin gap)

### Rank 8 · Train seat evidence playbook
App: **RailMadad** (CRIS, `cris.railmadad`), 2.7 stars, 10 lakh+ downloads.
On-thesis review (23 Aug 2026):
> "once you register a complaint we get a call saying they will investigate, then they immediately close the complaint. There is no provision to follow up on your closed complaint."
Also: cannot track a complaint inside the app; a fake "you received a call" record. This is the false-closure pattern applied to trains, and it supports the playbook's premise (the gap is evidence discipline and follow-through, not filing). Contrast worth noting: the railway booking apps RailOne and UTS are 4.6 stars; only the complaint app is broken. The seat-specific pain (someone in my reserved seat) is not in the top reviews; it stays enforcement-bound.

### Ranks 10, 13, 14 · Municipal false-closure / footpath / pothole (one app covers all three)
App: **Swachhata-MoHUA** (MoHUA, `com.ichangemycity.swachhbharat`), 2.3 stars, 50 lakh+ downloads, 65.8K reviews.
Massive demand, deep dissatisfaction. The dominant complaint is enforcement, not information:
> "Not useful they did nothing and update status as rejected"
> "no benefit for raising complaints, nobody attends, complaints stay unattended for months"
> "1 week, status still Open. No proper follow-up or escalation option."
Two facts push these candidates down, not up. First, the pain is enforcement-bound ("nobody acts"), which a citizen-side information tool cannot fix. Second, the official app already has "reopen if not satisfied" and shows the inspector's "Resolved" photo, so our envisioned reopen-and-evidence mechanic partly exists in the incumbent. Differentiation is thin. This reinforces the board's mid/low placement.

### Rank 15 · PM-JAY desk-denial rights card
App: **Ayushman App** (NHA, `com.beneficiaryapp`), 3.7 stars, 1 crore+ downloads.
The app is only for creating the Ayushman card, and its reviews are all card-download bugs (one has 9,053 helpful votes), a geo-block error, no back button. The desk-denial pain our tool targets happens at the hospital counter, offline, so it does not appear here; the root cause is fiscal (hospitals unpaid). Consistent with the board's low ranking: highest social value, weakest product traction.

---

## Group C: the lens is blind (no app, or the app is the wrong surface)

### Rank 9 · Passport verification stall triage (scanned earlier, 2026-08-29)
App: **mPassport Seva** (3.9 stars, 10 lakh+ downloads). Reviews are dominated by app-technical failures (login, "can't talk to servers", "Please try after sometime" on status check = 157 helpful), not process-stall pain. One on-thesis review (Chanderpal Singh, 27 Aug 2026): normal passports show each step (Police, SP, RPO) but a PCC hides mid-process status, so a stalled file is invisible. The stall pain is a Reddit/X signal, not an app-store one.

### Rank 6 · ITR refund hold triage
App: **AIS for Taxpayers** (Income Tax Dept, `io.lntinfotech.AIStaxpayer`), 3.8 stars, 10 lakh+ downloads. This app only views the Annual Information Statement; reviews are data-mismatch and login bugs plus a 40-entry cap. Refund status is checked on the e-filing web portal, not here. Refund-hold pain is a web-portal + Reddit signal (the earlier scan found high-engagement Reddit posts).

### Rank 7 · NSP scholarship pipeline decoder
App: **NSP OTR** (NIC, `in.gov.scholarships.nspotr`), 4.5 stars, 1 crore+ downloads. This app is only the one-time registration front door; reviews are login/server/initialization failures with real deadline urgency ("last date going to get over"). The pipeline-stall pain (defect codes, disbursement, wrong-owner escalation) lives on the NSP web portal and Reddit (148-comment status threads found earlier), not in this app.

### Ranks 2, 3, 4, 11, 12, 16, 17, 18 · no consumer app that fits the pain
- **Rank 2 GST SCN**: registration is web (GST portal); third-party apps (TaxBuddy, ClearTax) are filing services, not registration-SCN help. Lens N/A. Pain already strong on Reddit/X.
- **Rank 3 Insurance ombudsman**: Bima Bharosa and the ombudsman are web; insurer apps are private. Lens N/A.
- **Rank 4 CPGRAMS appeal**: pgportal is web; no popular CPGRAMS app. Lens N/A. (It is the escalation engine inside ranks 1, 2, 5.)
- **Rank 11 Pension stall**: Jeevan Pramaan (life certificate) exists, but the stall pain is EPS/treasury, web and offline. Weak/N-A.
- **Rank 12 UDID**: web portal, UMANG-hosted; no standalone popular app. Lens N/A.
- **Rank 16 ESIC**: UMANG-hosted; no popular standalone app. Lens N/A. (Board already flagged: audience not on English social either.)
- **Rank 17 FSSAI**: FoSCoS is web; a "Food Safety Connect" complaint app exists but with low usage. Weak/N-A.
- **Rank 18 Trade licences**: city-specific, no national app. Lens N/A.

---

## Net effect on the board

- **Aadhaar (#5) is strengthened.** It is now the second candidate, after EPF, with a strong on-thesis signal on *both* the social channels and the app store. The two leads are the two problems where the rejection-and-no-reason pain is loudest across every lens.
- **The municipal cluster (#10, #13, #14) stays down, with a sharper reason.** Huge demand, but the wall is enforcement, and the incumbent app already ships reopen and resolved-photo. Confirmed, not promoted.
- **Trains (#8) holds.** The false-closure evidence is real; the seat-specific pain stays enforcement-bound; the complaint app itself is the weak incumbent.
- **PM-JAY (#15) holds low.** Card app only; denial pain is offline and fiscal.
- **Everything in Group C is unchanged.** The app-store lens is simply blind to those problems; their evidence stands on Reddit, X, and the web portals.
- **Strategic confirmation of the whole board:** government redressal apps (RailMadad 2.7, Swachhata 2.3) are rated far below government transaction apps (RailOne/UTS 4.6, ABHA 4.5, NSP OTR 4.5). The redressal-and-closure layer is where citizens are most unhappy, and that is the layer this board builds in.

Method: Play Store listings read on 2026-08-29 via logged-in Chrome; "most relevant" and "newest" review sorts. Quotes are verbatim from the listings. Design principle unchanged: system design that removes the leverage, never anti-bribery.
