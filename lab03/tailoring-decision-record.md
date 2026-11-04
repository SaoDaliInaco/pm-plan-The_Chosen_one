# TDR-01 · Life cycle and methodology for the Realtime Quiz project

Status: proposed · 2026-11-04 · to be decided by the sponsor (Head of IT Department)

## Context

The Realtime Quiz project will be delivered by a team of four junior student developers, each contributing 10 hours per week. The project has a fixed duration of 14 weeks, starting on 29 September 2026, with a pilot involving 50 students in Week 14. The sponsor requires an approved project management plan by the end of Week 3, a fixed cash budget of $200 and an early working MVP demonstration by Week 7. Although eight Must features are defined in the charter, detailed UI screens, question flows and real-time interaction requirements may evolve during development. Technical uncertainty is significant because WebSocket broadcasting must achieve less than 500 ms latency and less than 200 ms timer drift on a limited 2 GB RAM VPS. Therefore, the project needs formal planning and governance together with iterative development and frequent feedback.

## Options considered

1. Waterfall (score 3.00/5): Provides strong upfront planning and formal sponsor control but delays feedback and increases the risk of discovering technical problems late.
2. Pure Scrum (score 3.10/5): Supports frequent feedback and technical experimentation but provides weaker control over fixed approval gates, budget and deadlines.
3. Hybrid (score 4.30/5): Combines a predictive scope, schedule and budget baseline with four Agile sprints, regular demonstrations and formal phase gates.

## Decision

Choose the Hybrid life cycle, subject to sponsor approval at G1.

The two strongest reasons are:

1. It provides formal planning and governance to protect the Week 3 plan approval, $200 budget and Week 14 pilot deadline.
2. It allows iterative development and early technical testing to manage WebSocket uncertainty and deliver a working quiz before the Week 7 MVP checkpoint.

## Consequences

### Positive consequences

- The sponsor receives a clear project plan, budget and schedule before development begins.
- Sprint reviews provide regular feedback and opportunities to improve the quiz.
- Early testing reduces the risk of discovering performance and synchronization problems near the pilot.

### Negative consequences and mitigations

- Combining predictive planning with Agile sprints requires additional coordination. -> Mitigation: Use one integrated schedule and a short weekly PM coordination meeting.
- Formal phase gates may delay decisions. -> Mitigation: Set review dates in advance and agree on a maximum two-working-day decision period.
- Junior developers may struggle with sprint estimation and technical implementation. -> Mitigation: Keep sprint goals small, conduct code reviews and reserve contingency time for technical issues.

## Tailoring

| Keep from predictive                                                                                 | Keep from agile                                                                              | Drop                                                                                                    |
| ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| WBS to level 2: needed for the scope baseline and work ownership.                                    | Product backlog: allows detailed requirements to be refined during development.              | Detailed upfront UI specifications: screens and interactions need user feedback before being finalized. |
| Baseline schedule and $200 budget: needed to control the fixed Week 14 deadline and cash cap.        | Two-week sprints: provide regular delivery and technical feedback.                           | Daily sponsor approval: the sponsor is only needed at reviews and formal decision points.               |
| Four formal phase gates: needed for measurable sponsor decisions and project control.                | Sprint reviews and retrospectives: support inspection, feedback and continuous improvement.  | Large upfront technical design: WebSocket performance must be tested through working prototypes.        |
| Change control for Must requirements: protects the agreed scope and prevents uncontrolled expansion. | Sprint planning and backlog prioritization: allow the team to adapt lower-priority features. | Separate predictive and Agile schedules: one integrated schedule avoids conflicting plans.              |

## Phase gates

| Gate | Week and date        | Evidence required                                                                                                  | Decision maker                  | Possible outcomes                                |
| ---- | -------------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------- | ------------------------------------------------ |
| G1   | Week 3 / 2026-10-19  | Approved charter and scope baseline; WBS and 14-week schedule completed; budget estimate within $200.              | Sponsor (Head of IT Department) | Continue / continue with changes / stop / repeat |
| G2   | Week 7 / 2026-11-16  | Working MVP demonstrated; core Must features tested; WebSocket prototype latency and timer drift results recorded. | Sponsor (Head of IT Department) | Continue / continue with changes / stop / repeat |
| G3   | Week 11 / 2026-12-14 | Release candidate passes functional tests; latency below 500 ms; timer drift below 200 ms; zero critical defects.  | Sponsor (Head of IT Department) | Continue / continue with changes / stop / repeat |
| G4   | Week 14 / 2027-01-04 | Pilot completed with 50 students; attendance and quiz completion results recorded; zero critical defects.          | Sponsor (Head of IT Department) | Continue / continue with changes / stop / repeat |
