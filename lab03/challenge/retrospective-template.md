# Sprint Retrospective · Realtime Quiz

This document defines the team retrospective standard and records the retrospective review session conducted at the conclusion of **Sprint 1**.

---

## 1. Sprint Details

| Attribute | Details |
| :--- | :--- |
| **Sprint Name / Number** | Sprint 1 (Weeks 4–5 of 14-week hybrid schedule) |
| **Timebox / Dates** | Tuesday 2026-10-20 to Monday 2026-11-02 (10 working days) |
| **Retrospective Meeting** | Monday 2026-11-02, 15:15 – 16:00 (45-minute timebox) |
| **Meeting Location / Channel** | IT Department Project Lab / Hybrid Discord Session |
| **Facilitator** | Student B (Scrum Master) |
| **Sprint Goal** | *"Establish the foundational project skeleton with continuous integration, user authentication with roles, and basic quiz authoring capabilities."* |

---

## 2. Attendees

| Name | Project Role | Attendance Status |
| :--- | :--- | :--- |
| **Student A** | Product Owner / Developer | Present |
| **Student B** | Scrum Master / Developer | Present |
| **Student C** | Developer | Present |
| **Student D** | Developer | Present |

*Note: In accordance with Scrum best practices, the Project Manager and Sponsor do not attend the internal retrospective to preserve open, psychological safety for honest team reflection.*

---

## 3. Sprint Data & Burndown Observations

### Quantitative Metrics
- **Planned Capacity:** 4 students × 10 h/week × 2 weeks = **80 hours**.
- **Actual Hours Expended:** 78 hours (Student A: 21 h, Student B: 19 h, Student C: 20 h, Student D: 18 h).
- **Committed Points:** 30 story points (7 Must items: B-01 to B-07).
- **Completed Points (DoD Met):** **25 story points** (B-01, B-02, B-03, B-04, B-06, B-07).
- **Unfinished Points (Returned to Backlog):** **5 story points** (Item B-05: Create quiz).
- **Achieved Velocity:** **25 points** (Planned: 30 points; 83.3% completion rate).

### Burndown Observations (from `burndown.mmd` daily data)
1. **D0–D2 Start Stall (Flatline at 30 points):**  
   For the first two full days (D0, D1, D2), the team recorded zero burned story points. The actual line remained flat at 30 points, causing the team to immediately fall **two full days behind** the ideal burn rate ($30 \text{ pts} \rightarrow 24 \text{ pts}$). This occurred because all developers began multiple stories in parallel and encountered local Docker/Postgres environment alignment issues rather than completing foundational setup together.
2. **D4–D5 Mid-Sprint Plateau (Stall at 23 points):**  
   Work paused between D4 and D5 with no completed stories as developers switched between frontend route guards and backend authentication controllers.
3. **D6–D9 Steep Catch-up Curve (Burned 15 points in 4 days):**  
   Once the authentication pipeline (B-02, B-03, B-04) and question authoring (B-06, B-07) converged, points dropped rapidly from 20 to 5.
4. **D10 Last-Mile Spillover (5 open points):**  
   On Day 10, 5 story points remained open because Item B-05 failed the Definition of Done (test coverage and accessibility requirements were left until the final hours and could not be resolved prior to the sprint boundary).

---

## 4. What Went Well

- **Robust CI/CD Foundation (B-01):** The GitHub Actions pipeline, multi-stage Docker builds, and Flyway database migrations were successfully implemented and run cleanly on every pull request.
- **Solid Core Security & Role Architecture (B-02, B-03, B-04):** User registration, password hashing (BCrypt), 12-hour expiration JWT tokens, and role-based route guards (`ROLE_INSTRUCTOR`, `ROLE_STUDENT`) were fully implemented and pass automated integration tests.
- **Complex Question Management Delivered (B-06, B-07):** Despite being the largest single item in the sprint (8 points), question creation, editing, deletion, and single/multiple option handling met all acceptance criteria without blocking the team.
- **Effective Daily Scrums:** The 15-minute daily standups kept everyone aligned and quickly highlighted blockers during the mid-sprint surge.

---

## 5. What to Improve

- **Eliminate Delayed Sprint Start (The D0–D2 Flatline):** Starting 4–5 separate stories simultaneously on Day 1 led to excessive context switching, branch collisions, and delayed integration. No single story reached "Done" until Day 3.
- **Stop Leaving Definition of Done (DoD) Checks to the Final Day:** Item B-05 was functionally code-complete on Day 9, but automated JaCoCo line coverage was only 68% (failing the 80% DoD gate) and contrast on draft/published buttons failed WCAG AA. Because verification happened on Day 10 afternoon, there was insufficient time to write unit tests and fix styling.
- **Mitigate Product Owner Dual-Role Overload:** Student A spent substantial hours refining upcoming Sprint 2 requirements, answering user interface questions, and managing sponsor communications, which severely reduced available coding time for B-05 in Week 2.
- **Decompose Large Stories (Reduce Story Point Variance):** Sprints containing 5-point and 8-point stories create high variance in burndown tracking and increase the penalty when a single item misses the DoD.

---

## 6. Action Items

The following action items are derived directly from the burndown observations and team challenges identified during Sprint 1.

| # | Action Item | Root Cause Addressed (Burndown Data) | Owner | Due Date | Check-in Next Retrospective |
| :-: | :--- | :--- | :--- | :--- | :--- |
| **A-01** | **Enforce a strict WIP limit of maximum 2 concurrent stories** across the four developers. Developers must pair or assist code reviews before picking up new tickets to avoid task thrashing. | D0–D2 flatline (30 points held for 2 full days due to 4 simultaneous active branches). | **Student B** (Scrum Master) | 2026-11-03 (Sprint 2 Day 1) | Verify that first story burns down by D2 in Sprint 2 burndown. |
| **A-02** | **Institute Shift-Left DoD verification with a D-9 (12:00) Code Freeze**: PRs must include JaCoCo $\ge 80\%$ test coverage and basic WCAG checks before requesting review; all development must freeze by Day 9 noon for final QA/testing. | D10 spillover of 5 points (B-05 failed DoD coverage check at the last hour of sprint). | **Student A** (PO / Dev Lead) | 2026-11-11 (Sprint 2 Day 8) | Confirm zero stories carried over due to late DoD test failures. |
| **A-03** | **Slice all backlog items to $\le 5$ points (target 2–3 points)** during Sprint 2 planning and refinement. Decompose large stories into distinct API contract, backend service, and frontend UI slices. | Mid-sprint plateau (D4–D5 at 23 pts) and large carryover risk from monolithic stories. | **Student A** (Product Owner) | 2026-11-03 (Sprint 2 Planning) | Check backlog sizing distribution in Sprint 2 planning table. |
| **A-04** | **Re-balance Student A's development allocation**: Cap Student A's Sprint 2 development tasks at 5 story points max (e.g., completing carried-over B-05) to ensure sufficient time for Product Owner duties and stakeholder updates. | Under-delivery of B-05 due to PO role context switching in Week 2. | **Student B** (Scrum Master) & **Student A** (PO) | 2026-11-03 (Sprint 2 Planning) | Review Student A's workload and completed story points. |

---

## 7. Retrospective Template Standard (Blank Form for Future Sprints)

For reference during upcoming retrospectives (Sprints 2, 3, and 4), the standard template layout is maintained below:

```markdown
# Sprint [Number] Retrospective · Realtime Quiz

## 1. Sprint Details
- **Sprint Name / Number:** Sprint [X]
- **Timebox / Dates:** [Start Date] to [End Date]
- **Meeting Date & Time:** [Date, Time, Duration]
- **Facilitator:** Scrum Master
- **Sprint Goal:** [Sprint Goal Text]

## 2. Attendees
- **Attendees:** [List of participants and roles]
- **Absentees:** [List of absentees and reasons, if any]

## 3. Sprint Data & Burndown Observations
- **Planned Capacity:** [Hours]
- **Actual Hours Expended:** [Hours]
- **Committed Points:** [Points]
- **Completed Points (DoD Met):** [Points]
- **Carried Over Points:** [Points]
- **Achieved Velocity:** [Points]
- **Burndown Observations:** [Key inflection points, lag analysis, plateau analysis]

## 4. What Went Well
- [Positive outcome 1]
- [Positive outcome 2]

## 5. What to Improve
- [Impediment / bottleneck 1]
- [Impediment / bottleneck 2]

## 6. Action Items
| # | Action Item | Root Cause Addressed | Owner | Due Date | Check-in Next Retro |
|---|---|---|---|---|---|
| A-01 | [Specific Action] | [Observation] | [Owner] | [Date] | [Verification Criteria] |
```
