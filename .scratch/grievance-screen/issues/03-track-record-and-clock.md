# 03: Track (local record, 21-day clock, reminder)

**What to build:** A filed grievance shows a timestamped record with a visible countdown to the 21-day reply due date, so the member can tell a normal wait from a stall. Once the clock lapses, a one-tap, pre-written, reference-numbered reminder appears.

**Blocked by:** 02.

**Status:** done

The grievance record is a session-scoped in-memory object (no backend), shape from prototyping:

```
{ ref, filedOn, dueOn /* filedOn + 21 days */, stage, atr, verifiedResolved: 'yes' | 'no' | 'partly' | null }
```

- [x] The filed grievance shows a record with filed date, 21-day due date, and current stage, rendered with the existing status-steps timeline (done / warn / bad states). *(Filed panel gained "Reply due by" + "Reply clock" kv rows and a `#grv-timeline` status-steps list; stages are filed (done) then under-review (warn) / routed (done), then reply-due (warn on track, bad lapsed).)*
- [x] A visible countdown to the 21-day due date is shown; the clock is computed at runtime in the browser from a fixed illustrative filed date. *(`#grv-countdown` pill: "21 days to reply" [warn] on track, "7 days overdue" [bad] lapsed. `grvDaysBetween()` computes the diff at runtime via the existing `validDMY` parser against a fixed illustrative "today" anchor, so both states reproduce identically every review.)*
- [x] When the due date has lapsed, a one-tap pre-written, reference-numbered reminder is offered. *(`#grv-reminder` block shows only in the lapsed state; pre-written text quotes the reference, filed and due dates, and claim ID; "Send reminder (demo)" logs a "Reminder sent (demo)" step onto the timeline and shows a "nothing was actually transmitted" confirmation.)*
- [x] Every illustrative figure (resolution-time medians, demo dates and reference) is tagged inline. *(Reference, filed date, due date each carry an inline `(illustrative)` tag; median line reads "about 18 days (illustrative)". The live countdown number is left untagged since the due date it derives from is tagged.)*
- [x] Verified in-browser in both the pre-lapse and lapsed states, mode-gated, with reset returning the record to a clean state. Zero em-dashes; `node --check` passes. *(Both states asserted via scripted DOM checks; a two-button demo clock control moves only the illustrative "today". Reset (route hook + mode-switch block) restores the report panel, clears fields, and resets `GRV.asOf` and `GRV.reminderSent`. In Current mode the screen redirects to home and `setGrievanceClock`/`sendGrievanceReminder`/`submitGrievance` all fall through to `dead()`. No console errors.)*
