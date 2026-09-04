# EPFO Portal Design Study

A local-only, unpublished comparative prototype of India's EPFO Member e-Sewa portal (`epfo-portal-clone.html`), toggling between a byte-faithful Current Portal replica and a Revamped Portal redesign, built to argue for specific, evidence-grounded fixes to real member-facing problems.

## Language

**Father's Name**:
The KYC/PAN field holding the member's father's name. A mismatch here (e.g. PAN says "RAKESH K. VERMA" against "RAKESH VERMA" on Aadhaar/EPFO) is a rejection trigger reported by members and practitioner guides, not one established by any EPFO circular; and the stronger claim that EPFO checks this field independently of the member's own name during claim scrutiny is unverified (one PAN-facing guide lists the checked fields as name, date of birth and gender only, with the father's name absent). "OTHERS" itself is not a published EPFO category. In the study the field is therefore modeled as the *proposed decode* behind the raw "OTHERS" remark: a likely cause to check, not an asserted mechanism (verification record: [2026-09-02-epf-knowledge-base.md](2026-09-02-epf-knowledge-base.md), section 3). What remains fully true: no KYC screen, current or redesigned, surfaced the field before this study added one.
_Avoid_: "father's/guardian name" — no guardian-in-place-of-father scenario is modeled for this persona; the hedge doesn't correspond to anything real in the study and should collapse to the plain term.
