# 06: Sync the EPFO Revamp Scorecard

**What to build:** The EPFO Revamp Scorecard artifact reflects the shipped Grievance Redressal screen. Grievance is a new screen, so the scorecard gains a Grievance row and the aggregate count moves from "of 24" to "of 25". Track Claim Status's row is updated to note its dispute path now links into the standalone Grievance screen. The honest illustrative-data caveats (no real EPFiGMS/CPGRAMS/RTI submission) are recorded.

**Blocked by:** 02, 03, 04, 05.

**Status:** done

- [x] A Grievance row is added to the scorecard with Pro / Con / Improvement cells reflecting exactly what shipped (guided routing, composer, 21-day clock, verified closure, pre-filled appeal), and the illustrative boundary stated honestly in the Con. *(Placed at the end of the Core narrative group, right after Track Claim Status. Con names the illustrative boundary: nothing filed for real, ref/routing/clocks/closure/forums all demo state, clock runs from a fixed illustrative "today".)*
- [x] The aggregate stat is recomputed from "of 24" to "of 25" in both places it appears (the lede paragraph and the closing-notes bullet), verified by counting the pro and cosmetic-pro rows so they sum to 25. *(Lede now "Fourteen of the twenty-five"; closing bullet now "14 of 25". Verified by grep: 14 `class="pro"` + 11 `class="cosmetic-pro"` = 25 screen rows; no stray "twenty-four"/"of 24"/"Thirteen" remain.)*
- [x] Track Claim Status's row notes that its per-claim dispute path now links into the standalone Grievance screen rather than holding a parallel grievance surface. *(Appended to Track's Pro cell: its dispute path now cross-links in one step into the standalone Grievance screen, pre-filled from the claim, rather than holding a parallel grievance surface of its own.)*
- [x] The scorecard artifact is redeployed to the same existing URL. Zero em-dashes in the scorecard. *(Redeployed to https://claude.ai/code/artifact/0233cf6c-88b7-4e14-ab75-f00baab3f86a with favicon unchanged; em-dash grep returns 0.)*
