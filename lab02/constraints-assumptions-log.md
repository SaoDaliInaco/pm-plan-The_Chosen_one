# Constraints and assumptions log · Realtime Quiz · v0.1 · week 2

| Id | Type | Statement (measurable) | Source / owner | Validate by |
|------|------------|---------------------------|----------------|-------------|
| C-01 | Constraint | Pilot go-live with 50 concurrent students must occur in week 14 (no later than 2026-12-22; revised to week 12 by dean's notice). | charter Section 4, Dean / Academic calendar | fixed |
| C-02 | Constraint | Team effort capacity is exactly 40 h/week (4 student developers × 10 h/week), providing 560 h across 14 weeks (or 480 h across 12 weeks). | charter Section 5, Supervising Lecturer (PM) | fixed |
| C-03 | Constraint | Total cash budget is strictly capped at 200 USD (Linode VPS 100 USD, domain 15 USD, dev tools 60 USD, reserve 25 USD) with zero additional funds. | charter Section 5 & 7, Head of IT Department (sponsor S01) | fixed |
| C-04 | Constraint | Platform must deploy on a single Linode VPS instance (2 vCPU, 2 GB RAM) with WebSocket broadcast latency <= 500 ms at 95th percentile. | charter Section 2 (O3, O4), IT Operations Admin (S06) | fixed |
| C-05 | Constraint | Student authentication (F06) and personal data storage must remain on campus-controlled infrastructure (gicitc.com) with zero external third-party data sharing. | stakeholder analysis S08, Data Protection Officer | fixed |
| A-01 | Assumption | Campus proxy and network firewall pass persistent WebSocket/STOMP traffic over ports 80/443 for 50 concurrent connections without dropping sessions. | owner: Campus Network Admin (S07) / PM | W3 -> R-01 |
| A-02 | Assumption | Backend WebSocket server memory consumption stays below 1.5 GB RAM and CPU below 70% under 20 concurrent sessions of 100 participants. | owner: Lead Backend Developer (S03) | W7 -> R-02 |
| A-03 | Assumption | Client browser system clocks synchronize via NTP with drift < 200 ms relative to server clock to maintain synchronized question timers (F07). | owner: Lead Frontend Developer (S03) | W6 -> R-03 |
| A-04 | Assumption | All 50 pilot participants have personal mobile or laptop devices running evergreen browsers (Chrome >= 115, Safari >= 16, Firefox >= 115). | owner: Pilot Coordinator / PM | W10 -> R-04 |
| A-05 | Assumption | Open-source PDF export library renders Khmer Unicode fonts (Khmer OS Battambang) without missing glyphs across all 50 student quiz reports (F11). | owner: Full-stack Developer (S03) | W8 -> R-05 |

Review at every milestone. Overdue assumption = open issue.
