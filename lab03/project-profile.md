# Project profile · Realtime Quiz

Sources: [charter](../lab01/project-charter.md), [MoSCoW list](../lab02/moscow-list.md)

| # | Criterion                            | Evidence (one fact) | Weight | Score 1-5 | W x S |
|---|--------------------------------------|---------------------|-------:|----------:|------:|
| 1 | Requirements stability               | 8 Must features fixed in charter accounting for 300 h (59.5% effort), but UI screens, question flows, and real-time interaction details are emergent | 25 | 3 | 75 |
| 2 | Technical uncertainty                | Real-time WebSocket broadcasting (F05) requires sub-500 ms latency and < 200 ms timer drift across 50 concurrent students on a single 2 GB RAM VPS with potential campus proxy blocks | 25 | 4 | 100 |
| 3 | Team experience with agile           | Student team of 4 junior developers has basic classroom Agile/Scrum knowledge but no prior commercial production experience delivering high-concurrency systems | 15 | 3 | 45 |
| 4 | Contract and governance constraints  | Sponsor mandates fixed schedule (approved PM plan in week 3, pilot in week 14) and fixed cash cap ($200); internal project with no external commercial contract penalty | 20 | 2 | 40 |
| 5 | Need for early delivery and feedback | Charter specifies early working MVP demo in week 7 and bi-weekly iterative validation to de-risk live pilot with 50 students in week 14 | 15 | 4 | 60 |
|   | **Profile** = SUM(W x S) / 100       |                     |    100 |           | **3.2** |
| 6 | (optional) Sponsor availability      | Sponsor (Head of IT Department) is on-campus and available for bi-weekly milestone reviews and sprint demos, but day-to-day decisions are delegated to the PM |      - |         4 |     - |

Score 1-5: 1 = the fact favours predictive, 5 = it favours adaptive.

Interpretation: < 2.5 predictive · 2.5-3.5 hybrid · > 3.5 agile

## Profile summary
The Realtime Quiz project has a fixed feature list and strict external milestone deadlines, but it faces substantial technical uncertainty regarding real-time WebSocket synchronization under campus network conditions. The two dominating criteria are Requirements stability (weight 25, score 3) and Technical uncertainty (weight 25, score 4), yielding an overall profile score of 3.2 which places the project firmly in the hybrid band. Task 2 must therefore compare predictive (Waterfall), adaptive (Scrum), and tailored hybrid approaches as candidate families.
