# Weighted scoring: build in-house, buy a SaaS quiz tool, or hybrid · Realtime Quiz

## Weights justification (agreed 2026-10-06, before scoring)

Weights (agreed 2026-10-06, before scoring): learning 40, cost 25, time 20, fit 15. Sum = 100.

1. **Learning value for the capstone (weight 40):** As a university Software Engineering capstone, pedagogical value in building full-stack distributed real-time systems is the primary objective of the course.
2. **Cost within the 200 USD cash budget (weight 25):** The 200 USD cash budget is strictly fixed by the department with no mechanism for additional funding, making low external spend essential.
3. **Time to the week-14 pilot (weight 20):** Delivering a working platform for the week-14 pilot is a non-negotiable semester milestone; schedule predictability is critical.
4. **Fit to the 47 functional requirements (weight 15):** The solution must fulfill the core functional requirements (FR-A1 through FR-N3) established in the charter baseline.

Sum check: 40 + 25 + 20 + 15 = 100.

---

## Option descriptions

- **Build (In-house):** The 4-student capstone team develops the application in-house over 14 weeks (504 h planned effort) on a Linode VPS (25 USD/month × 4 = 100 USD) and custom domain (15 USD), totaling 115 USD of the 200 USD cash budget.
- **Buy (SaaS Quiz Service):** Procure a commercial hosted quiz platform—specifically **Slido Pro** (quoted at 39 USD/month for up to 50 concurrent participants, totaling 156 USD across the 4-month semester, representing 78% of the cash budget).
- **Hybrid:** Procure a managed real-time WebSocket messaging layer (such as Ably / Pusher Channels student tier at 19 USD/month × 4 = 76 USD) while developing custom question authoring, authentication, score reporting, and exports in-house on our Linode VPS (100 USD), totaling 176 USD (88% of the cash budget).

---

## Scoring matrix

| Criterion | Weight | Build | Buy (SaaS) | Hybrid | Notes |
|:---|:---:|:---:|:---:|:---:|:---|
| Learning value for the capstone | 40 | 5 | 1 | 3 | Full SE lifecycle vs pure configuration vs custom front-end/reporting |
| Cost within the 200 USD cash budget | 25 | 4 | 3 | 3 | 115 USD spend vs 156 USD (Slido) vs 176 USD (Ably + VPS) |
| Time to the week-14 pilot | 20 | 3 | 5 | 4 | 14-week planned development vs immediate day-1 availability vs saving 48 h on WebSocket |
| Fit to the 47 functional requirements | 15 | 5 | 3 | 4 | 47/47 requirements tailored vs ~31/47 SaaS feature match vs ~42/47 custom fit |
| **Weighted score** | | **435** | **260** | **335** | `=SUMPRODUCT(weights, scores)` |
| **Percent of maximum (500)** | | **87 %** | **52 %** | **67 %** | `Score / (5 * 100)` |

---

## Score evidence

- **Learning value:**
  - *Build (5):* Maximum learning value; team designs architecture, real-time WebSocket communication, and database schemas.
  - *Buy (1):* Minimal learning value; configuration only, involving no meaningful software engineering implementation.
  - *Hybrid (3):* Moderate learning value; team builds user interface, authoring workflows, and data exports, but outsources distributed socket messaging.
- **Cost within 200 USD:**
  - *Build (4):* Linode VPS (100 USD) + domain (15 USD) = 115 USD, leaving an 85 USD (42.5%) reserve buffer.
  - *Buy (3):* Slido Pro costs 39 USD/month × 4 months = 156 USD, consuming 78% of the 200 USD cash budget and leaving only 44 USD.
  - *Hybrid (3):* Messaging service (76 USD) + VPS (100 USD) = 176 USD, consuming 88% of the 200 USD cash budget and leaving only 24 USD.
- **Time to week-14 pilot:**
  - *Build (3):* Demands 504 hours across 14 weeks with tight sprint timelines and an MVP checkpoint at week 7.
  - *Buy (5):* Commercially hosted system available immediately on day 1 with zero development lead time.
  - *Hybrid (4):* Offloading WebSocket synchronization saves 48 hours (F05), reducing schedule pressure and aiming for completion around week 11.
- **Fit to 47 functional requirements:**
  - *Build (5):* 100% bespoke coverage of all 47 functional requirements (FR-A1 through FR-N3).
  - *Buy (3):* Standard SaaS covers core live polling (~31 of 47 requirements), but lacks custom role workflows, specific LMS integration, and custom grading exports.
  - *Hybrid (4):* Covers approximately 42 of 47 requirements, allowing custom UI, grading logic, and reporting, with slight constraints imposed by third-party socket API limits.

---

## Hand calculations

- **Build:** `40 * 5 + 25 * 4 + 20 * 3 + 15 * 5 = 200 + 100 + 60 + 75 = 435` (87% of 500)
- **Buy (SaaS):** `40 * 1 + 25 * 3 + 20 * 5 + 15 * 3 = 40 + 75 + 100 + 45 = 260` (52% of 500)
- **Hybrid:** `40 * 3 + 25 * 3 + 20 * 4 + 15 * 4 = 120 + 75 + 80 + 60 = 335` (67% of 500)

---

## Sensitivity check

Shift 10 points of weight from the heaviest criterion (*Learning value*: 40 $\rightarrow$ 30) to the lightest criterion (*Fit to requirements*: 15 $\rightarrow$ 25).

New weights: Learning 30, Cost 25, Time 20, Fit 25 (Sum = 100).

- **Build:** `30 * 5 + 25 * 4 + 20 * 3 + 25 * 5 = 150 + 100 + 60 + 125 = 435`
- **Buy:** `30 * 1 + 25 * 3 + 20 * 5 + 25 * 3 = 30 + 75 + 100 + 75 = 280`
- **Hybrid:** `30 * 3 + 25 * 3 + 20 * 4 + 25 * 4 = 90 + 75 + 80 + 100 = 345`

**Conclusion:** The winner is **unchanged (Build)**. Even when pedagogical learning value is down-weighted in favor of functional fit, Build retains a dominant lead (435 vs Hybrid 345 vs Buy 280).
