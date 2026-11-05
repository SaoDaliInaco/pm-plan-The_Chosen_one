# Scrum setup · Realtime Quiz

## Roles
| Role | Person | Accountable for | Not responsible for |
|---|---|---|---|
| Product owner | Student A | Managing and prioritizing product backlog, defining acceptance criteria | Writing code architecture or assigning daily tasks |
| Scrum master | Student B | Facilitating Scrum events, removing blockers, coaching the team on Scrum practices | Managing the project budget or altering scope directly |
| Developers | Students A-D | Building increments, testing features, ensuring adherence to Definition of Done | Defining final business priorities or stakeholder agreements |
| Project manager | Supervising Lecturer | Overseeing stage gates, overall budget, stakeholder communications, and risk management | Direct management of daily sprint task execution |
| Sponsor | Head of IT Department | Funding approval, stage gate reviews, final product acceptance | Daily operational team decisions |

*Note on Product Owner dual role:* Student A acts as Product Owner while also participating as a developer. To limit conflicts of interest, backlog prioritization is strictly based on MoSCoW rankings from Lab-02, and technical implementation decisions are decoupled from priority assignments.

## Sprint goal (sprint 1, weeks 4-5)
Establish the foundational project skeleton with continuous integration, user authentication with roles, and basic quiz authoring capabilities.

## Event calendar · sprint 1 (2026-10-20 to 2026-11-02)
| Event | Date(s) | Time | Timebox | Attendees | Output |
|---|---|---|---|---|---|
| Sprint planning | Tue 2026-10-20 | 10:00 | 2 h | PO, SM, Devs | Sprint goal, Sprint backlog |
| Daily scrum | Mon-Fri (10 days) | 09:00 | 15 min | Devs, SM | Updated daily plan and blockers resolved |
| Backlog refinement | Wed 2026-10-28 | 14:00 | 1 h | PO, Devs | Refined and estimated future backlog items |
| Sprint review | Mon 2026-11-02 | 14:00 | 1 h | Team, PM, Sponsor | Incremental product demo and stakeholder feedback |
| Sprint retrospective | Mon 2026-11-02 | 15:15 | 45 min | PO, SM, Devs | Process improvements and actionable team retro items |

## Definition of ready
1. Item is mapped to at least one Functional Requirement ID (`FR-xx`).
2. Item has clear acceptance criteria written in Given/When/Then format.
3. Item is estimated using Fibonacci points (maximum 8 points).
4. Technical dependencies and required data models are identified.
5. User interface expectations or wireframe sketches are attached if applicable.

## Definition of done
1. Code compiles successfully without errors or warnings.
2. Unit tests pass locally and in the automated CI pipeline.
3. Line coverage of new service code meets or exceeds 80% in JaCoCo reports.
4. Peer code review completed and approved by at least one other developer.
5. API endpoints are documented (e.g., Swagger/OpenAPI) and verified.
6. Feature conforms to WCAG AA contrast and basic accessibility guidelines.
7. Tested successfully across desktop and mobile viewport resolutions.
8. No high-severity security vulnerabilities or unmanaged secrets committed.

Planning velocity: 30 points · Capacity: 4 students × 10 h/week × 2 weeks = 80 hours total.