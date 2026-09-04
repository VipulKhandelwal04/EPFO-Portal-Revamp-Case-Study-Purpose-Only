# Discovery Board — Detailed (5W1H, pitfalls, build reasoning)

Date: 2026-08-29. Status: discovery phase. No candidate is final.
Language note: this document uses simple language rules (short sentences, active voice, one idea per sentence).

## Words used in this document (glossary)

- **EPFO**: the government body that holds workers' provident fund (PF) money.
- **PF claim**: a request to withdraw your own PF money.
- **CPGRAMS**: the central government's online complaint portal.
- **RTI**: Right to Information. A citizen can ask any public office for information. The office must reply in 30 days.
- **SCN**: Show Cause Notice. A notice from an officer that lists problems with your application.
- **GST**: the tax registration every business needs.
- **FSSAI**: the licence body for food businesses.
- **UDID**: the government identity card for persons with disabilities.
- **ESIC**: the health insurance body for factory and company workers.
- **PM-JAY**: Ayushman Bharat. Free hospital treatment for poor families.
- **Ombudsman**: a free government referee for insurance disputes. Its decision binds the insurer.
- **TTE**: the ticket examiner on a train.
- **RailMadad**: the railway complaint portal.
- **False closure**: an office marks a complaint "resolved" but did not fix the problem.
- **Escalation**: moving a complaint to a higher authority when the first office fails.
- **Decoder**: a tool that reads a rejection note and explains it in plain words.

## The repeated pattern

Most strong candidates share one shape. A rule, a deadline, or a payment right exists on paper. The government itself published it. Citizens do not know it. A small tool can put that knowledge in the citizen's hand at the right moment.

---

## TIER A — strongest candidates

### 1. EPF Rejection Decoder — Employment

- **What (problem):** EPFO rejects about 1 in 5 PF claims. The rejection note is short and unclear. People do not know what to fix. Each retry costs weeks.
- **What (tool):** A one-page decoder. It reads the rejection note. It gives the full fix list and complaint drafts.
- **Who:** Workers who withdraw their own PF money. Many file after a job loss or an emergency. About 25 lakh claims were rejected in one year (2022-23).
- **When:** Days or weeks after the worker files the claim online.
- **Where:** EPFO. It is a central body. The rules are the same in every state.
- **Why (cause):** Records do not match (name, date of exit, bank details). The employer often caused the mismatch. EPFO flags one defect at a time. So each rejection creates one more retry.
- **How (tool steps):**
  1. The user selects or pastes the rejection note.
  2. The tool explains the note in plain words (English and Hindi).
  3. The tool lists every fix, in order. Each fix names the actor: user, employer, or EPFO.
  4. If the fault is not the user's, the tool writes a complaint draft with the correct deadlines.
- **Why build it:** The pain is large and constant. Success is easy to measure: the next claim gets paid. The rules are central and stable. We can check every fix against EPFO's own documents. Only static articles compete. No interactive tool exists.
- **Why not build it:** EPFO changes its systems often (new portal versions). The knowledge base needs regular checks. If EPFO improves its own rejection notes, the tool loses value.
- **Pitfalls and limits:** A wrong fix instruction harms a desperate user. So every entry needs a source check. The tool cannot force the employer to act. It can only draft the complaint.

### 16. GST Registration SCN Decoder — Licences / Taxes

- **What (problem):** Officers reject GST registrations with unclear notices. The applicant has only 7 working days to reply. Officers often demand documents the law does not require.
- **What (tool):** A decoder for the notice. It drafts the reply. It cites the rule that blocks illegal document demands.
- **Who:** Freelancers, small sellers, and new businesses. Every business needs GST registration to operate formally.
- **When:** After application, when the SCN arrives. The 7-day clock starts then.
- **Where:** The central GST portal. Officers sit in state and central offices. Behavior varies by officer.
- **Why (cause):** Officers raise queries on weak grounds. The government admitted this. It issued Instruction 03/2025 in April 2025. The instruction bans demands beyond the official document list. Almost no applicant knows this instruction.
- **How (tool steps):**
  1. The user pastes the SCN text.
  2. The tool explains each objection in plain words.
  3. The tool drafts the reply within the correct format.
  4. If the officer demanded an illegal document, the tool cites Instruction 03/2025 in the draft.
  5. The tool shows the 7-day deadline as a clear clock.
- **Why build it:** The citable rule is dated, official, and public. The clock is brutal, so the tool's speed has real value. The audience is large and online. Paid accountants serve this need today. A free tool has a clear lane.
- **Why not build it:** Tax rules change often. A wrong draft can hurt a real business application. Accountants already serve people who can pay. The hardest cases need human judgment.
- **Pitfalls and limits:** The tool must never promise approval. Officer behavior varies. The instruction helps, but a hostile officer can still delay. The tool must say this honestly.

### 12. Insurance Claim Rejection → Ombudsman Kit — Healthcare (adjacent)

- **What (problem):** Insurers rejected or reduced health claims worth about ₹26,000 crore in one year. Most people stop after the rejection letter. A free referee exists. Few use it.
- **What (tool):** A rejection-letter decoder plus an escalation kit with deadlines.
- **Who:** Middle-class families with health insurance. Their claim was rejected or cut.
- **When:** After the insurer sends a rejection or a short settlement.
- **Where:** First the insurer's complaint cell (30-day clock). Then the Bima Bharosa portal. Then the Insurance Ombudsman (file within 1 year). All central and uniform.
- **Why (cause):** Insurers cite policy clauses most people cannot read. People do not know the ombudsman is free. They do not know its decision binds the insurer.
- **How (tool steps):**
  1. The user pastes the rejection letter.
  2. The tool explains the cited clause in plain words.
  3. The tool checks the escalation deadlines against the user's dates.
  4. The tool drafts the complaint for each stage.
- **Why build it:** The money at stake is large. The forum is free and binding. Success is measurable. Rules are central. Our own research found top-voted success stories that used this exact path.
- **Why not build it:** This is not a government service. Insurers are private companies. The case study is about government processes. A paid competitor exists (Insurance Samadhan: ₹999 plus 12-15% success fee). Complex cases need human help.
- **Pitfalls and limits:** The tool must not give legal advice. It only explains and drafts. The framing problem is real: use it only if the case study accepts "public grievance machinery" as government.

### 13. ESIC Unknown Entitlements — Healthcare

- **What (problem):** ESIC covers over 13 crore people. Dispensaries often lack medicines. Workers then buy medicines with their own money. ESIC's own policy says this money is refundable. Almost nobody knows.
- **What (tool):** A rights card plus a refund claim helper for ESIC members.
- **Who:** Factory and company workers with ESI cards. Mostly lower-income, semi-digital users.
- **When:** At the dispensary, when the medicine is out of stock. Or when a referral or refund is stuck.
- **Where:** ESIC dispensaries and hospitals. Central rules, uneven local quality.
- **Why (cause):** ESIC publishes its refund policy, its 21-day complaint norm, and its RTI route. This knowledge never reaches the worker at the counter.
- **How (tool steps):**
  1. The user picks the situation (no medicine, referral denied, refund stuck).
  2. The tool shows the exact entitlement with the official source.
  3. The tool lists the claim steps and required papers.
  4. If the claim stalls, the tool drafts the complaint or the RTI.
- **Why build it:** Squarely a government service. Huge covered population. Clear unknown entitlement. It shares a future business channel with candidate #1: the same staffing firms and HR platforms serve both PF and ESI.
- **Why not build it:** The audience is hard to reach online. Refund processes vary in practice across regions. Evidence of claim success rates is thin. It needs field validation.
- **Pitfalls and limits:** A refund right on paper may still fail in a bad office. The tool must set honest expectations. Hindi-first design is necessary, not optional.

### 10. Pothole Injury Compensation Kit — Public infrastructure

- **What (problem):** Courts ordered fixed compensation for pothole deaths and injuries. Bombay High Court (Oct 2025): ₹6 lakh for a death, ₹50,000 to ₹2.5 lakh for injuries, payment within 6-8 weeks. Almost no victim claims it.
- **What (tool):** An evidence checklist for the moment of the accident, plus a claim drafting kit with the deadline clock.
- **Who:** Accident victims and their families. Pedestrians are about 28% of road deaths in Bengaluru alone.
- **When:** Right after an accident caused by a pothole, open manhole, or broken road.
- **Where:** The city corporation or road authority. Court orders differ by state. Start with one state (Maharashtra has the freshest order).
- **Why (cause):** The entitlement lives in court orders and legal blogs. Victims in shock do not know to photograph the pothole or keep records.
- **How (tool steps):**
  1. The tool gives an immediate evidence checklist (photos, medical papers, witnesses, spot details).
  2. The tool drafts the written claim to the correct authority.
  3. The tool tracks the 6-8 week payment clock.
  4. If unpaid, the tool shows the escalation route (tribunal or court).
- **Why build it:** Fixed amounts, a court-ordered clock, and a defined route. High moral weight. Nobody serves it as a tool.
- **Why not build it:** Claims still need lawyers in many cases. The scheme is state-specific, so scale is limited. Users arrive in grief; the product needs great care. Volume per city may be low.
- **Pitfalls and limits:** The tool must not act as a lawyer. It prepares the person for the claim or for a legal aid visit. Recovery may still take months despite the order.

---

## TIER B — good, each with one big weakness

### 17. FSSAI Tier + Renewal Clock — Licences

- **What:** Food businesses pick the wrong licence tier and get rejected. Or they miss renewal. Late fee: ₹100 per day. After 180 days the licence dies. Running without one risks ₹2-5 lakh fines. Tool: a 3-question tier picker, document list, renewal reminders, and the little-known 3-month rescue window.
- **Who / When / Where:** Home bakers, cloud kitchens, small food shops. At start-up and at renewal. FSSAI is central; one national portal.
- **Why build:** Cleanest small build on the board. Reachable audience (food seller communities). Agents charge thousands for a ₹100 registration.
- **Why not:** Stakes per user are smaller than Tier A. Consultant content sites already answer most questions, just with worse incentives.
- **Pitfalls:** Renewal reminders create an ongoing duty. A missed reminder could harm a user. State food offices add local quirks.

### 14. UDID / Disability Certificate Clock — Healthcare / Welfare

- **What:** Disability certificates take months (253-day average waits in one state). The law requires issue within 3 months and written rejection reasons within 1 month. Appeal routes exist. Nobody invokes them. Tool: status decoder, clock tracker, appeal drafter.
- **Who / When / Where:** Persons with disabilities and their caregivers. After application. State medical boards under a central law.
- **Why build:** Exact pattern fit (clock + unknown right + escalation). Sympathetic, underserved users. NGO partners exist for distribution.
- **Why not:** Execution sits with state boards, which vary widely. Reach depends on caregivers and NGOs, not search. Success may be slow to measure.
- **Pitfalls:** Users are vulnerable. Wrong guidance costs them scheme access. Every state-board difference needs verification.

### 2. Train Seat Evidence Playbook — Transport

- **What:** People with confirmed seats find them occupied. Staff often do not act. A consumer court paid ₹75,000 total to a family because they filed a complaint during the journey, with a timestamp. Tool: an in-journey evidence guide plus a compensation claim drafter.
- **Who / When / Where:** Reserved-ticket passengers. During the journey. Railways (central), consumer courts (district).
- **Why build:** Clear precedent. Clear evidence recipe. Massive relatable pain.
- **Why not:** The tool cannot get the seat back in the moment. That is an enforcement gap. Compensation arrives months later through a consumer case. Most people will not file one.
- **Pitfalls:** Overpromising is easy. The honest pitch is small: "create the record now, decide later."

### 5. CPGRAMS False-Closure Appeal Kit — cross-sector

- **What:** Offices close complaints without fixing problems. Rating the reply "Poor" unlocks a formal appeal with a 30-day clock. Few know this. Tool: appeal drafter plus deadline clocks.
- **Why build:** False closure is the #1 pattern in all our data. The unlock trick is real and obscure.
- **Why not:** It is a meta-tool, not a sector tool. The user asked for narrow. Also, appeals may get the same false closures. This needs testing (about 20 real cases).
- **Pitfalls:** If appeals fail at the same rate, the tool only documents failure. Its DNA already lives inside Tier A candidates.

### 8. Pension Stalls — Welfare

- **What:** Pensions sit stuck for months or years. Offices invent requirements. Families of the dead wait for family pension. Tool would decode stalls and draft escalations.
- **Why build:** Deep pain, elderly users hurt most. Adjacent to EPFO machinery (EPS pension).
- **Why not:** Cases are messy and one-off. Less pattern, more chaos. Better served as a later extension of candidate #1 than as a standalone tool.
- **Pitfalls:** Elderly users need a proxy user (their adult children). Case variety defeats a simple decoder.

### 9. ITR Refund Holds — Taxes (not fully drilled)

- **What:** Tax refunds stay pending even when records match. Complaints get closed without resolution. Tool would triage the hold and draft escalations.
- **Why build:** Large online audience. Central body. Clear money metric.
- **Why not:** Not yet drilled. The accountant ecosystem may already serve it. Hold reasons may be opaque, like Aadhaar.
- **Pitfalls:** Needs its own evidence pass before any decision.

---

## TIER C — weak fits (documented so we do not re-litigate them)

### 3. Aadhaar Update Rejection Loop — Identity
- **Why it tempts:** Massive pain. Rejections with no reasons. Fees lost per retry.
- **Why not:** UIDAI behavior is inconsistent. We cannot verify fix advice against stable rules. Wrong advice at scale is a real harm. Parked until rejection causes prove decodable.

### 4. Passport Verification Stall Triage — Documentation
- **Why it tempts:** Huge visible pain. Clear stall moments.
- **Why not:** "Normal wait" data does not exist on day one. The tool would guess. Crowdsourcing needs users we do not have yet. Cold-start problem.

### 6. Municipal Complaint False Closure — Municipal
- **Why it tempts:** Fake-photo closures are the #1 civic complaint.
- **Why not:** Every city has different systems. Jurisdiction mapping is the unsolved hard part. The official Swachhata app already owns intake, with mandated response times (12 hours to 1 week). Only the deadline-clock slice is usable, and it is thin.

### 7. Scholarship (NSP) Black Hole — Education / Welfare
- **Why it tempts:** Cruel harm (blocked exams over unpaid fees).
- **Why not:** The portal's internals are opaque. The failure is seasonal. Students are scattered and hard to reach. We cannot verify fix paths.

### 11. Footpath Obstruction Router — Public infrastructure
- **Why it tempts:** Daily, universal, deadly (200+ pedestrian deaths per year in one city).
- **Why not:** Broken footpaths and returning vendors are enforcement failures. A tool cannot keep a footpath clear. The one useful fact (vehicles on footpaths belong to traffic police, not the city) can live inside another tool.

### 15. PM-JAY Denial at the Hospital Desk — Healthcare
- **Why it tempts:** Highest moral stakes on the board. Denial is an official violation with a hotline (14555).
- **Why not:** The root cause is often a payment war between insurers and hospitals. No citizen tool fixes that. The audience is the least digital in India. Paper cards and helpline posters may serve better than an app.

### 18. Municipal Trade Licence Renewals — Licences
- **Why not:** The documented failure is inspector bribery and discretion. Our design principle rules out anti-bribery targets. Rules differ city by city. Parked.

---

## How to read this board (decision lens)

Build-worthiness = pain evidence × fix-path verifiability × reach × measurable success.

1. Tier A candidates pass all four tests. Each also matches the repeated pattern: official rule + clock + escalation, unknown to citizens.
2. Tier B candidates fail one test each (stakes, reach, timing, breadth, or evidence).
3. Tier C candidates fail on causes we cannot fix: unstable rules, enforcement gaps, fragmentation, or unreachable users.

One honest cross-cutting limitation applies to every candidate. These tools inform and draft. They do not compel. A determined bad office can still stall. The tools make stalling visible, documented, and appealable. That is the whole promise, and it is enough only when the escalation forum actually works.
