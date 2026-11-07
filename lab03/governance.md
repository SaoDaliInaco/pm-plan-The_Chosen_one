# Governance · Realtime Quiz hybrid life cycle

## Stage gates
### G1 · Plan approved · end of week 3 (2026-10-19)
- [ ] Project charter and high-level scope signed by sponsor (evidence: `lab01/project-charter.md`)[cite: 5]
- [ ] WBS and schedule baseline established (evidence: Lab-04 plan files)[cite: 5]
- [ ] Budget capacity and cash limits verified (evidence: `business-case.md`)[cite: 5]
- [ ] Risk register initialized with top 5 risks (evidence: Lab-09 risk register)[cite: 5]
- [ ] Methodology decision record accepted (evidence: `lab03/tailoring-decision-record.md`)[cite: 5]
**Inputs:** Charter, scope statement, WBS, milestone schedule, budget summary.  
**Decision maker:** Sponsor (Head of IT Department).  
**Outcomes:** Continue / Continue with changes / Stop / Repeat.

### G2 · MVP checkpoint · end of week 7 (2026-11-16)
- [ ] All Must features operational and verified against DoD (evidence: Sprint 4 review report)[cite: 5]
- [ ] Line coverage >= 80% on core services (evidence: JaCoCo report in CI)[cite: 5]
- [ ] WebSocket connection stability verified under basic load (evidence: test logs)[cite: 5]
- [ ] Zero unmitigated high-priority risks active (evidence: risk register review)[cite: 5]
- [ ] Hours expenditure within 5% of planned baseline (evidence: timesheet report)[cite: 5]
**Inputs:** Sprint reviews 1-4, test reports, risk register.  
**Decision maker:** Sponsor and Project Manager.  
**Outcomes:** Continue / Continue with changes / Stop / Repeat.

### G3 · Release candidate · end of week 11 (2026-12-14)
- [ ] All Must and at least 80% of Should items meet the DoD (evidence: backlog export)[cite: 5]
- [ ] Line coverage >= 80% on service and realtime packages (evidence: JaCoCo report in CI)[cite: 5]
- [ ] Load test with 100 simulated students passed with p95 broadcast latency < 500 ms (evidence: load test report)[cite: 5]
- [ ] Security checklist signed off with no exposed secrets in repository (evidence: security audit file)[cite: 5]
- [ ] Total hours used <= 90% of 560-hour capacity budget (evidence: project hours tracker)[cite: 5]
**Inputs:** Sprint review notes, CI pipeline reports, load test results, security checklist.  
**Decision maker:** Sponsor with Project Manager.  
**Outcomes:** Continue / Continue with changes / Stop / Repeat.

### G4 · Acceptance and closure · week 14 (2027-01-04)
- [ ] Student pilot with 50 participants completed successfully (evidence: pilot evaluation report)[cite: 5]
- [ ] Production deployment runbook handed to IT Operations (evidence: signed hand-over form)[cite: 5]
- [ ] Post-project lessons learned workshop completed (evidence: retro summary document)[cite: 5]
- [ ] Financial and administrative sign-off achieved within cap (evidence: closure sign-off memo)[cite: 5]
- [ ] Repository archived and tagged clean (evidence: GitHub release tag)[cite: 5]
**Inputs:** Pilot metrics report, operational runbook, lessons learned log.  
**Decision maker:** Sponsor.  
**Outcomes:** Project closure / Operational transition.

## Tolerances (manage by exception)
| Tolerance | Stage 1 (W1-3) | Stage 2 (W4-7) | Stage 3 (W8-11) | Stage 4 (W12-14) |
|---|---|---|---|---|
| Time | ± 3 days | ± 1 sprint (2 weeks) | ± 3 days | 0 days (Fixed Pilot Date) |
| Cost (hours) | ± 10% | ± 10% | ± 5% | 0% (No overtime in pilot week) |
| Scope | ± 5% backlog items | ± 10% Should features | ± 5% Should features | 0% Scope changes frozen |
| Quality | Code standards met | JaCoCo coverage ≥ 75% | JaCoCo coverage ≥ 80% | JaCoCo coverage ≥ 80% + zero blocker bugs |
| Risk | High risks identified | Mitigation owners assigned | Residual risks accepted | Contingency plans ready |

**Escalation path:** Developers → Scrum Master → Project Manager → Sponsor.  
**Exception trigger:** Any projected deviation exceeding the stage tolerances automatically triggers an immediate Exception Report to the Project Manager and Sponsor within 24 hours.

## Reporting
- **Weekly Highlight Report:** Submitted by the Project Manager every Friday, highlighting completed work, upcoming tasks, active risks, and current tolerance status.
- **Sprint Review Checkpoint:** Conducted every two weeks at the end of each sprint; serves as direct evidence collection for the Project Manager.
- **Exception Report Template:** Triggered upon tolerance breach, outlining: (1) Deviation details, (2) Viable recovery options with cost/time impacts, and (3) Explicit PM recommendation for sponsor decision.

## Closure criteria
| Area | Criterion | Verified by | Owner |
|---|---|---|---|
| Acceptance | Successful execution of 50-student live quiz pilot with zero critical bugs | Sponsor & IT Department | Project Manager |
| Hand-over | Clean repository release tag, production Docker config, and operational runbook delivered | IT Operations Lead | Lead Developer / DevOps |
| Lessons learned | Documented sprint retrospectives and final project review workshop summary | Project Team | Scrum Master |
| Administrative closure | Final project repository archive and course grade verification completed | Supervising Lecturer | Project Manager |