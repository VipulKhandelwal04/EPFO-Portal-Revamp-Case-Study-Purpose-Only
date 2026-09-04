# CPGRAMS, screen by screen: what it holds now, what to change

**Date: 2026-08-29.** Based on the live portal (pgportal.gov.in, version 7.0), public screens observed directly. Two goals per screen: (1) make it easy to report, (2) reduce false closure (a grievance marked "disposed" without the problem being fixed).

Each change is tagged:
- **[Portal]** = a change the government would make inside CPGRAMS. Real lever, but you cannot ship it.
- **[App]** = a change your citizen-side companion tool can deliver with no CPGRAMS cooperation. This is your buildable path.
Many changes come in both forms: the portal version is ideal, the app version is what you can actually build now.

The two highest-leverage fixes, before the screen list:
1. **Guided, plain-language routing at report time.** The single biggest reporting failure is the citizen picking the wrong ministry/department, which buries the grievance. Fix the category step and you fix most of "hard to report."
2. **Verified closure, not self-closure.** The single biggest false-closure fix is to stop treating the department's "disposed" as the truth, and instead ask the citizen "was it actually fixed?" and make the appeal one tap, pre-filled, and time-boxed.

---

## Screen 1 — Home / landing

**Holds now:** government header and DARPG branding; top nav (View Status, Nodal PG Officers, Redress Process, Grievance menu, Nodal Authority for Appeal, Mobile App, Language, Sign In); a carousel promoting the Samadhan Didi AI chatbot and voice-based lodging; an "About CPGRAMS" block; "What's New"; and a red warning that email grievances are not entertained.

**Problems:** the primary action (lodge a grievance) is buried inside a dropdown menu, not a front-and-centre button; a first-timer cannot tell where to start; the page sells features (chatbot, voice) more than it guides the anxious user.

**Changes:**
- **[Portal/App]** One large primary button: "Report a problem" — and a second, equal one: "Check / appeal my complaint." Everything else is secondary.
- **[Portal/App]** A three-step "how this works" strip: Report → 21-day reply → if not fixed, appeal. Set the expectation up front, including the appeal right, which almost no one knows.
- **[App]** A live "typical resolution time for this department" figure, from your own aggregated data, so the citizen knows what normal looks like before they start.

## Screen 2 — Registration / sign-up

**Holds now:** a heavy form required *before* lodging — Name, Gender, full Address (premise, locality, sub-locality), Country, State, District, Pincode, Mobile, Phone, Email, and a captcha.

**Problems:** you must complete a long personal-details form before you can even describe your problem; this is the first big drop-off; the captcha and phone/address fields add friction; many citizens abandon here.

**Changes:**
- **[Portal]** Let people describe the problem first, register last (report-then-register). Reduce mandatory fields to mobile + OTP; collect address only if the grievance needs it.
- **[Portal]** Offer prefill from DigiLocker (name, address) so the citizen does not retype identity details.
- **[App]** Your app can hold the citizen's details once, locally, and pre-compose everything, so the portal form is filled in seconds. This is the bring-your-own-data pattern: the user types their details once into your tool, never again.

## Screen 3 — Lodge Public Grievance (behind login)

**Holds now:** select the Ministry / Department / Organization (a dropdown tree), a grievance description with a character limit, an option to attach a PDF, and submit, which returns a registration number.

**Problems:** the department tree is the core reporting failure — a citizen does not know whether a passport delay is MEA, or a PF issue is EPFO vs the Labour Ministry, so the grievance lands in the wrong queue and is closed as "does not pertain to us"; the free-text box gives no help writing an effective grievance; there is no completeness check or evidence prompt.

**Changes:**
- **[Portal/App]** Replace the department tree with a **symptom-based guided picker**: "What went wrong?" in plain language, which maps to the correct department and auto-detects jurisdiction (central vs state). This is the FixMyStreet routing idea and the biggest single ease-of-reporting win.
- **[Portal/App]** A **grievance composer** that structures the text into: what happened, what rule/entitlement applies, and the specific outcome you want. A vague grievance invites a vague closure; a specific one is harder to close falsely.
- **[App]** An **evidence prompt** at report time (photo, prior reference numbers, dates) and a **completeness check** before submit, so nothing is missing that the department could later use to close it.
- **[App]** **Save draft** and vernacular/voice input (the portal already has voice via Samadhan Didi; extend it).

## Screen 4 — View Status / track

**Holds now:** Registration number + Email or Mobile + captcha → the status and, on closure, the Action Taken Report (ATR).

**Problems:** the citizen must hold the registration number and re-enter a captcha each time; the status is coarse and does not show which office is sitting on the file or for how long past the 21-day clock; the closure text is often boilerplate.

**Changes:**
- **[App]** Keep the citizen's own timestamped record (filed date, 21-day due date, each update, closure date) so they never lose the reference number and can see the clock. This is the audit trail the portal does not surface.
- **[Portal]** Show a clear stage view with the responsible office named and days-elapsed-vs-clock, so a stall is visible and attributable.
- **[Portal/App]** A visible countdown to the 21-day reply deadline, and a one-tap "send reminder" when it lapses.

## Screen 5 — Closure / Action Taken Report (the false-closure screen)

**Holds now:** when a grievance is disposed, the citizen sees the department's ATR — frequently a short, generic "action taken" note that restates the problem or says it does not pertain to them.

**Problems:** this is where false closure happens. A self-written, unstructured ATR lets a department close a ticket without doing anything, and the citizen has no structured way to contest it.

**Changes:**
- **[Portal]** Force a **structured ATR**: a required field distinguishing "action taken" from "explanation of why no action," what was done, by which officer, and supporting evidence/document. Boilerplate becomes impossible.
- **[App]** A **closure classifier**: paste or read the ATR and label it — real action, explanation, or non-answer — so the citizen instantly knows whether to accept or appeal.
- **[App]** Capture the citizen's own "before" evidence and, where relevant, an "after" check, so closure can be tested against reality (the San Diego before/after idea).

## Screen 6 — Rate Grievance / feedback (the appeal trigger)

**Holds now:** after closure the citizen can rate the resolution; rating it "Poor" unlocks the formal appeal (30-day window). This lever exists but is obscure.

**Problems:** almost no one knows that rating "Poor" is what unlocks the appeal; the rating is presented as satisfaction feedback, not as the gateway to escalation; many citizens passively accept a false closure because the next step is hidden.

**Changes:**
- **[Portal/App]** Ask the **verified-closure question** plainly: "Was your problem actually resolved? Yes / No / Partly." A "No/Partly" immediately surfaces the appeal path. This is the Japan follow-up-review idea and the core anti-false-closure move.
- **[Portal/App]** Make the appeal **one tap from a Poor/No rating**, with the 30-day clock shown.
- **[App]** Feed every "No/Partly" into your **department scoreboard** (median resolution time, false-closure rate, citizen-verified satisfaction) — the accountability metric CPGRAMS does not publish. Rank on verified resolution, never on complaint volume.

## Screen 7 — Appeal (Nodal Authority for Appeal)

**Holds now:** a route to file an appeal to a nodal appellate authority, within 30 days of a Poor rating.

**Problems:** the appeal often returns to an office close to the one that failed; the citizen must re-explain everything; the form is not pre-filled.

**Changes:**
- **[App]** **Pre-fill the appeal** with the original grievance text and the closure ATR verbatim, so the citizen does not start over.
- **[App]** Draft the appeal to cite the specific rule the office broke and the outcome sought, and point onward to RTI and the relevant ombudsman/Lokpal if the appeal also fails — an escalation ladder tilted toward a forum independent of the closer.
- **[Portal]** Route appeals to an authority genuinely independent of the closing office (the examiner-independence idea from Japan's administrative appeal reform).

## Screen 8 — Reminder / Clarification

**Holds now:** send a reminder or respond to a clarification request on an open grievance.

**Changes:**
- **[App]** Auto-prompt a reminder the moment the 21-day clock lapses, pre-written and reference-numbered.
- **[Portal]** Make an unanswered clarification request itself start a visible sub-clock, so it cannot be used to park a grievance indefinitely.

---

## Cross-screen: the accountability layer (mostly [App])

The features above fix the individual journey. The accountability layer, built from aggregated user data, is what creates system pressure:
- A public **department/ministry scoreboard**: median resolution time, false-closure rate, citizen-verified satisfaction.
- A periodic **recurring-failure report** (top repeated false-closure patterns).
- **Collective escalation**: when many users hit the same false closure at one office, package a joint RTI/media-ready dossier.

Two hard rules carried from the accountability research: never rank on a metric an office can improve by suppressing complaints (rank on verified resolution), and never expose a complainant to retaliation (CPGRAMS discloses identity, so any public feature must be anonymized). See `cpgrams-accountability-models-2026-08-29.md`.

## The honest split

Screens 1-4 changes are mostly about **easy reporting** and can be delivered largely by your companion app (guided routing, pre-fill, composer, evidence, local record). Screens 5-7 changes are about **false closure**; the strongest versions (structured ATR, independent appeal routing) are portal/state-side, but the app can still deliver the verified-closure question, the closure classifier, the pre-filled appeal, and the scoreboard — which together attack false closure without any government change.
