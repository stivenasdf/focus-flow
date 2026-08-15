# Focus::Flow roadmap after v1.143

Updated August 15, 2026.

This roadmap starts from the live v1.143 baseline. Release numbers below describe coherent batches, not rigid deadlines. A batch can be split if testing shows that it is too risky to publish safely at once.

## Product rules

- More intelligence with less manual input.
- Important actions must remain reachable without returning to the top of a page.
- Every major chart should answer: what happened, what it means, how confident the interpretation is, and what action is reasonable.
- The same design tokens and component patterns must be used across every page.
- Imported bulk activity data must not bloat the main cloud-synced state document.
- Personalization must be bounded, explainable and resettable.

## Baseline already live

- Morning-first Today's Numbers entry.
- Recovery reserve, Training Call, load breakdown, sleep opportunity and bounded calibration.
- Basic 7-day outlook and weekly wake schedule.
- Minimum-dose lifting, warm-up tracking, RIR feedback, training-max regression and strength forecasts.
- Intervals.icu connection, activity history, manual single-activity entry, basic power and pace-duration curves, HR ranges and personal efficiency summaries.
- Weekly habit check-in and improved habit history.
- Money page foundation.
- Twelve themes, daylight shuffle and mobile swipe navigation.

## Foundation — design language before the next redesign

- Define spacing, type scale, radii, borders, surfaces, status colours, controls, menus, scrollbars, empty states and card anatomy.
- Define one chart language: axes, legends, hover details, confidence, comparison ranges and interpretation blocks.
- Use the native system UI font stack for prose so Apple devices use San Francisco and Windows uses Segoe UI. Keep a monospaced face only where aligned numerical data benefits from it.
- Add accessibility checks for light/dark contrast, keyboard focus, touch targets and reduced motion.
- Create reusable sidebar, drawer, bottom-sheet, overflow-menu and data-table components before page-specific work.

## v1.144 — adaptive navigation, Notes and global visual repair

Status: implemented and released in v1.144 on August 15, 2026.

### Desktop navigation

- Add a 210 px expandable / roughly 60 px collapsed left sidebar.
- Put Today, Recovery, Habits and Tasks first.
- Group Lifting and Activities under Training.
- Group Goals, Money and Books under Life.
- Put Stats, sync and Settings near the bottom.
- Automatically collapse at narrower desktop widths without taking useful chart space.

### Mobile navigation

- Replace the crowded tab strip with Today, Recovery, Habits, Tasks and More in a bottom dock.
- Keep swipe navigation as an optional shortcut.

### Notes

- Make Notes reachable from the persistent navigation at any scroll position.
- Replace free-floating pin/unpin behaviour with a predictable right drawer on desktop and a bottom sheet on mobile.
- Remove location jumping and width changes between modes.
- If desktop resizing remains useful, use one diagonal resize handle and one Reset size action.
- Preserve note content and the last sensible desktop width; never preserve an off-screen position.
- Keep editing minimal: headings, bullets, bold, undo/redo and plain-text paste.

### Global controls and visual repairs

- Put sync state in the persistent navigation footer with Sync now, last-sync time, error state and account access.
- Keep Settings reachable from the same location.
- Redesign 7-Day Training Outlook as a compact day timeline with clear capacity, suggested load, confidence and expandable reasons.
- Redesign Weekly Wake Schedule as aligned weekday rows with Required / Preferred / Open expressed in plain language.
- Apply the new design language to Settings and the hardest-to-read Stats summary card.

## v1.145 — Tasks visual rebuild

Status: implemented and released in v1.145 on August 15, 2026.

- Rebuild the Task page and cards using the same hierarchy as Recovery.
- Keep the closed card simple: completion, title, next action, time/due signal and one overflow control.
- Move priority, date, timer, subtasks, notes, habit/book links and destructive actions into a clean details drawer or grouped overflow menu.
- Reduce the visible filter strip; move uncommon filters into one menu.
- Keep Done, Defer, Blocked and Drop visually distinct and neutrally worded.
- Show learned estimates and evidence without cluttering every card.
- Surface stuck tasks with a small suggested first step.

## v1.146 — Today, Schedule and adaptive planning

Status: v1.146 shipped on August 15, 2026 as a user-priority Recovery and Lifting reliability release. It added iPhone-safe Recovery guidance, local morning-entry drafts, clearer morning entry, visible sleep duration, collapsed-rail sync status, a bodyweight trend card, a docked mobile navigation safe area, and fatigue-aware push-up/burpee primers. The originally planned Today/Schedule work below remains open and rolls forward; it was not silently marked complete.

- Finish the NOW / TODAY / LATER structure.
- Make Focus Now, Focus Queue and ordinary To Do unambiguous.
- Rebuild schedule entry around normal phrases and approximate periods rather than manual calendar construction.
- Show Next up and Free until only when they improve the decision.
- Let missed plans move, shrink or drop instead of accumulating as overdue clutter.
- Improve Best next move using available time, schedule, recovery, training, priorities and energy.
- Add explicit same-day run/lift ordering when both are proposed.
- Learn usual start time and duration only after at least three comparable completions, then offer a one-tap schedule suggestion instead of silently adding it.
- Calculate a feasible daily time budget from fixed commitments, historical durations and the protected sleep cutoff. Fit high priorities first and visibly move, shrink or defer lower priorities that cannot fit.

## v1.147 — Habits, Stats and remaining gamification cleanup

Status: v1.147 shipped on August 15, 2026 as a user-priority navigation, Notes, morning-entry and Money release. It replaced collapsed-sidebar letters with recognizable page icons, put the collapse control first, restored a movable and two-dimension resizable desktop Notes window with a full reset, accepted approximate sleep times such as `08:-- AM`, and rebuilt Money around individual paychecks, purchases, account payments, categories, two default credit cards and a line of credit.

The rolled-forward Habits, Stats and progression work below was completed and released as v1.148 on August 15, 2026. The Habits page now keeps sorted rows stable during check-ins, reverses consistency order, supports check-off/count/minutes/avoidance targets, preserves partial effort as Minimum kept, and adds comeback, time-fit and weekend-friction insights. Stats is organized into Recent, Patterns and History with plain-language interpretations. Visible levels, prestige, XP multipliers, streak bonuses, the generic Memory Game and the giant onboarding modal were replaced by concrete milestones and a compact progressive checklist.

### Habits

- Make Consistency sorting cycle high-to-low and low-to-high with a visible arrow.
- Keep a sorted view stable while check-ins are being tapped so rows do not jump under the finger.
- Add count, duration and avoidance habit types where useful.
- Support Full target, Minimum kept and Missed without punishment language.
- Expand pattern insights for momentum, time-of-day fit, weekend friction and comeback behaviour.

### Stats and progression

- Rebuild Stats into Recent, Patterns and History.
- Replace dense totals with interpretations such as best focus window, estimate bias and fragmentation.
- Decide whether the header level earns its space; a concrete nearest milestone may be more meaningful than a bare level number.
- Remove remaining prestige, XP multipliers, rarity/grind mechanics and streak pressure.
- Remove or hide the generic Memory Game and replace the giant Welcome Guide with progressive onboarding.

## v1.149 — Activities data integrity and importing

Status: v1.149's first repair and workout-analysis slice was completed on August 15, 2026. Manual entry is minimized by default. Every stored activity can be deleted locally; deleted synced activities stay hidden across later syncs and can be restored by rebuilding imported history. A stored activity can be repaired from an original FIT, TCX or GPX file without changing its Recovery load or session response. The repaired stream is compacted locally and excluded from the cloud document. Opening an activity now shows field coverage, whole-workout context, best-effort effort detection and comparisons with similar-duration stored efforts. Missing streams are stated plainly rather than estimated.

Still open and rolling into the next Activities batch:

- Source coverage now appears directly on each compact history row in v1.155, naming missing duration, sport, distance, HR, cycling power and load/RPE with warning or repair severity. A separate filterable report remains open if the row-level workflow proves insufficient.
- Group the report by likely cause: Strava-sourced limitation, incomplete Intervals record, failed import, unsupported sport or duplicate.
- Add Open source activity, Ignore and targeted Rebuild derived data actions. Replace file is complete.
- Batch FIT, TCX and GPX repair now has a preview, date-and-sport matching, ambiguity blocking and explicit confirmation in v1.156. A separate multi-file new-activity import with duplicate review, failure counts and one-step undo remains open.
- Deduplicate batch imports by source ID first, then start time + sport + duration; never silently duplicate load.
- Theme remaining native number controls and file controls consistently.
- Move growing detailed streams to local IndexedDB if real-world storage testing shows the compact local representation is not sufficient.
- Add import counts, failures and undo for the most recent batch.
- The v1.155 compact row and expanded detail now provide the formal per-activity data-quality summary, explicit sport, effective load source, uploaded filename and sport-specific power labels.

## v1.150 — Activities coaching intelligence

Status: completed for the current product scope in v1.159 on August 15, 2026. Per-workout pace/HR/cadence and cycling-power coverage, stream-aware effort isolation, exact cursor/touch values, weighted nearby-effort comparison, editable sport and source-activity opening are implemented. v1.159 adds an easy-run-aware detector, an interactive effort strip, a longitudinal sustained-effort explorer with 30-day/90-day/1-year/all-time ranges, Recovery-aware quality-session spacing and a personal cardio-hours progression ceiling. Running power stays out of the coaching model. Intervals.icu aggregate cycling curves do not expose a reliable source date for every point, so the local sustained-effort explorer is the recency view rather than an invented curve date.

### Curves and records

- The sustained-effort explorer shows newest evidence and trend by short, medium and long duration band; aggregate Intervals curve points remain date-agnostic when the source omits dates.
- Stale duration context is paired with the current Recovery hard-test gate; it does not turn every detected effort into a test.
- Fitness records open the source activity and approximate effort window when a locally stored source ID and stream exist.
- Duration curves and detected sections explicitly avoid implying that every point was a deliberate maximal test.

### Aerobic interpretation

- HR decoupling now has all-cardio, running and cycling views plus progressive 3%, 5% and 8% coaching-guide bands in v1.156. These are practical heuristics rather than universal physiological cut-offs.
- Running pace/HR and cycling power/HR now state which direction is useful and translate the recent percentage into plain language. More detailed comparability and confidence warnings remain open.
- Running pace/HR, cycling power/HR and the sustained-effort explorer have 30-day, 90-day, 1-year and all-time views.
- Comparisons keep sport fixed and weight duration, load, session shape and indoor/outdoor context rather than requiring brittle exact matches.
- Changes show size, confidence/sample limits and a practical interpretation.

### Awards and chart guidance

- Show awards on the activity that earned them.
- The main Awards feed now prioritizes recent achievements, v1.156 added a calm top-10 metric explorer, and v1.158 adds all-time/calendar-year scope plus a dedicated compact card. Richer grouping by sport and distance/duration remains open.
- Include near-bests such as fifth or tenth best this year so progress remains visible.
- v1.158 gives every major longitudinal chart a short What this shows / Useful direction / What to do block and places those charts in one large switchable workspace with exact-value hover/tap access.
- Prioritize weekly volume/load, intensity distribution, duration curves, aerobic efficiency and decoupling; avoid adding charts that cannot change a decision.

## v1.151 — Recovery clarity and forecast separation

Status: implemented and released in v1.151 on August 15, 2026.

- Separate estimated Body Battery into a current reserve based on logged data and a distinct forecast after outstanding expected work plus the app's current training prescription.
- Replace prescription estimates with actual logged work and training instead of stacking both drains.
- Show a conditional 5K test window in the 7-day outlook when the 42-day cadence is due, while keeping same-day recovery checks as the final gate.
- Recognize clearly titled imported 5K races, parkruns, tests and time trials; exact-distance high-RPE runs can also qualify, while ambiguous ordinary runs do not silently reset the cadence.
- Compare today's whole-body, leg, back and upper-body fatigue with the user's own previous seven days.
- Rename user-facing systemic fatigue to whole-body fatigue and explain that it is a subjective general-fatigue signal, not a direct nervous-system measurement.
- Explain that sleep-bar colors use duration versus the sleep target, timing bands show consistency, and WHOOP sleep score remains separate.
- Give lifting a dedicated marker in the 14-day Training Call history, including a strength strip on mixed cardio/lifting days.

## v1.152 — Recovery weighting, sleep action and reserve trajectory

Status: implemented and released in v1.152 on August 15, 2026.

- Keep the newest HRV bar and label inside the chart edge.
- Give feel, freshness, sleep/recovery and fatigue visuals progressive semantic colors rather than abrupt three-color jumps where a continuum is meaningful.
- Make Recovery weighting visible: feel and whole-body fatigue are ×1.5; direct sensor signals are ×1; WHOOP Recovery is reduced to ×0.5 when HRV or sleep is also present to limit overlap.
- Preview exactly what clearing learned mismatch labels changes today: Recovery index, Training Call, prescribed-day battery forecast and number of labels removed. Keep fixed safety rules and source data untouched.
- Turn a large recent sleep deficit into a specific three-night sleep-opportunity and training-protection response while continuing to state that the total is not an exact balance to repay hour-for-hour.
- Add a small Body Battery trajectory from morning to now to after-plan. A gentle ordinary-time-awake allowance is used only when wake time is logged, is itemized in the ledger and updates while Recovery is open.

## v1.153 — Money priority foundation and historical Recovery context

Status: implemented and released in v1.153 on August 15, 2026.

- Recognize a lift completed today before asking the recommendation engine for another lift; show the completed lift by name and confirm its estimated load is already included.
- Keep an open next-day wake commitment visibly open while suggesting an asleep, wind-down and wake window from recent personal wake timing plus the current sleep-opportunity buffer.
- Show physical-fatigue comparisons as explicit arithmetic: today minus the rolling 7-day median equals the signed change, followed by rising / easing / steady direction.
- Evaluate every historical HRV bar against the rolling 30-day baseline that existed on that date. Draw the changing usual-range ribbon and baseline through time; keep fixed thresholds visible on other suitable Recovery charts.
- Extend Money accounts with APR / savings interest, debt minimum payments, emergency-fund designation, loan / financing types and confirmation of penalty-free extra payments.
- Auto-estimate essential monthly costs from logged Housing, Groceries, Transport, Health, Debt / interest and debt minimums, with an optional manual override.
- Auto-calculate selectable 3- or 6-month emergency targets, a one-month starter-buffer heuristic, and a 12-month emergency projection that includes the entered savings rate and monthly contribution.
- Add a transparent next-dollar sequence: monthly obligations and minimums → starter buffer → highest-interest expensive debt → full emergency fund → low-rate financing versus uncertain investing.
- Keep investment return as a user-entered comparison assumption, not a promise; block early-financing guidance until prepayment terms are confirmed.

Remaining Money phase 2:

- Support recurring transactions and CSV import before attempting bank-account connectivity.
- Add monthly cash flow, category spending, savings rate, debt balance, investment contributions and net-worth charts.
- Add debt due dates, investment fees and richer account/tax assumptions.
- Add highest-interest versus lowest-balance payoff scenarios with time to debt-free and interest avoided side by side.
- Keep the concrete financial target on Money and link it to any broader life goal on Goals.

## v1.154 — Recovery and training intelligence completion

Status: completed in v1.159 on August 15, 2026. v1.154 handled the chart/load separation and forecast groundwork; v1.159 closes the defined Recovery/training intelligence items with conservative learning, same-day ordering, editable lift classifications, decision history, personal experiments, an independent adaptive movement primer and prescription-linked habits.

- Recovery keeps plain-language signal groups and treats the summary index as context, not a Garmin Body Battery equivalent.
- Cardio, work and lifting stay separate through load, time-budget and prescription decisions. A full cardio-hours ceiling does not by itself cancel a separately safe lift.
- Prediction-versus-reality learning requires repeated evidence, names the evidence and applies conservative caps.
- Activity priority and same-day cardio/lifting order are explicit.
- Lift movement area and fatigue price are editable; cautious lift-fatigue learning needs repeated next-day pairs and pauses when manually overridden.
- Recovery decision history connects saved call, actual sessions and response. Optional personal experiments show context without claiming causation.
- Push-ups and burpees are one independent adaptive movement primer with its own dose, fatigue-aware mix and progression.
- Cardio, lifting and primer appear as Recovery-linked habits whose dose follows the prescription; prescribed rest/skip counts as following the plan.
- Literature and calculation review remains a permanent safety-maintenance responsibility rather than a one-time feature checkbox.

## v1.155 — Integrations and low-effort nutrition

Status: v1.155 shipped on August 15, 2026 as a user-priority Activities reliability release. It restored the mobile reload control; rebuilt Activity history into compact one-column paginated rows; made sport and missing-data severity explicit; separated running power from cycling power and records; fixed duration-curve pointer coordinates; included exact uploaded-file run efforts in Personal bests; used uploaded filenames as visible titles; and connected source load or duration × session-RPE load to the original date in Recovery and its later fatigue context. Personal aerobic baseline coverage now says whether the first ride is usable and names each missing prerequisite. The WHOOP and Nutrition work below remains open and rolls forward; it was not silently marked complete.

- Add a secure OAuth backend before WHOOP import; never store a WHOOP client secret in GitHub Pages.
- Map imported WHOOP sleep, recovery, HRV and resting HR into Today's Numbers with source labels and manual override.
- Import WHOOP physiological cycles and work-labelled activities for labour calibration. Consolidate overlapping activity windows and use Day Strain as the daily nonlinear exertion reference; never add visible WHOOP activity Strain scores arithmetically.
- Harden direct Zwift to Intervals routing and duplicate/source diagnostics.
- Keep Nutrition lightweight: ate enough for training, protein anchor, produce, hydration and optional note.
- Estimate simple replenishment ranges from bodyweight plus the prescribed session’s type, duration and intensity: daily protein range, carbohydrate range and approximate exercise-energy replacement. Show ranges and familiar food portions, never fake precision.
- Keep total-calorie guidance separate from exercise calories. A safe daily target also needs normal living needs and the user’s goal; warn when the available data could encourage chronic low energy availability rather than silently prescribing a deficit.
- Prefer importing summaries from an existing meal tracker over building a calorie database or requiring weighed food.
- Decide the meal-tracker target before building a connector.

## v1.156 — Activities repair safety, volume and heart-rate context

Status: implemented and released on August 15, 2026 as a user-priority Activities and Recovery reliability build.

- Ignore reported elevation when a run is identified as virtual, retain the raw value for transparency and explain why it is not treated as difficulty.
- Protect single-file replacement from an opposite-sport or wrong-date file. Batch repair previews every match, accepts only a clear same-date and same-sport candidate, and blocks ambiguity or duplicate targeting before any stored activity changes.
- Add eight-week running distance, cycling distance and combined-cardio time/load charts. Combined cardio deliberately avoids adding kilometres across unlike sports.
- Add plain-language useful-direction guidance to running pace/HR, cycling power/HR and heart-rate decoupling, including sport-specific decoupling views and clearly labelled coaching heuristics.
- Keep recent achievements as the default Awards view and add a top-10 explorer by metric.
- Add 30-day, 90-day and all-time distance-by-sport totals.
- Continue storing activity maximum heart rate and surface it in activity details, recent highest-HR context and Awards.
- Add resting heart rate to Today's Numbers with separate HRV4Training one-minute, WHOOP overnight and other-source baselines. Use it as visible context only until enough same-method observations support cautious validation; do not blend unlike measurement methods or silently alter the Recovery score.

## v1.157 — Activity response, stream analysis and Recovery clarity

Status: implemented and released on August 15, 2026 as a user-priority Activities, Sleep and Body Battery reliability build.

- Recommend one consistent HRV4Training morning resting-heart-rate source for manual entry while retaining clearly separated WHOOP overnight and other-source histories. Resting heart rate remains excluded from the Recovery master score, but can support an explicitly labelled activity-load estimate.
- Calculate a cautious Focus::Flow activity load when a TCX/FIT/GPX file has useful heart-rate data but no source load. Source load remains first priority; a later session-RPE response overrides the HR-derived estimate; missing inputs remain pending rather than invented.
- Rebuild How did it go? as a readable full-width activity response with larger questions, a nearby open control and explicit Close without saving / Save and close actions.
- Add synchronized per-workout elevation, pace/speed, sport-specific power, heart-rate and cadence traces when the uploaded stream contains them. Every trace shares one time cursor and detected efforts are softly aligned across the stack. Virtual-run elevation stays excluded from training interpretation.
- Show how last night's sleep changed the rolling 14-day deficit, including the latest shortfall and the older shortfall that rolled out of the window.
- Separate the Body Battery morning, current and after-plan values from the trajectory plot so neither the line nor the numbers obscure the other.

## v1.158 — Activity decisions, visual consistency and low-friction capture

Status: implemented and released on August 15, 2026 as an Activities usability, Recovery performance and cross-app consistency build.

- Consolidate longitudinal Activities charts into one large switchable workspace while keeping synchronized per-workout traces inside each expanded activity.
- Add What it shows / Useful direction / What to do guidance beside every workspace chart and exact-value hover/tap access where data exists.
- Make Activity file actions visible above the collapsed manual form. Keep safe multi-file repair explicitly separate from multi-new-activity import.
- Give Activity Awards a dedicated compact card and all-time/calendar-year Top 10 scope.
- Add a transparent running-load guard using personal rolling volume and prior-30-day longest-run context without presenting one universal mileage rule as medical certainty.
- Avoid rebuilding every Recovery card on each repeated navigation; render once per day and continue rerendering when relevant data changes.
- Compact Bodyweight Trend, restore inherited dark-theme text contrast, and audit Money inputs/generated assets against theme tokens.
- Let a reading-linked Focus session capture an unfamiliar word immediately; allow its meaning to be filled in later before review games use it.

## v1.159 — Activities coaching and Recovery completion

Status: implemented on August 15, 2026. This release closes the current v1.150 and v1.154 feature scopes, adds the personal cardio-hours ceiling, edits/repairs sport at the activity level, closes old RPE prompts after 14 days, prevents replacement activities from double-counting manual loads, and makes workout timeline/effort values inspectable.

## v1.160 — Goals, Books and review loop

- Complete goal status, next milestone, evidence, obstacle planning, review cadence and archive.
- Connect goals to actual task, habit, reading, training and Money evidence.
- Complete key book learnings, finish reflection, spaced review and reading-goal pacing.
- Refine Weekly Review, Morning Brief and Evening Shutdown into one low-effort planning loop.

## v1.161 — Cross-app personal intelligence

- Build What Focus::Flow has learned about me with evidence links and confidence.
- Improve What should I do now using the mature task, schedule, training and recovery systems.
- Add personal friction detection across tasks, habits and schedules.
- Add cautious adaptive planning and decision-history follow-up.
- Detect recurring habit/task/training timing and historical duration, then present explicit schedule suggestions with evidence and an accept/dismiss choice.
- Protect required commitments and prescribed sleep first, calculate remaining usable time, and avoid presenting an impossible day as a list of personal failures.
- Preserve explicit user control over every learned adjustment.

## Deferred until the evidence or need is strong

- Maintenance Mode as an explicit mode.
- Population comparisons that cannot be normalized responsibly for age, sex, training history and measurement method.
- Automatic bank connectivity before the manual/CSV Money model proves useful.
- Full calorie and macro tracking inside Focus::Flow.
- Continuous theme colour blending; fixed, tested phase changes remain safer for contrast and identity.
