# Designing Trustable Repeat Mobility: A Rapido Product Case Study for India's 15–25 Riders

*An independent product strategy case study prepared as a portfolio exercise, based entirely on publicly available information (app store listings, public financial reporting, and public safety documentation). This is not based on Rapido internal data and does not claim access to proprietary metrics.*

---

## Note on Method

Before proposing anything new, this case study first maps what Rapido's public app listings already confirm exists — bike taxis, autos, cabs, Bike Lite, Bike Metro, metro ticketing, favourites, live tracking, unique PIN, insurance, and helmets for bike-taxi riders. Where a claim below is treated as a "gap," it is a gap in *orchestration or quality*, not in whether the base capability is present. Where a number or figure is used, its source is cited; where no public source exists, it is explicitly flagged as an assumption.

---

## 1. Strategic Lens, Assumptions, and Method

**Strategic lens:** This case study treats Rapido not as a single-rider convenience app but as a two-sided marketplace. Any feature proposed here is evaluated on whether it improves *both* the youth rider experience *and* a marketplace lever (captain idle time, cancellation rate, pickup accuracy) — because a feature that only helps riders while hurting captain economics is not viable at Rapido's stage.

**Key assumptions (explicitly flagged, not sourced):**
- Exact ride-frequency and churn figures for the 15–25 cohort are not public; directional reasoning is used instead of invented numbers.
- Persona names and quotes in journey maps are illustrative composites, not verbatim user research.
- Any metric target ("increase," "decrease") is a directional goal, not a committed number.

**Prioritisation method selected:** A weighted scoring model (User Impact 35%, Feasibility 25%, Business Impact 25%, Risk/Strategic Fit 15%) rather than RICE, because Reach is hard to estimate credibly without internal data, while Feasibility and marketplace-risk are the more decision-relevant axes for an external teardown.

**Why the final direction is promising:** The two problems with the clearest, most frequent, most verifiable evidence trail are pickup ambiguity at campuses/metro stations and helmet quality — both are called out indirectly in Rapido's own public materials (helmet provision claims, night-ride safety-check references) and in the structural nature of Indian campus/metro geography. They are also the two problems that are cheapest to pilot without regulatory exposure.

---

## 2. Executive Summary

Rapido has scaled bike-taxi, auto, and cab mobility across 500+ Indian cities and reports over 75 million customers and 1 million+ captains on its public app listings.<sup>[1]</sup> Financially, Rapido's FY25 operating revenue rose 44% to ₹934 crore with net loss narrowing to ₹258 crore, and MediaNama separately reported total revenue crossing ₹1,000 crore for the year.<sup>[2][3]</sup> Captain incentives remain reported as the company's largest cost line.<sup>[3]</sup>

India's population skews young — government sources cite roughly 65% under age 35<sup>[4]</sup> — making the 15–25 cohort strategically significant: high trip frequency (college, coaching, metro last-mile, hostel travel), but also highly price-sensitive and quick to switch apps under friction.

**Core user problem:** Rapido's booking flow is optimised for a single, anonymous point-to-point ride. Youth mobility, by contrast, is repetitive, budget-constrained, socially coordinated, and safety-sensitive — and the app does not yet orchestrate for that pattern.

**Core business problem:** Because captain incentive costs are already the largest expense line, Rapido cannot win this segment through discounting. It must win through lower friction and higher trust per ride, which simultaneously improves marketplace efficiency (fewer cancellations, less captain idle time).

**Final recommendation:** A youth-focused reliability layer — **Campus & Metro Pickup Zones**, paired with a **Helmet Quality Feedback Loop** and **Saved Route Cards** — rather than a broad "Gen Z social" feature. These are the highest-frequency failure points with the lowest regulatory and marketplace risk, and they compound into a longer-term **Night Safety Mode** for trust-building among young women and guardians.

**Expected impact:** Directionally, this should reduce pickup-related cancellations and calls, improve perceived helmet/safety trust (relevant given past regulatory scrutiny of bike-taxi safety in Karnataka<sup>[5]</sup>), and convert repeat student routes into booking habits — all without relying on discounting.

---

## 3. Company and Market Context

### Facts
- Rapido's public listings describe presence across 500+ cities with 75M+ customers and 1M+ captains.<sup>[1]</sup>
- FY25 operating revenue grew 44% YoY to ₹934 crore; net loss narrowed ~30% to ₹258 crore.<sup>[2]</sup>
- Rapido uses a commission model for bike taxis and a subscription model for autos/cabs, with subscription revenue growing sharply.<sup>[2]</sup>
- Captain incentives are reported as the largest cost category.<sup>[3]</sup>
- Karnataka's bike-taxi ban and related litigation cited safety and regulatory-framework concerns, illustrating that bike-taxi availability is not uniform or guaranteed across states.<sup>[5]</sup>

### Assumptions
- Direct market-share figures versus Ola, Uber, and Namma Yatri for the 15–25 cohort specifically are not public and are not estimated here.
- Youth users are assumed to be more price-sensitive and more likely to compare apps than the general rider base — this is a reasonable inference from India's youth-heavy, cost-conscious demographic profile, not a sourced statistic.

### Strategic implications
- Rapido's affordability position is already a competitive asset; the opportunity is not "make it cheaper" but "make repeat use more reliable and trustworthy," which protects margins.
- Any bike-taxi-only feature carries state-level regulatory exposure and should degrade gracefully to auto/cab/metro alternatives.

---

## 4. Target User Segment: 15–25-Year-Olds

| Segment | Age Range | Context | Key Needs | Pain Points | Product Opportunity |
|---|---:|---|---|---|---|
| School students | 15–18 | Coaching, school, activities | Guardian confidence, predictability | Low independence, parental anxiety | Guardian-aware safety framing (not a full guardian control system — see risks) |
| College students | 18–22 | Daily commute, hangouts | Affordability, speed, low friction | Price sensitivity, pickup confusion | Route habit tools, pickup precision |
| Interns / first earners | 20–25 | Office/internship commute | Punctuality, predictability | Surge pricing, delays | Commute-route reliability tools |
| Young women riders | 15–25 | Education, work, social travel | Safety, verified pickup, trip sharing | Night-travel anxiety | Proactive (not reactive) safety surfacing |
| Late-evening users | 18–25 | Coaching, work shifts, social outings | Supply availability, safety confidence | Low late-night supply, unsafe waiting | Night Safe Mode |

Note: Rapido's public safety documentation already references a night-time (10 pm–6 am) post-ride contact process and an SOS button.<sup>[6]</sup> The opportunity is not to invent safety tooling from zero, but to move existing reactive tools earlier in the journey, where anxiety is highest — before and during the ride rather than only after.

---

## 5. App Experience Analysis (Existing Capability vs. Youth Friction)

| Stage | User Goal | Existing Rapido Capability | Friction for 15–25 | Business Impact | Opportunity |
|---|---|---|---|---|---|
| Discovery | Find a low-cost ride app | High download volume, brand familiarity<sup>[1]</sup> | Low — trust is already high | Low acquisition cost | No change needed |
| Onboarding | Fast login | One-click phone login<sup>[7]</sup> | Low | Retained | No change needed |
| First booking | Enter pickup/drop | Core booking flow, favourites<sup>[1]</sup> | Campus/metro pickup points are imprecise | Cancellations, calls to captain | Pickup micro-zones |
| Pickup | Meet captain | Live tracking, unique PIN<sup>[1]</sup> | Crowded gates/exits cause confusion | Delay, frustration | Landmark-based pickup pins |
| Ride | Travel safely | Insurance, helmet provision claimed<sup>[1]</sup> | Helmet hygiene/fit not user-rated | Trust erosion, repeat-use drop | Helmet condition feedback |
| Payment | Pay quickly | UPI, wallet, cashless options<sup>[7]</sup> | No visibility into monthly spend | N/A — support feature only | Optional spend summary |
| Post-ride | Rate, resolve issues | General rating, night safety check<sup>[6]</sup> | Feedback is generic, not youth-specific | Missed signal on recurring issues | Add helmet/pickup-specific feedback categories |
| Rebooking | Repeat same trip | Favourites (saved *places*)<sup>[1]</sup> | No saved *route* object | Missed habit-formation opportunity | Saved Route Cards |

---

## 6. Real-World Ride Experience

Public app-store reviews (anecdotal, not statistically representative, but directionally consistent) surface recurring themes: pickup confusion at ambiguous points, captain reluctance to accept without added fare, and occasional cash-only requests.<sup>[1]</sup> These offline moments matter disproportionately for young riders because:

- A confused pickup at a crowded metro exit or coaching-centre lane creates visible, public anxiety, especially for younger or first-time riders.
- Helmet quality is a physical trust signal in a way software cannot fully compensate for — if the app promises safety but the physical helmet feels unhygienic or loose, that promise visibly breaks.
- Parents/guardians of the 15–18 sub-segment are not present during the ride; their confidence is built entirely on secondhand accounts of these offline moments (word-of-mouth), making offline reliability a de facto retention lever even though it happens outside the app.

---

## 7. Problem Discovery

**Problem 1 — Campus and metro pickup ambiguity**
Pain: "College gate" or "metro exit" is not one point; it maps to multiple physical gates, hostel entries, and platform exits.
Triggers: Real-world campus geography (offline) + generic pin-drop UX (app).
Business impact: Cancellations, wasted captain time, poor ETA reliability.
Affected: Rider, captain, platform.
Why now: This is a daily, high-frequency failure — not an edge case — for any student user.

**Problem 2 — Helmet quality is claimed but not measured**
Pain: Helmets are promised in Rapido's own listings,<sup>[1]</sup> but there is no visible mechanism to rate or enforce their condition.
Triggers: Physical hygiene/fit (offline) + no dedicated feedback field (app).
Business impact: Repeat-use erosion, safety-perception risk — amplified by past regulatory scrutiny of bike-taxi safety.<sup>[5]</sup>
Affected: Rider, captain, platform, regulators indirectly.
Why now: Regulatory sensitivity around bike-taxi safety makes this a proactive-trust issue, not just a comfort issue.

**Problem 3 — Repeat-route friction**
Pain: Favourites save places, not full route intent (mode, cost expectation, timing).
Business impact: Missed habit formation, higher cost-per-repeat-booking effort.
Affected: Rider, platform.

**Problem 4 — Fare/acceptance uncertainty**
Pain: Anecdotal reviews reference added-fare or cash-only requests before acceptance.<sup>[1]</sup>
Business impact: Erodes the "affordable and reliable" positioning for the most price-sensitive segment.
Affected: Rider, captain (reputational), platform.

**Problem 5 — Late-evening safety is reactive**
Pain: Rapido's own safety documentation frames night contact as a *post-ride* check.<sup>[6]</sup> Anxiety, however, peaks *before and during* the ride.
Business impact: Suppresses adoption among young women, minors, and guardians who influence their decisions.
Affected: Rider, guardian, platform.

**Problem 6 — Group/social travel is not owned by the platform**
Pain: Friends coordinate rides and split costs manually outside the app (e.g., via chat apps).
Business impact: Rapido loses visibility into a common youth travel pattern; Uber India's public Group Rides and fare-split feature<sup>[8]</sup> shows this is a validated pattern elsewhere, though Rapido's bike-first mode makes direct replication non-trivial and lower priority here.

---

## 8. User Journey Map (Representative Persona)

**Persona:** A 19-year-old college student booking Rapido from a metro station to her college gate on a weekday morning.

| Stage | User Action | User Thought | Pain Point | Emotional State | App Touchpoint | Offline Touchpoint | Opportunity |
|---|---|---|---|---|---|---|---|
| Exit metro | Opens app | "Where do I even mark pickup?" | Vague pin location | Mildly anxious | Map pin | Crowded exit gate | Pickup micro-zones |
| Book ride | Selects mode | "Is bike or auto cheaper today?" | Re-evaluates cost every time | Neutral | Fare comparison screen | N/A | Route-level cost memory |
| Wait | Waits for captain | "Will he find me?" | Calls needed to clarify location | Slightly stressed | Live tracking | Standing at ambiguous spot | Landmark pickup pin |
| Ride starts | Wears helmet | "This helmet smells." | No way to flag it separately | Discomfort | Generic rating (post-ride only) | Physical helmet condition | Helmet feedback field |
| Arrival | Reaches college | "That was fine, but tiring to plan." | No memory of this being a routine trip | Relief, mild fatigue | Ride ends, no route saved | Walks into campus | Saved Route Card prompt |

---

## 9. Feature Opportunity Exploration

### Feature 1: Campus & Metro Pickup Zones
- **Problem solved:** Pickup ambiguity at high-density youth locations.
- **Segment:** College students, school students, metro commuters.
- **In-app component:** Pre-mapped landmark pickup/drop points per campus/station, shown before booking.
- **Offline component:** Physical signage or platform-side coordination with a small number of high-traffic campuses/stations (pilot-only, not day-one requirement).
- **Business impact:** Fewer cancellations, lower captain idle time, better ETA accuracy.
- **Complexity:** Medium — requires manual zone-mapping for a limited pilot set of locations, not real-time detection.
- **Risks:** Zone data goes stale if campus layouts change; requires periodic refresh.

### Feature 2: Helmet Quality Feedback Loop
- **Problem solved:** Helmet hygiene/fit is claimed but unmeasured.
- **Segment:** All bike-taxi riders, especially first-time and youth riders.
- **In-app component:** A separate post-ride rating field ("Clean / Okay / Smelly / Damaged / Not provided") distinct from the general star rating.
- **Offline component:** Low-scoring captains flagged for a helmet check or replacement; optional disposable hygiene liners in high-frequency zones.
- **Business impact:** Restores trust in a publicly-claimed safety feature; useful defensive data point given regulatory scrutiny history.<sup>[5]</sup>
- **Complexity:** Low for the feedback field; medium for the operational audit/replacement loop.
- **Risks:** Requires operational follow-through — a feedback field with no consequence is worse than none, since it signals the issue was heard and ignored.

### Feature 3: Saved Route Cards
- **Problem solved:** Favourites save places, not full repeat-route intent.
- **Segment:** Students and interns with fixed daily routes.
- **In-app component:** After 3 repeat trips on the same origin-destination pair, prompt to save as a "Route Card" showing usual time, fare range, and a one-tap "book usual."
- **Offline component:** None required — purely an app-side habit tool.
- **Business impact:** Reduces booking friction, increases repeat-use frequency.
- **Complexity:** Low-medium — pattern detection on existing ride-history data.
- **Risks:** Minimal; mainly a UX/notification-fatigue risk if over-prompted.

### Feature 4: Night Safety Mode (proactive, not just post-ride)
- **Problem solved:** Existing night-safety tooling is reactive (post-ride contact).<sup>[6]</sup>
- **Segment:** Young women riders, late-evening users, minors (with caution — see risks below).
- **In-app component:** For rides booked after a set evening hour from campus/coaching hubs, proactively surface trip-sharing with a chosen contact *before* the ride starts, not only after.
- **Offline component:** None required beyond existing SOS infrastructure.
- **Business impact:** Directly targets the segment most likely to be adoption-blocked by safety concerns (young women, guardians of minors).
- **Complexity:** Medium — mostly a sequencing/timing change to existing safety features rather than new infrastructure.
- **Risks:** Notification fatigue if triggered too broadly; must remain opt-in to avoid feeling paternalistic to adult riders.

### Feature 5: Captain Acceptance Quality Reporting
- **Problem solved:** Anecdotal reports of forced cancellations or added-fare requests.<sup>[1]</sup>
- **Segment:** All price-sensitive riders, especially youth.
- **In-app component:** A fast, structured post-cancellation reason field ("Captain asked me to cancel," "Asked for extra fare," etc.), rather than open-text feedback.
- **Offline component:** None directly; feeds into captain-side quality scoring.
- **Business impact:** Distinguishes genuine supply-demand mismatch from marketplace misbehaviour, protecting the affordability promise.
- **Complexity:** Medium — requires backend scoring logic and careful captain-side fairness design.
- **Risks:** Risk of false or retaliatory reports; needs a fair, evidence-weighted scoring approach rather than blunt penalties.

*(A sixth idea — guardian-linked controls for under-18 riders — was considered but deprioritised here; see Section 11 and Risks for why.)*

---

## 10. Feature Prioritisation

**Method:** Weighted scoring (User Impact 35%, Feasibility 25%, Business Impact 25%, Risk/Strategic Fit 15%), each scored 1–5. This method was chosen over RICE because "Reach" cannot be credibly estimated without internal data, while feasibility and regulatory/marketplace risk are the more decision-critical variables for an external teardown.

| Feature | User Impact | Feasibility | Business Impact | Risk/Fit | Score | Rationale |
|---|---:|---:|---:|---:|---:|---|
| Campus & Metro Pickup Zones | 5.0 | 4.5 | 4.5 | 5.0 | **4.75** | Highest-frequency, lowest-risk fix; no regulatory exposure |
| Helmet Quality Feedback Loop | 5.0 | 4.0 | 4.0 | 5.0 | **4.50** | Directly reinforces an existing but unaudited safety claim |
| Saved Route Cards | 4.8 | 4.2 | 4.5 | 4.5 | **4.55** | Strong habit-formation lever, low build complexity |
| Night Safety Mode (proactive) | 4.8 | 3.7 | 4.0 | 5.0 | **4.33** | High trust value; sequencing change more than new infra |
| Captain Acceptance Quality Reporting | 4.5 | 3.6 | 4.4 | 4.3 | **4.24** | Marketplace-critical but needs careful fairness design |

**Top three selected for MVP:** Campus & Metro Pickup Zones, Helmet Quality Feedback Loop, Saved Route Cards — the highest-frequency, lowest-regulatory-risk problems, forming a coherent "reliability layer" rather than a scattered feature list.

---

## 11. Final Feature Recommendation

**Feature name:** Rapido Campus Routes + Helmet Trust Layer

**One-line pitch:** Make daily student and youth mobility faster, safer, and more predictable by fixing pickup precision and helmet trust — without relying on discounting.

**Target segment:** College and school students, metro-dependent commuters, and — as a secondary beneficiary — young women and guardians who gain confidence from a visibly more reliable and hygienic experience.

**Core user problem:** Every trip, however routine, is treated by the app as a first-time booking — vague pickup point, unmeasured helmet quality, no memory of the route.

**Core business problem:** Captain incentive costs already dominate Rapido's cost base,<sup>[3]</sup> so youth retention must come from friction reduction and trust-building, not price cuts.

**Why this matters for 15–25-year-olds:** These are the exact friction points this segment hits daily — campus gates, metro exits, and physical safety comfort — and they are the moments most likely to generate negative word-of-mouth among a highly connected, socially networked age group.

**Why it fits Rapido:** It builds directly on infrastructure Rapido already has (favourites, live tracking, helmet provision, night safety check) rather than requiring new regulatory-sensitive capability like bike-pooling or full guardian-control systems.

**Why it beats alternatives considered:** A broad "Guardian Circle" or full parental-control system was considered (see Document draft direction) but was deprioritised as the *first* MVP because it introduces meaningful privacy, consent, and compliance complexity for a segment (under-18 users) that requires careful legal review — better suited to a later phase after the core reliability layer is validated.

---

## 12. Detailed Feature Concept

### Feature Name
Rapido Campus Routes + Helmet Trust Layer

### One-Line Pitch
A youth-mobility reliability layer that fixes pickup precision, measures helmet trust, and turns repeat student routes into one-tap habits.

### User Problem
Functionally: pickup is imprecise, helmet condition is invisible, and every repeat trip requires re-planning. Emotionally: this creates low-grade daily anxiety and erodes confidence in an otherwise trusted brand.

### Business Problem
Retention and repeat-frequency among a high-volume, low-margin segment cannot be won with discounts given existing cost structure;<sup>[3]</sup> it must be won with reliability.

### Target Users
**Primary:** College/school students, metro-dependent commuters, first-time riders.
**Secondary:** Young women riders (via the helmet-trust and eventual night-mode extension), captains (via reduced pickup-call time), Rapido support teams (via reduced ambiguous-complaint volume).

### Core Feature Components — App Side
- Pre-mapped pickup/drop micro-zones for a pilot set of campuses/metro stations
- Separate helmet-condition feedback field, distinct from overall ride rating
- Saved Route Cards after repeat-trip detection, with one-tap rebooking

### Core Feature Components — Real-World Side
- Landmark-based pickup guidance shown to both rider and captain
- Helmet audit/replacement trigger for captains with recurring low helmet scores
- Optional low-cost hygiene liners in the highest-frequency pilot zones

---

## 13. Core User Journey for the Final Feature

| Step | User Action | App Response | Offline Experience | Trust Impact | Business Value |
|---|---|---|---|---|---|
| 1 | Opens app near campus/metro | Detects known micro-zone location | N/A | Neutral | Sets up precision |
| 2 | Selects destination | Shows named pickup zones (e.g., "Main Gate," "Library Road") instead of a generic pin | Physically stands at a named, known point | Reduces ambiguity | Fewer cancellations |
| 3 | Confirms booking | Sends exact landmark to captain | N/A | Builds confidence | Faster captain navigation |
| 4 | Captain arrives | Live tracking + landmark match | Clear, quick pickup | Increases trust | Lower idle time |
| 5 | Rides | N/A | Wears helmet | Neutral-to-negative if poor condition | N/A |
| 6 | Ends ride | Prompts separate helmet-condition rating | N/A | Signals the issue is heard | Data for captain audit |
| 7 | Repeats trip 3x | Prompts "Save as Route Card?" | N/A | Builds habit | Higher repeat-booking rate |
| 8 | Books again later | One-tap "Book usual" | N/A | Convenience, reduced fatigue | Shorter time-to-booking |

---

## 14. Mini PRD

### Objective
Reduce pickup-related friction and improve helmet-trust perception for the 15–25 rider segment, converting repeat trips into app-native habits.

### Goals
- Reduce pickup-related cancellations and support calls in pilot zones.
- Establish a measurable helmet-quality signal tied to captain-side action.
- Increase repeat-route booking rate via Saved Route Cards.

### Non-Goals
- Full guardian-control or parental-approval system (deferred to a later phase pending legal review).
- Real-time group-ride fare splitting (deprioritised; lower frequency, higher build complexity for a bike-first platform).
- Any feature that requires new bike-taxi regulatory approval in restricted states.

### User Stories
- *As a student rider*, I want to select a named pickup zone at my campus so my captain finds me without a phone call.
- *As a young woman rider*, I want to rate helmet hygiene separately so recurring issues are visible to the platform, not buried in a generic rating.
- *As a captain*, I want a clear landmark instead of a raw GPS pin so I spend less time searching for riders.
- *As a support team member*, I want structured helmet-feedback data so I can trigger audits without relying on open-text complaints.

### Functional Requirements
- Pickup/drop zone mapping for a defined pilot set of locations.
- Separate helmet-condition feedback field at ride completion.
- Route-repeat detection and Saved Route Card prompt after a defined threshold (e.g., 3 matching trips).
- Backend flagging for captains below a minimum helmet score.

### Non-Functional Requirements
- Low added latency at booking (zone selection should not slow the existing flow).
- Regional language support for zone labels and feedback prompts.
- Minimal data/battery overhead — no new background tracking required beyond existing live-tracking infrastructure.

### Edge Cases
- Campus/station layout changes and zone data goes stale — needs a periodic review cadence.
- Rider selects a zone but stands elsewhere — pickup guidance should degrade gracefully to standard pin-drop.
- Captain disputes a low helmet score — needs an appeal/review path to keep the system fair.
- Rider skips the helmet feedback prompt — should not block ride completion.

### Dependencies
- Existing maps/location infrastructure.
- Existing notification and post-ride feedback systems.
- Support/operations team bandwidth for helmet-audit follow-through.
- Legal review before any future guardian-linked expansion.

### Launch Plan
- **MVP:** Pilot in a small number of campuses/metro stations in 1–2 cities; helmet feedback field rolled out platform-wide (low build cost, high signal value).
- **Pilot expansion:** Add Saved Route Cards; expand pickup zones to more campuses based on pilot cancellation-rate data.
- **Scale:** Broaden to more cities; evaluate Night Safety Mode as a follow-on once the reliability layer is validated.

---

## 15. Success Metrics

### North Star Metric
**Repeat-route booking rate among 15–25 riders** — a direct signal that the app is being trusted for daily, habitual use rather than one-off trips.

### Input Metrics
- Pickup-zone selection rate (adoption of the new UX)
- Helmet-feedback submission rate
- Saved Route Card creation rate

### Output Metrics
- Pickup-related cancellation rate (directional decrease expected)
- Repeat ride rate among student/youth cohort
- Helmet-complaint rate per 1,000 bike rides (directional decrease expected)

### Guardrail Metrics
- Booking-flow conversion (zone selection must not add friction that reduces completed bookings)
- Captain dispute/appeal volume on helmet scoring (should stay low, indicating fairness)
- Support escalation volume (should not spike from the new feedback channel)

*(All target directions above are goals for a pilot to validate, not committed figures — no internal baseline data is available externally.)*

---

## 16. Experimentation Plan

**Hypothesis:** Precise pickup zones and a dedicated helmet-feedback channel will reduce pickup-related cancellations and improve perceived safety/hygiene trust among student riders, without adding meaningful booking friction.

**Target city/segment:** A pilot in 1–2 cities with dense campus/metro clusters (e.g., Bengaluru or Hyderabad, given existing Bike Metro presence there<sup>[1]</sup>), focused on college students during peak commute windows.

**MVP test design:** Roll out pickup zones for a limited set of campuses/stations; A/B test bookings from those locations against a control group using standard pin-drop.

**Duration assumption:** 6–8 weeks, sufficient to capture weekday commute patterns and initial habit formation.

**Success criteria:** Directional reduction in pickup-related cancellations and support calls in the test group versus control, with no material drop in booking conversion.

**Failure criteria:** No measurable change in cancellation rate, or a conversion drop attributable to added zone-selection friction.

**Data to collect:** Cancellation reasons, time-to-pickup, helmet-feedback distribution, Route Card adoption.

**Iteration:** If successful, expand zone coverage and layer in Saved Route Cards; if not, revisit zone granularity or UX placement before wider rollout.

---

## 17. Business Justification

This feature set addresses the highest-frequency, best-evidenced friction points for the 15–25 segment while requiring no new regulatory approval and no discounting. Given that captain incentives are already the largest cost line,<sup>[3]</sup> a feature that reduces cancellations and captain idle time is not just a rider-experience improvement — it is a direct marketplace-efficiency gain. Improved helmet trust is also a reasonable hedge against renewed regulatory scrutiny of bike-taxi safety, given prior state-level action in this space.<sup>[5]</sup> The MVP is deliberately scoped to be low-complexity and reversible — pilotable in a small number of locations before any city-wide commitment — which keeps downside risk contained while the higher-complexity, higher-risk ideas (guardian controls, group fare-splitting) are deferred pending validation and legal review.

---

## 18. Risks and Trade-Offs

| Risk | Severity | Likelihood | Mitigation |
|---|---|---|---|
| Zone data goes stale as campuses/stations change | Medium | Medium | Periodic manual review cadence for pilot zones |
| Helmet feedback collected but not acted on operationally | High | Medium | Tie feedback directly to a captain-side audit/replacement trigger before launch, not after |
| Captain-side friction from helmet scoring (perceived as punitive) | Medium | Medium | Include an appeal/review path; use scoring as a coaching signal before penalisation |
| Added booking-flow steps reduce conversion | Medium | Low-Medium | A/B test zone selection against standard pin-drop before full rollout |
| Guardian/parental features (deferred) raise privacy and consent complexity for minors | High | N/A (deferred) | Explicitly out of MVP scope; requires dedicated legal review before any future phase |
| Low adoption if riders don't notice the new pickup-zone option | Low | Medium | Surface it prominently at booking, not buried in settings |

---

## 19. Roadmap

**Phase 1 — MVP (Reliability Layer):** Pickup/metro zone pilot in 1–2 cities; helmet-feedback field rolled out broadly; success gate: measurable reduction in pilot-zone cancellations with no conversion drop.

**Phase 2 — Habit Layer:** Saved Route Cards; expand pickup zones based on Phase 1 data; begin captain helmet-audit operational loop at scale; success gate: repeat-route booking rate shows directional improvement.

**Phase 3 — Trust Layer:** Evaluate proactive Night Safety Mode as a sequencing change to existing safety tooling; assess (with legal input) whether any guardian-facing extension is warranted for the under-18 sub-segment; success gate: validated demand signal from Phase 1–2 data before committing further engineering investment.

---

## 20. Closing Note

Rapido has already solved the hard problem of affordable, wide-reaching mobility. The opportunity for the 15–25 segment is not a flashy new product line — it is making the everyday, repeat parts of that experience feel precise, hygienic, and predictable. That is a smaller, more disciplined bet, but it is the one most consistent with Rapido's existing cost structure and marketplace constraints.

---

### Sources

1. Rapido — Google Play Store listing, "Rapido: Bike-Taxi, Auto & Cabs"
2. The Economic Times — "Rapido FY25 revenue jumps 44% to Rs 934 crore, loss narrows 30% to Rs 258 crore"
3. MediaNama — "Exclusive: Rapido Crosses Rs 1,000 Crore Revenue in FY25" (Jan 2026)
4. Press Information Bureau, Government of India — factsheet on youth demographics
5. The Economic Times — "Karnataka's ban on bike taxis: A timeline"
6. Rapido Safety Guidelines (public PDF)
7. Rapido — Apple App Store listing, "Rapido: Bike-Taxi, Auto & Cabs"
8. Uber — "Group Rides" and "How to Split Fare," Uber India public pages
