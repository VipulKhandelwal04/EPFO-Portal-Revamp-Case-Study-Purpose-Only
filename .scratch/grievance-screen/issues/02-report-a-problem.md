# 02: Report a problem (symptom picker, composer, submit)

**What to build:** On the grievance screen, a member can report a problem end to end. They choose what went wrong in plain language, which routes the grievance to the correct EPFO office; they write the grievance with a composer that structures it into what happened, which rule or entitlement applies, and the outcome they want; a completeness-and-evidence prompt runs; and Submit produces an illustrative reference number and a filed-record confirmation. This reuses the EPFiGMS-draft generation already prototyped in Track Claim Status rather than duplicating it.

**Blocked by:** 01.

**Status:** done

- [x] A plain-language symptom picker maps each option deterministically to an EPFO office or queue (no adaptive scoring), replacing a raw department tree.
- [x] A grievance composer structures the member's text into what-happened, the rule or entitlement that applies, and the outcome sought.
- [x] A completeness-and-evidence prompt runs before submit; submitting an incomplete grievance is blocked with a specific correction message, not a generic error. *(Five ordered checks: symptom, claim ID, what-happened, outcome, evidence, each with its own message.)*
- [x] Submit generates an illustrative reference and shows a filed-record confirmation; the reference is tagged illustrative inline. *(Reference and filed date both carry an inline (illustrative) tag; the note carries the claim ID and cited rule.)*
- [x] In Current mode the report action falls through to the existing byte-faithful behavior, never the Revamped flow. *(submitGrievance guards on currentMode and returns dead(); the screen also redirects to home in Current mode.)*
- [x] Verified in-browser (full report flow), mode-gated, and the reset from ticket 01 clears composer state on re-entry. Zero em-dashes; `node --check` passes.
