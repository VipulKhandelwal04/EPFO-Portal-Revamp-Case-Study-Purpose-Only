---
type: analysis
project: govt-case-study
date: 2026-09-02
---

# EPF Citizen-Side Copilot — Build Arrangement (from the Revamp Scorecard)

**Question:** The EPFO Revamp Scorecard's Con/Improvement cells are effectively a backlog. How should those tickets be arranged so a **citizen-side deployable** product fulfils the role the real EPFO portal fails at?

**Answer (lead with it):** Treat the scorecard's improvements not as a flat priority list but as a **dependency tree with one root**. The only thing separating the prototype from a real portal is that it *fakes* three things: **identity, system-of-record data, and submission**. In the citizen-side model chosen here, you cannot make those real (no open gov APIs) — so you **extract the decode / prepare / escalate slices into a bring-your-own-data (BYOD) copilot and hand every transaction back to the real portal.** The product spine survives; the "real integration" tickets collapse into BYOD substitutes (paste-a-remark, DigiLocker passbook pull, drafts the member files themselves).

## Premise / decision (user, 2026-09-02)

Two portals were on the table; the user chose **(b)**:

- **(a) EPFO-internal adoption** — how EPFO itself would ship the redesign; real integrations on the table. *Not chosen.*
- **(b) Citizen-side deployable** — the BYOD mode this whole project has lived in (see [[govt-case-study-project]] memory and the research notes): no open EPFO/Parivahan/Passport API, client-side, no accounts (privacy is a hard constraint), deterministic knowledge base + LLM-for-prose-only, DigiLocker as the legal document-pull substitute. **Chosen.**

A citizen-side product **cannot be** the 25-screen portal. It does the portal's *broken bits* (decode a rejection, prepare a complete fix, draft the escalation) and deep-links out for every transaction. If the user later wants to promote this deployment choice to a formal spec amendment, it should become a note in `../decisions/`.

## The reframe

Nearly every substantive scorecard "Improvement" is a leaf hanging off one shared root ("connect the real ECR feed," "wire to EPFiGMS," "real UAN/Aadhaar lookups"). Under (b) the root is **not** government integrations — it is:

1. a **deterministic knowledge base** (rejection codes, KYC match rules, service standards, EPFiGMS/CPGRAMS routing + addressees, statutory deadlines, escalation ladder), human-verified against EPFO sources — this is the product asset (memory: "build the remark knowledge base FIRST");
2. a **BYOD ingest layer** (paste text / pull documents from DigiLocker, all client-side);
3. a **draft-generator** (deterministic addressee/statute/deadline fill + LLM prose) the member files themselves.

## The spine — the priority path *through* the tree

A generic "foundation-first" stack is what any portal would produce. This project's thesis is the **closure / escalation layer**, so the tickets order along the one vertical that proves *this* product's role:

**KYC truth → real claim pre-flight → structured rejection + status decode → grievance draft + reply clock → verified closure + appeal.**

The dependency layers are *how* each rung is built; the spine is *why* they are built in that order.

## The backlog (citizen-side, dependency-ordered)

Materialize as `/to-tickets` **once the two open questions below are answered**. Kept here inline so nothing is lost; a future session can split into files. (Note: the `/to-tickets` default is a hidden `.scratch/` folder, which Obsidian does not show — if these become files, put them in a **visible** folder so they stay in the vault.)

| # | Ticket | Blocked by | Delivers |
|---|---|---|---|
| 01 | Scope the citizen-side boundary + portal hand-offs | — | Honest product edge: copilot does the broken bits; every transaction deep-links to the real portal instead of being rebuilt |
| 02 | Deterministic EPF knowledge base | — | One versioned, source-cited data spine (rejection codes incl. OTHERS, soft-vs-exact KYC rules, service standards, EPFiGMS/CPGRAMS routing + addressees, 21/30-day deadlines, escalation ladder) replacing every hardcoded per-screen fact |
| 03 | BYOD ingest (client-side, no accounts) | — | Member brings their own data (paste a remark, upload/pull a passbook), parsed on-device; nothing leaves the browser |
| 04 | Rejection-remark decoder | 02, 03 | Paste your real remark → field-by-field decode of the exact cause (incl. OTHERS → father-name) + ordered cure path *(memory's #1 candidate)* |
| 05 | Generalized claim pre-flight (KYC-field registry) | 02, 03 | Reusable KYC-field-check registry run against your own KYC state, flagging what bounces before you file |
| 06 | Passbook-fed contribution-gap & exit detector | 02, 03 | From your own passbook, detect gaps and blank/late exit dates as nudges — the Alert Centre fed by your data, not a live ECR feed |
| 07 | EPFiGMS grievance draft + member-driven 21-day clock | 02, 04 | Ready-to-file grievance draft (deterministic addressee/statute/context + LLM prose) you paste into the real portal, plus a reply tracker you update |
| 08 | Verified closure + CPGRAMS/RTI appeal drafts + ladder | 07 | Mark whether it was actually resolved; No/Partly generates a KB-backed appeal/RTI draft with the 30-day clock and independent-forum ladder *(the core thesis)* |
| 09 | Portal-linking guidance cards | 02, 06 | Transactional nudges (stale untransferred account, unsigned e-Nomination, self-mark-exit window, JD routing) become explain-and-deep-link cards, not rebuilt transactions |
| 10a | Death-claim prep/decoder | 02, 03 | Prep checklist + format validation (incl. PPO-number check) for the death/pension claim; filing stays the portal's |
| 10b | Higher-wages prep + status decoder | 02, 03 | Higher-wages (EPS higher-pension option) prep guide + application-status decoder; filing stays the portal's |

**Frontier:** 01, 02, 03 start immediately → then {04, 05, 06} in parallel → 07 → 08; 09 after 06; 10a and 10b after foundation.

**Validation gate (from memory, [[govt-case-study-project]]):** after 08, run ~20 real false-closure cases through the appeal path before trusting it.

## What is OUT of scope (hand off, do not rebuild)

These are the real portal's transactional job; the copilot deep-links to them instead: Login, Change Password, UAN Card, Activate UAN, Forgot Password, Know Your UAN, Direct UAN Allotment, UAN for Existing PF, Contact Details, Service History (view), Annexure K, and the *transactional* parts of Mark Exit / Transfer / Modify Basic Details / E-Nomination (their *knowledge* slices survive as guidance cards in ticket 09).

## (b)-honesty constraints (must hold in every ticket)

- Grievance and appeal are **drafts the member files**, never real submissions.
- The reply clock is **member-updated**, not a live feed.
- All data is **BYOD**, parsed client-side; no accounts, nothing leaves the device.
- Deterministic KB for addressees / statutes / deadlines / routing; **LLM only for prose**.

## Open questions — RESOLVED (user, 2026-09-02)

1. **Is ticket 01 (the scope cut) the right call?** **Resolved: confirm the cut.** Deep-link every pure-transaction/identity screen (Login, Activate/Forgot/Change UAN, Know Your UAN, UAN Card, Contact Details, Service History view, Annexure K) and the transactional halves of Mark Exit / Transfer / Modify Basic Details / E-Nomination; keep only their knowledge slices as ticket-09 guidance cards. Rationale: each screen either authenticates the member to EPFO or writes to its system of record — impossible citizen-side without gov APIs/accounts, and a client-side "EPFO login" is phishing-shaped. The smaller surface is the honest edge, not a gap. *Candidate to promote to a `../decisions/` note if it firms up.*
2. **Split ticket 10?** **Resolved: split into 10a (death-claim) and 10b (higher-wages).** They share no knowledge base and no persona; bundling only saved a table row. Both stay low-priority, post-foundation, prep-only. (Backlog table above updated.)

## Ticket 02 — DONE (2026-09-02)

Knowledge base written and source-cited: [2026-09-02-epf-knowledge-base.md](../research/2026-09-02-epf-knowledge-base.md). Every fact in the earlier fetch list was verified against EPFO / DARPG / DigiLocker sources and given a confidence tier; unconfirmable items are flagged there, not invented. **Findings that change other tickets** (detail in KB §10):

- **No rejection-code dictionary exists**, and "R-07 = bank mismatch" is unsupported → ticket 04 decodes free-text remark *patterns*, not codes.
- **Father's-name-on-PAN independent scrutiny is unconfirmed** (practitioner-tier, mildly contradicted by a PAN-fields source) → ticket 04 presents it as a likely cause to check; the `research/CONTEXT.md` glossary overstates it (edit pending).
- **DigiLocker passbook is not a reliable pull** (sources describe a link-out to UMANG; the official EPFO DigiLocker page now 404s) → tickets 03/06 use a **member-uploaded** passbook (passbook portal / UMANG); DigiLocker pull kept for UAN card / PPO / scheme certificate only.
- **TAT = 30 days statutory / 20 days penal-interest threshold** (Para 72(7)), not a flat 20.
- **Rejection rate:** drop the illustrative 84%; use **33.8%** (final-settlement, FY22-23). The late-2024 **21.59% is combined reject+return**, not a rejection rate (pure reject ~13.77%).
- **KYC is exact-match-gated** (EPFO circular 13 Aug 2025; mismatch → Joint Declaration), not "soft-match at seeding."

**Live-portal pass (same day):** KB §12 adds the portal-truth vs member-report split against the actual portals — every prototype claim classified as portal-confirmed (A) or reported-only (B, must carry a provenance label in the product). Charter PDF recovered from the live site: per-form TATs resolved verbatim (7/3 working days aspirational, 20 days "as per Scheme", grievance 7 working days, HQ addressee = ACC (CSD)). New portal fact for tickets 01/09: **direct UAN allotment + UAN activation are discontinued on the portal, moved to UMANG (Face Auth)** — deep-links for those go to UMANG.

**v2 priority fetches** (KB §11): the primary 13 Aug 2025 KYC circular; the 9 Mar 2026 Lok Sabha reply on rejection reasons; DigiLocker passbook-pullability checked in the DigiLocker app's EPFO issuer list itself.

## Source artifacts & related notes

- Prototype (25 screens, Current-vs-Revamped toggle): `../research/epfo-portal-clone.html`
- Revamp Scorecard source: `../research/epfo-revamp-scorecard.html`; published artifact: https://claude.ai/code/artifact/0233cf6c-88b7-4e14-ab75-f00baab3f86a
- Grounding research: `../research/cpgrams-accountability-models-2026-08-29.md`, `../research/international-analogues-per-candidate.md`, `../research/candidate-complaint-scan-2026-08-29.md`, `../research/social-listening-govt-complaints.md`
- Prior design-health analysis of the prototype: `2026-08-31T12-18-49Z__epfo-portal-clone-html.md`
- Memory: [[epfo-portal-clone]] (prototype + scorecard state, hard rules), [[govt-case-study-project]] (candidate evidence, BYOD/no-API constraints)

**Caveats:** This is a *proposed* arrangement, not a frozen plan — the two open questions above are unresolved, and the project is still officially in discovery phase per `../decisions/2026-08-28-system-design-not-anti-bribery.md`. The scorecard facts it rearranges are themselves illustrative until ticket 02 replaces them with sourced ones.

**Data source:** EPFO Revamp Scorecard (Con/Improvement cells) + the prototype's screen inventory, arranged under the citizen-side (b) constraint set from the project memory.
