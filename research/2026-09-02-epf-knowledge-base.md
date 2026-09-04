---
type: research
project: govt-case-study
date: 2026-09-02
---

# EPF Deterministic Knowledge Base (ticket 02, v1)

The source-cited data spine for the citizen-side EPF copilot ([roadmap](../analyses/2026-09-02-epf-citizen-copilot-roadmap.md), ticket 02). It replaces the prototype's illustrative per-screen facts with verified ones. Per the (b)-honesty constraints, **the facts here carry structure, sources, and a confidence tier; the LLM only writes prose around them.** A tool consuming this must treat a statutory deadline differently from a forum claim — so every fact is tiered, and everything below the OFFICIAL line is guidance, not ground truth.

Verification method: three discovery agents swept EPFO / DARPG / DigiLocker sources (2026-09-02); I then re-fetched every load-bearing URL myself and confirmed each verbatim quote appears on the live page. Facts resting on agent-only extraction (binary PDFs, archived pages I could not re-fetch) are marked **[agent-extracted]**. Nothing here is invented — gaps are recorded in §11, not filled.

## Confidence tiers

- **STATUTORY / CIRCULAR** — a statute, scheme paragraph, or government circular/OM.
- **OFFICIAL-PORTAL** — text published on a `.gov.in` EPFO/DARPG portal.
- **PRACTITIONER-GUIDE** — reputable consultancy / business press describing (often reporting a circular I could not fetch directly).
- **COMMUNITY-REPORT** — forums, member anecdotes. Signal, not fact.
- **COULD-NOT-CONFIRM** — searched, no adequate source found. A finding, not a placeholder to guess into.

---

## 1. Claim-settlement service standard (TAT)

The prototype's "20 days" is **grounded but imprecise**. Para 72(7) sets two different clocks:

| Clock | Value | What it means | Tier |
|---|---|---|---|
| Statutory settlement ceiling | **30 days** | Outer limit to settle a complete claim | STATUTORY |
| Accountability threshold | **20 days** | Past this, the Commissioner is personally liable; 12% p.a. penal interest may be charged and deducted from their salary | STATUTORY |

- Source: [Para 72(7), EPF Scheme 1952 (indiankanoon)](https://indiankanoon.org/doc/111744363/) — *me-verified*.
- Quote: "The claims, complete in all respects submitted along with the requisite documents shall be settled and benefit amount paid to the beneficiaries within 30 days from the date of its receipt by the Commissioner."
- Quote: "In case the Commissioner fails without sufficient cause to settle a claim complete in all respects within 20 days, the Commissioner shall be liable for the delay beyond the said period and penal interest at the rate of 12% per annum may be charged on the benefit amount and the same may be deducted from the salary of the Commissioner."
- **KB rule:** present 30 days as the statutory limit and 20 days as the penal-interest / service threshold. Do not state "20 days" as the hard legal ceiling.
- Also note: Para 72(7) blocks payout for claims above ₹50,000 without a verified Aadhaar (PRACTITIONER; see §4).

### Citizen's Charter per-form TATs — RESOLVED at official tier (2026-09-02 live-portal pass)

Charter obtained from the live epfo.gov.in nav: [CitizenCharter.pdf](https://pmvbry-cdn.epfindia.gov.in/wp-content/uploads/2025/11/CitizenCharter.pdf) (issue date Nov 2022; still the hosted charter as of the Nov-2025 CDN path) — *me-downloaded and text-extracted.* Tier: OFFICIAL-PORTAL. The earlier practitioner guesses ("Form 19 ≈ 20 working days, Form 31 ≈ 15") were **wrong**:

| Service | "as per Scheme" | "as per Citizens' Charter" |
|---|---|---|
| PF final withdrawal (Form-19) | 20 days | **7 working days** |
| PF part withdrawal (Form-31) | 20 days | 7 working days |
| Illness / pandemic advance (Form-31) | 20 days | **3 working days** |
| PF transfer (Form-13) | 20 days | 7 working days |
| Withdrawal by nominees/survivors (Form-20) | 20 days | 3 working days |
| Insurance to nominees (Form-5IF) | 20 days | 3 working days |
| Monthly pension (Form-10D) | 20 days | 7 working days |
| Withdrawal benefit / Scheme Certificate (Form-10C) | 20 days | 7 working days |
| Grievance redressal | — | **7 working days** |

- Quote: "Settlement Time as per Citizens' Charter is aspirational and is over and above the time-limits statutorily mandated by the Schemes framed under the EPF & MP Act, 1952."
- So the full clock stack is: **7/3 working days (aspirational charter) → 20 days (charter "as per Scheme" = the Para 72(7) penal-interest threshold) → 30 days (statutory ceiling)**. The prototype's flat "20-day service standard" matches the charter's own "as per Scheme" column — defensible, but the KB rule above (present the stack, not one number) still applies.
- Charter also gives EPFO's network: **21 Zonal, 138 Regional, 117 District offices** (⚠️ EPFiGMS homepage says "135 field offices" — different vintages; don't present either as exact without a date).

---

## 2. Claim rejection: codes, remarks, and the "OTHERS" bucket

- **There is no published EPFO rejection reason-code list.** Reasons are exposed as free-text officer remarks in "Track Claim Status" and the passbook. Tier: OFFICIAL-PORTAL (behavior) / COULD-NOT-CONFIRM (existence of any code scheme). Source: [epfo.app](https://epfo.app/claim-rejected.html) *[agent-fetched]* — "The rejection reason is written there, usually as a short officer remark."
- **"R-07" (bank-name mismatch) is UNSUPPORTED.** No official or practitioner source defines an R-07 code or ties it to bank mismatch. The *phenomenon* (bank-KYC / name-on-bank mismatch causing rejection) is real; the **code label "R-07" is not** — do not surface it. Tier: COULD-NOT-CONFIRM.
- **"OTHERS" as an officially published category is COULD-NOT-CONFIRM.** No fetched page gave a verbatim definition or a share-of-rejections figure. Plausible as an internal catch-all; not citable as fact.
- Real remark *wording* seen in practitioner renderings (not verbatim EPFO screen text): "Member details mismatch", "Service overlap detected", "EPS not eligible", "Pending with employer", "KYC not verified".
- **KB rule for the decoder (ticket 04):** key off remark **text patterns**, not a code dictionary. There is no code dictionary to key off.

---

## 3. Father's-name mismatch (the decoder's headline cause)

- **General claim:** a name mismatch (incl. father's name) between EPF records and Aadhaar is a well-attested rejection trigger. Tier: PRACTITIONER-GUIDE (+ COMMUNITY corroboration). Source: [kustodian.life](https://kustodian.life/resources/epf-claim-rejected-name-aadhaar-dob-mismatch-fix-guide-2025) — *me-verified; the page cites **no** EPFO circular, it is practitioner experience.*
  - Quote: "Older EPF accounts often used initials (e.g., 'R. Kumar') while Aadhaar uses full names (e.g., 'Rajeev Kumar')."
  - Real father's-name-field scenario: "Spouse's name replaces father's name post-marriage (especially for women) in Aadhaar, but not in EPF."
- **The specific mechanism** — that EPFO checks the father's name *as on PAN* **independently of the member's own name**, and that a mismatch silently becomes an "OTHERS" rejection — is **COULD-NOT-CONFIRM.** No circular. One PAN-specific guide lists the PAN-checked fields as name, DOB, gender — father's name **absent**, mildly contradicting the mechanism ([poonawallafincorp](https://poonawallafincorp.com/blogs/financial-insights/pan-epf-mismatch-resolution-guide) *[agent-fetched]*).
- **Correction to `CONTEXT.md`:** its glossary stated a father's-name/PAN mismatch "silently becomes the unexplained OTHERS code" as if established. That is a practitioner-tier inference, not circular-backed, and the PAN→father's-name-field link specifically is unconfirmed. Ticket 04 must present this as a "**likely cause to check**," never an asserted mechanism. *(Glossary entry rewritten to this tier 2026-09-02.)*

---

## 4. KYC match rule (soft-match vs exact-match)

The roadmap hypothesised "soft-match at seeding vs exact-match at claim." The evidence instead points to **exact match as the gate throughout**, per the EPFO circular dated **13 Aug 2025**:

- Exact match of name + gender + DOB (UAN vs Aadhaar) → employer can auto-seed via KYC, **no separate EPFO approval**. Any mismatch → the **Joint Declaration (JD)** correction path. Tier: PRACTITIONER-GUIDE reporting a circular (primary circular not fetched). Source: [BusinessToday, 2025-08-14](https://www.businesstoday.in/personal-finance/retirement-planning/story/epfo-eases-aadhaar-uan-linking-speeds-up-updates-claim-settlements-489456-2025-08-14) — *me-verified*.
  - Quote: "According to an EPFO circular dated August 13, 2025, if a member's name, gender, and date of birth in the UAN match exactly with Aadhaar, the employer can directly seed Aadhaar through the 'KYC' functionality on the Employer Portal."
  - Quote: "'No separate approval as such is required from EPFO,' the circular clarified."
  - Quote: "The EPFO has also overhauled the Joint Declaration (JD) process for cases where member details differ between Aadhaar and UAN."
- Matching for Aadhaar/UAN is reported as **exact / character-by-character** (missing middle name, initials-vs-full-name, extra spaces all block it). Tier: PRACTITIONER (search synthesis; the underlying UIDAI demographic-match spec was not located).
- **KB rule (pre-flight, ticket 05):** treat the check as exact-match; flag any deviation (initials, middle name, spacing, spouse-vs-father name) as a bounce risk; route corrections to JD. The primary circular text (13 Aug 2025) is a **priority fetch** for v2.

---

## 5. Claim rejection rate (denominator + period pinned to every figure)

The prototype's **84% is UNSUPPORTED** — no source produced an 84% figure on any denominator. Drop it. Never compare figures across denominators.

| Figure | Denominator | Period | Tier | Source (me-verified unless noted) |
|---|---|---|---|---|
| **33.8%** (24.93 L of 73.87 L) | Final-settlement claims only | FY2022-23 | PRACTITIONER / press (EPFO data via Indian Express / Reporters' Collective) | [moneylife](https://mas360.moneylife.in/article/epfo-rejection-rates-surge-challenges-and-solutions/4540.html) |
| ~13% → 18.2% → 35.2% → 33.8% | Final-settlement | 2017-18 → 2018-19 → 2021-22 → 2022-23 | PRACTITIONER / press | moneylife |
| **21.59% combined** (13.77% reject + 7.82% return) | All claims | as of 26 Nov 2024 | OFFICIAL statement via press | [outlookmoney](https://www.outlookmoney.com/retirement/invest/life-insurance-pension-plan/epf-claim-settlement-improves-with-lower-claim-rejections-epfo) |
| 11.92% reject + 13.44% return | Final-withdrawal claims | as of 26 Nov 2024 | OFFICIAL statement via press | outlookmoney |
| ~26% | All claims | FY2023-24 | PRACTITIONER (FACTLY, unfetched — 403) | factly.in |

- Quote (moneylife): "Out of a total of 73.87 lakh claims received for final PF settlement, a staggering 33.8% (24.93 lakh) were rejected."
- Quote (outlookmoney): "As of 26 November 2024, the combined rejection and return ratio was 21.59 per cent." / "This includes 13.77 per cent inadmissible claims, and Returns (deficiency in claims) stood at 7.82 per cent."
- **Two corrections to memory:** (a) the "~21.6% late 2024" figure is a **combined reject+return** ratio, **not** a rejection rate — pure rejection ≈ 13.77%; (b) rejection did **not** rise monotonically — 2021-22 (35.2%) was higher than 2022-23 (33.8%).
- **KB rule:** the honest headline is "roughly one in three *final-settlement* claims rejected in FY22-23 (33.8%)," with the denominator always stated. A stronger primary lead exists — a **Lok Sabha written reply, 9 Mar 2026** (MoS Labour, on rejection reasons) — priority fetch for v2. The FY22-23 count has an unresolved 1.34 cr vs 1.64 cr discrepancy (§11).

---

## 6. EPFiGMS — grievance routing (ticket 07)

- **Live portal:** https://epfigms.gov.in/ — OFFICIAL. "EPFiGMS is a customised portal of EPFO with an aim to redress grievances for the services provided by EPFO."
- **Routing is office-level, auto-directed by UAN.** Tier: OFFICIAL-PORTAL — *me-verified*.
  - Quote: "Grievances can be lodged at any place and will land in concerned office to which the grievances pertain. Grievances can be sent to Head office at New Delhi or to the field offices now 135 across the country."
  - Quote: "UAN integrated with master data base of EPFO resulting in identification of EPF office for redress of grievance."
- **Who can file:** "Grievance can be lodged by PF member, EPS Pensioner, Employer and Others" (OFFICIAL, me-verified — and re-confirmed 2026-09-02 as the four filer options on the live [registration page](https://epfigms.gov.in/Grievance/GrievanceMaster) itself; the category dropdown loads only after selecting a status, so it remains unverifiable statically).
- **Addressee:** RO-level routing names the **office, not an officer** (the RPFC framing stays PRACTITIONER-tier). But the Citizen's Charter names the HQ escalation addressee at official tier — quote: "Public Grievance Officer at Head Office: Additional Central PF Commissioner (CSD), Employees' Provident Fund Organisation, Bhavishya Nidhi Bhawan, 14 Bhikaiji Cama Place, New Delhi-110066." Charter also lists the channels: epfigms.gov.in (also on UMANG), pgportal.gov.in, 24x7 toll-free **1800118005**, and per-RO WhatsApp helplines.
- **EPFiGMS-specific SLA — RESOLVED at official tier:** the Citizen's Charter commits "General time limit for settlement of any grievance shall be 7 working days" and "In case of non-redressal, the grievance is escalated to the next higher authority." So the clock stack for ticket 07 is: **7 working days (EPFO charter) → 21 days (CPGRAMS norm, §7)**. The practitioner "15–30 working days" figure is superseded.
- **Grievance categories (9), PRACTITIONER-tier** — the live dropdown sits behind UAN+OTP, so this is from convergent practitioner guides ([cleartax](https://cleartax.in/s/epfo-grievance) *[agent-fetched]*), not re-verified by me: (1) Transfer of PF accumulation, (2) Final settlement of pension, (3) Final settlement/withdrawal of EPF, (4) PF balance queries, (5) EPS Certificate, (6) Cheque returned/misplaced, (7) Payment of insurance benefit, (8) Issue of PF balance/slip, (9) Any other concerns.

---

## 7. CPGRAMS — reply clock + appeal (ticket 08)

Governing document: **DARPG Office Memorandum, "Comprehensive Guidelines for Handling Public Grievances," dated 23 August 2024** (F.No. S-15/21/2021-(PG)-DARPG). Binary PDF I could not WebFetch; the citizen-facing headline facts below are **independently me-verified on the official pgportal FAQ**, so they stand at OFFICIAL tier. Section-level quotes are **[agent-extracted]** from the PDF.

| Fact | Value | Tier | Notes |
|---|---|---|---|
| Redress time limit | **21 days** (reduced from 30, Aug 2024) | STATUTORY + OFFICIAL | FAQ + OM |
| Interim reply | Required, with reasons, if delayed | STATUTORY + OFFICIAL | via interim ATR |
| Appeal filing window (citizen) | **30 days** from disposal | OFFICIAL | FAQ |
| Appeal disposal window (authority) | ≤ 30 days | STATUTORY | OM §6 *[agent-extracted]* |
| Appeal trigger | Mandatory feedback rating on disposal; a dissatisfied rating enables the appeal | OFFICIAL | rating ≠ appeal — filing is a separate step |

- Source: [pgportal FAQ](https://pgportal.gov.in/Home/Faq) — *me-verified.*
  - Quote (Q13): "21 days. In case of delay an interim reply with reasons for delay is required to be given."
  - Quote (Q15): "An Appeal provision has been made for redressal of dis-satisfied grievances … through a mandatory feedback [rating] to be given by the Citizen on disposal of the grievance by the Nodal Grievance Officers. The appeal needs to be filed by the applicant within 30 days."
- OM §5.1 *[agent-extracted]*: "the maximum redressal time advised by DARPG, for cases in CPGRAMS is further reduced to 21 days."
- **KB rule (reply clock, ticket 07):** member-updated 21-day clock from filing; interim-reply is the member's right to invoke. **Appeal (ticket 08):** two distinct 30-day clocks — the member's *filing* window and the authority's *disposal* window; do not conflate them.

### Escalation ladder (for ticket 08)
Rate reply "Poor" (dissatisfied) → file CPGRAMS **appeal** (30-day filing clock) → **RTI** to the concerned RO for the file/decision basis → independent forums (**Lokpal / CVC**, or the relevant ombudsman). The rung logic and the "always point to a forum outside the office that failed" principle are developed in [cpgrams-accountability-models-2026-08-29](cpgrams-accountability-models-2026-08-29.md); the 21/30-day clocks and appeal trigger here are the KB-grounded part. RTI/Lokpal step timings are **not yet KB-verified** (v2).

---

## 8. PPO number format (ticket 10a — death/pension validation)

- **Structure: 12 characters, segmented 5 + 2 + 4 + 1.** Tier: PRACTITIONER (breakdown) + OFFICIAL example.
  - First 5 = PPO issuing authority / office code; digits 6–7 = year of issue; digits 8–11 = sequential number; digit 12 = check digit.
  - Source (breakdown): [PNB MetLife](https://www.pnbmetlife.com/articles/retirement/what-is-ppo-number.html) — *me-verified.* Quote: "The PPO issuing authority's code number is represented by the first five digits. … the sixth and seventh digits. … the eight, ninth, ten, and eleventh numbers. Lastly, a … check digit is indicated by the twelfth or final digit."
- **Alphanumeric caveat (important):** for EPFO EPS-95, the office-code prefix can be **letters** — the EPFO SOP example is **"GRVSP0081010"** (12 chars, "GRVSP" + 7 digits). Source: EPFO DigiLocker SOP *[agent-extracted, archived PDF]*. So the validator must accept an **alphanumeric** 12-char pattern, not "12-digit numeric." (Purely-numeric 12-digit PPOs described by some blogs are the CPAO/AG *government-pension* format, not EPFO EPS-95.)
- **⚠️ Re-verify before ticket 10a's format validation depends on this.** The 5+2+4+1 breakdown is PRACTITIONER-tier and the one EPFO example ("GRVSP0081010") parses awkwardly against it (the year segment would read "00"). A wrong pattern would false-reject valid PPOs — the exact failure this product exists to prevent. Treat as a v1 hint, not a hard validator, until confirmed against real EPS-95 PPOs.

---

## 9. DigiLocker / BYOD ingest sources (tickets 03, 06 — ROADMAP-CRITICAL)

- **Pullable EPFO issued documents in DigiLocker: UAN Card, Pension Payment Order (PPO), Scheme Certificate.** Tier: PRACTITIONER (list) + OFFICIAL (PPO, via EPFO SOP *[agent-extracted]*). Source: [upstox](https://upstox.com/news/personal-finance/latest-updates/epfo-services-now-on-digi-locker-check-pf-account-balance-passbook-anytime-anywhere/article-178333/) — *me-verified.* Quote: "Members can access their EPFO documents anytime, including their UAN Card, Pension Payment Order (PPO), and Scheme Certificate."
- **The PASSBOOK is NOT a clean DigiLocker pull-document.** The mechanism-explaining sources say DigiLocker **links out to UMANG** to show the passbook/balance. Quote (upstox, me-verified): "Through Digilocker, individuals can connect to the UMANG app … and view their PF balance and passbook."
  - **Conflict, flagged:** some how-to press loosely lists "PF account passbook" under DigiLocker's Issuer Documents → EPFO. I could **not** resolve this at official tier — the official [EPFO DigiLocker page](https://www.epfo.gov.in/site_en/DigiLocker.php) now **404s** after the domain restructure. Tier of the passbook question: COULD-NOT-CONFIRM (official).
- Where members reliably get the passbook: the **EPFO Member Passbook portal** (`passbook.epfindia.gov.in`, behind UAN+password+captcha; page heading "EPF Passbook & Claim Status" — me-verified 2026-09-02) and the **UMANG app** (download PDF / screenshot).
- **Official corroboration (Citizen's Charter, me-extracted):** the Charter itself tells pensioners to "Use UMANG mobile application to view pension passbook" and to "Avail services of Digi Locker for safe custody and easy retrieval of the pension documents" — i.e., EPFO's own framing is passbook→UMANG, DigiLocker→documents. This upgrades the §10 finding: the passbook-is-not-a-DigiLocker-pull conclusion now has official-tier support.
- **ROADMAP FINDING → tickets 03/06:** do **not** hard-depend on a "DigiLocker passbook pull" as the BYOD ingest. Primary passbook path = **member uploads a passbook file** they downloaded from the passbook portal / UMANG. DigiLocker pull is a confirmed bonus for **UAN Card / PPO / Scheme Certificate** only. Also: DigiLocker EPFO pull is Android-only today (iOS → UMANG).

---

## 10. Roadmap-level findings (change the plan, not just the KB)

1. **No rejection-code dictionary exists** (§2). Ticket 04 must decode free-text remark *patterns*; "R-07 = bank mismatch" is unsupported and must not ship as a code.
2. **Father's-name-on-PAN independent scrutiny is unconfirmed and mildly contradicted** (§3). Ticket 04 presents it as a likely cause to check, not a mechanism. `CONTEXT.md` glossary overstates it — flag for edit.
3. **DigiLocker passbook is not a reliable pull** (§9). Tickets 03/06 pivot to user-uploaded passbook (passbook portal / UMANG); DigiLocker pull kept for UAN card / PPO / scheme certificate.
4. **TAT is 30 days statutory / 20 days penal-interest** (§1), not a flat 20. Present both.
5. **Rejection rate: drop 84%; use 33.8% (final-settlement, FY22-23)**; the late-2024 21.59% is combined reject+return, not a rejection rate (§5).
6. **KYC is exact-match-gated** (§4), governed by the 13 Aug 2025 circular; mismatch → JD. The "soft-match seeding" half of the roadmap framing isn't supported.

---

## 11. Could-not-confirm / open (do not invent — for a future web pass)

- Any EPFO rejection reason-**code** list; the "R-07" label; "OTHERS" as a published category + its share.
- The father's-name-**as-on-PAN independent-scrutiny** mechanism (needs a circular).
- The **primary EPFO KYC circular (13 Aug 2025)** text — priority fetch (currently press-tier).
- **UIDAI demographic soft-vs-exact match** governing spec.
- **Lok Sabha written reply, 9 Mar 2026** (MoS Labour) on rejection reasons — priority fetch (strongest primary for §2/§5).
- The **1.34 cr vs 1.64 cr** FY22-23 rejection-count discrepancy.
- **DigiLocker passbook-pullability** at official tier (the DigiLocker page 404s on epfo.gov.in; §9's Charter corroboration is strong but indirect — the definitive check is the DigiLocker app's EPFO issuer list itself).
- EPFiGMS **9-category list** at official tier (dropdown loads only after status selection on the live registration page); EPFiGMS **RO-level named addressee** (HQ addressee now resolved via Charter, §6).
- ~~Citizen's Charter verbatim per-form TATs~~ — **RESOLVED 2026-09-02** (§1, live-portal pass).
- ~~EPFiGMS-specific SLA~~ — **RESOLVED 2026-09-02** (§6: 7 working days per Charter).

---

## 12. Portal-truth vs member-report — the prototype-honesty split (2026-09-02 live-portal pass)

Direct check of the prototype's factual claims against the **actual live portals** (Member e-Sewa login page, EPFiGMS registration page, passbook portal, epfo.gov.in + its Charter PDF — all fetched by me 2026-09-02). Two lists: what the prototype asserts that the real portal/official documents actually say, and what it asserts that exists only in member reports (X/Reddit) or practitioner guides. The product must label the second list as "reported by members," never present it as portal fact.

### A. Confirmed on the live portal / official documents (portal-truth)

| Prototype claim | Live confirmation |
|---|---|
| 20-day service standard (used in breach copy, Track Claim Status) | Charter's own "as per Scheme" column = 20 days for every form (§1). Present with the 7/3-working-day charter column and the 30-day statutory ceiling. |
| Grievance flow: EPFiGMS exists, symptom→office routing | EPFiGMS live; office-level routing by UAN; filer types PF Member / EPS Pensioner / Employer / Others on the actual registration page (§6). |
| 21-day reply clock (grievance screen) | CPGRAMS official FAQ: 21 days + interim reply (§7). Note EPFO's own charter is stricter: 7 working days (§6) — the prototype's clock could show both. |
| 30-day appeal window after closure | CPGRAMS official FAQ: appeal within 30 days, unlocked via mandatory feedback rating (§7). |
| Escalation to a higher authority on non-redressal | Charter verbatim (§6), incl. the named HQ addressee: ACC (CSD). |
| Passbook behind UAN login; claim status alongside it | Live passbook portal heading "EPF Passbook & Claim Status," UAN+password+captcha (§9). |
| Exact-match claim scrutiny bouncing mismatched KYC | Exact-match gate is real (13 Aug 2025 circular, §4) — but see B4: the *seeding-is-soft* half is not. |
| e-Nomination push | Login-page banner: e-nomination filing mandatory. |

**New portal facts the prototype predates** (fold into ticket 01/09 deep-link targets): **Direct UAN allotment and UAN activation are DISCONTINUED on the member portal — both moved to UMANG with Aadhaar Face Authentication** (login-page notices, me-verified). Deep-links for those two must point to UMANG, not the portal. Death-claim filing by nominee (claims + pension) is a live portal front-door item (relevant to ticket 10a).

### B. Exists only in member reports / practitioner guides (label as "reported," never portal fact)

| # | Prototype claim | Actual grounding |
|---|---|---|
| B1 | "code R-07 (bank name mismatch)" (×9 in prototype) | **No code system exists anywhere** — not even community sources define R-07. The bank-mismatch *phenomenon* is practitioner-attested; the code label is fiction (§2). Remove the code framing entirely. |
| B2 | "OTHERS" as a named rejection category (×9) | Community/practitioner only; no official category list (§2). |
| B3 | Father's-name-on-PAN scrutiny → OTHERS bounce (×43 mentions) | Practitioner + community reports; no circular; mildly contradicted by a PAN-fields source (§3). The strongest real scenario in sources: spouse's name replacing father's name in Aadhaar post-marriage. |
| B4 | "Seeding would still pass on a soft match, but claim scrutiny would bounce" (KYC screen) | **Unsupported** — the 13 Aug 2025 circular gates *seeding itself* on exact match; mismatch → Joint Declaration (§4). Rewrite the KYC copy. |
| B5 | "84% chance of R-07 rejection (illustrative)" (×2) | Unfindable on any denominator (§5). Replace with 33.8% final-settlement FY22-23, denominator stated. |
| B6 | Rejection remark wordings ("Member details mismatch" etc.) | Practitioner renderings of remark text, not verbatim portal strings (§2). |
| B7 | False-closure / rejection-loop behavior patterns | X/Reddit social listening ([social-listening-govt-complaints](social-listening-govt-complaints.md)) — *but* officially corroborated in aggregate by DARPG's own feedback-call data (June 2026: only 56% of disposed grievances "Resolved"; Labour & Employment #1 by closed-unresolved volume). Pattern = real; any individual remark story = member-report. |
| B8 | EPFiGMS 9-category list (grievance composer) | Convergent practitioner guides; dropdown sits behind status-selection/OTP on the live page (§6). |

**Product rule (tickets 04/07):** every B-item surfaces with a visible provenance label ("members report…", "per practitioner guides…") and never in the same voice as A-items ("EPFO's charter commits…"). This split *is* the citizen-side honesty constraint applied to content.

**Applied to the prototype (2026-09-02, user-directed):** B1 fixed — R-07 relabeled as *proposed taxonomy* (provenance line added to the decode panel; the outward-facing EPFiGMS draft and grievance prefill now quote the real free-text remark instead of the code). B4 fixed — all soft-match copy rewritten to "accepted at seeding today / caught at exact-match claim scrutiny"; pills renamed FAILS CLAIM SCRUTINY. B5 (84%) retained as illustrative per user decision. Scorecard KYC row synced + artifact republished. **B3 fixed (2026-09-03, user-directed):** all father's-name mechanism copy flipped to reported voice — decode panel ("likely cause to rule out, not an official ground"), KYC note/desc, Profile defect list ("members repeatedly report… no EPFO circular confirms the check"), cure path and comparison-table header ("reported OTHERS cause"), and both outward-facing grievance prefill fields. B2/B6-B8 unchanged. **A-item sourcing applied (2026-09-03):** the prototype's 20-day standard and 21-day norm re-tagged from "(illustrative)" to their §1/§7 citations, and the grievance screen now states the Charter's 7-working-day commitment alongside the 21-day CPGRAMS norm (copy only; the demo clock still runs on 21 days). **Group-1 batch (same day):** §4's circular now cited in the prototype's JD copy; §8's PPO format drives a soft (warn-once, never-block) check on the death-pension form; the §12-A "UAN activation/allotment moved to UMANG" finding is now a banner on both retired screens (scorecard arithmetic updated 14→16 pro). **Group-2 demo-depth batch (2026-09-03):** 10 of 11 items shipped in the prototype (Mark Exit per-employment gating, Transfer banner, Home KYC-count note, Passbook trim, login banner, JD approval end-state, TrackApp rejected branch, Forgot step-2, evidence disclosure, pre-flight registry refactor); scorecard arithmetic 16→17 pro. **Pass-2 (same day):** §1's three-tier clock (7wd/20d/30d + Para 72(7) personal-liability/12%-penal-interest) now shown on the Track Claim Status norm panel and the stalled-claim detail; §6's HQ Public Grievance Officer (ACC-CSD) and toll-free 1800118005 added to the Grievance screen's escalation ladder as information-only (user-directed framing: EPFO's own internal 7-working-day escalation, not a new member-actionable rung).

## Sources (master)

Me-verified, live-portal pass 2026-09-02: [Member e-Sewa login](https://unifiedportal-mem.epfindia.gov.in/memberinterface/) · [EPFiGMS registration page](https://epfigms.gov.in/Grievance/GrievanceMaster) · [Passbook portal](https://passbook.epfindia.gov.in/MemberPassBook/login) · [epfo.gov.in](https://www.epfo.gov.in/) · [Citizen's Charter PDF](https://pmvbry-cdn.epfindia.gov.in/wp-content/uploads/2025/11/CitizenCharter.pdf) (downloaded + text-extracted).

Me-verified (re-fetched, quote confirmed on the live page): [pgportal FAQ](https://pgportal.gov.in/Home/Faq) · [epfigms.gov.in](https://epfigms.gov.in/) · [Para 72(7) indiankanoon](https://indiankanoon.org/doc/111744363/) · [moneylife rejection rates](https://mas360.moneylife.in/article/epfo-rejection-rates-surge-challenges-and-solutions/4540.html) · [outlookmoney late-2024](https://www.outlookmoney.com/retirement/invest/life-insurance-pension-plan/epf-claim-settlement-improves-with-lower-claim-rejections-epfo) · [kustodian.life name-mismatch](https://kustodian.life/resources/epf-claim-rejected-name-aadhaar-dob-mismatch-fix-guide-2025) · [PNB MetLife PPO](https://www.pnbmetlife.com/articles/retirement/what-is-ppo-number.html) · [upstox DigiLocker](https://upstox.com/news/personal-finance/latest-updates/epfo-services-now-on-digi-locker-check-pf-account-balance-passbook-anytime-anywhere/article-178333/) · [BusinessToday KYC circular](https://www.businesstoday.in/personal-finance/retirement-planning/story/epfo-eases-aadhaar-uan-linking-speeds-up-updates-claim-settlements-489456-2025-08-14).

Agent-extracted / not re-fetched by me: DARPG OM 23 Aug 2024 (pgportal PDF) · EPFO DigiLocker SOP (archived PDF) · [cleartax EPFiGMS](https://cleartax.in/s/epfo-grievance) · [epfo.app](https://epfo.app/claim-rejected.html) · [poonawallafincorp PAN-EPF](https://poonawallafincorp.com/blogs/financial-insights/pan-epf-mismatch-resolution-guide). Unfetched (blocked): factly.in FY23-24; EPFO Annual Report PDF; EPFO Citizen's Charter PDF.

Related notes: [[epfo-portal-clone]] · [[govt-case-study-project]] · [cpgrams-accountability-models-2026-08-29](cpgrams-accountability-models-2026-08-29.md) · [CONTEXT.md](CONTEXT.md) (§3 correction pending).
