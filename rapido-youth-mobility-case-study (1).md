# Rapido Saved Routes: Product Teardown and Feature Proposal

## Overview

Rapido is a large Indian mobility marketplace offering bike, auto, and cab rides across 500+ cities. Its public app listing mentions 75M+ customers, 1M+ captains, and over one billion rides.

Rapido’s FY25 operating revenue grew 44% to ₹934 crore, while losses narrowed to ₹258 crore. Public reporting also indicates that captain incentives remain one of Rapido’s largest cost lines. This makes discount-led retention less attractive as a long-term strategy.

This case study focuses on **18–25-year-old riders**: college students, interns, coaching students, and first earners who often repeat the same routes.

> **Core thesis:** Rapido should make repeated rides faster instead of building a broad youth or social feature.

---

## Target User

| Segment | Context | Repeated Route Example |
|---|---|---|
| College student | Hostel, campus, food spots, coaching | Hostel lane → College department |
| Intern | Metro / PG to office commute | Metro station → Office gate |
| Coaching student | Daily coaching or exam prep | PG → Coaching centre |
| First earner | Work and home commute | Office → Home pickup point |

The MVP focuses on 18–25 users because this group can independently transact, has repeated mobility needs, and avoids the consent and guardian complexity of under-18 flows.

---

## Current User Journey

Example user: a 20-year-old student rushing to class.

Frequent route:

> “Next to Nath Paan Vala” → “Mechanical Engineering Dept, DTU”  
> Mode: Bike  
> Payment: UPI

### Existing Flow

| Step | User Action | Friction |
|---|---|---|
| 1 | Opens Rapido | Starts from scratch |
| 2 | Sets pickup | GPS does not capture “next to Nath Paan Vala” clearly |
| 3 | Sets destination | Drop may default to college gate, not department |
| 4 | Selects mode | Picks bike again |
| 5 | Confirms ride | No route-level memory |
| 6 | Captain arrives | Rider may explain same landmark again |
| 7 | Ride ends | Rider completes UPI / QR / amount confirmation |
| 8 | Next day | Repeats the same flow |

The problem is not discovery. The user already knows where they want to go.

The problem is repeated manual effort.

---

## Problem Discovery

### Problem 1: Repeated Routes Are Treated Like New Rides

Young riders often repeat the same trips several times a week. A saved location is not enough because a route has more context.

A useful repeated route includes:

- origin
- destination
- pickup note
- drop note
- preferred ride mode
- payment preference
- usual time context

Without this route-level memory, the user repeats the same setup every time.

---

### Problem 2: GPS Does Not Capture Human Pickup and Drop Context

A map pin can show approximate coordinates, but riders and captains often coordinate through local landmarks.

Examples:

- “Next to Nath Paan Vala”
- “Opposite the photocopy shop”
- “Near the side gate”
- “Mechanical Engineering Dept, not the main gate”

This matters because unclear pickup and drop context can increase calls, delays, cancellations, and rider frustration.

---

### Problem 3: Mode and Payment Choices Are Repetitive

Rapido already offers bike, auto, and cab rides. For repeat routes, the preferred mode is often predictable.

| Use Case | Likely Mode |
|---|---|
| Student rushing to class | Bike |
| Student returning with bags | Auto |
| Intern going to office | Bike |
| Weekend ride home | Auto / Cab |

Payment is also repetitive. A rider who usually pays by UPI should not need to manually repeat the same payment flow every time.

---

## Why This Feature Was Prioritised

The feature was evaluated using five filters.

| Criterion | Why It Matters |
|---|---|
| Frequency | Does this happen often for 18–25 riders? |
| Marketplace value | Does it help captains or platform efficiency too? |
| Feasibility | Can it be built with existing product primitives? |
| Strategic fit | Does it fit Rapido’s current ride-hailing surface? |
| Risk | Does it avoid heavy legal, regulatory, or operational complexity? |

### Prioritisation Matrix

| Opportunity | User Value | Business Value | Feasibility | Risk | Decision |
|---|---:|---:|---:|---:|---|
| Saved Routes | High | High | Medium | Low | Build first |
| Custom Pickup / Drop Tags | High | High | Medium | Low | Build first |
| Preferred Mode Memory | Medium-High | Medium | High | Low | Build first |
| UPI-First Payment | Medium-High | High | Medium | Medium | Build carefully |
| Group Rides | Medium | Unclear | Medium | Medium | Defer |
| Guardian Controls | Low for MVP | Unclear | Low | High | Defer |

**Saved Routes wins** because it solves a high-frequency problem without requiring a new ride category, physical infrastructure, or heavy policy review.

It also supports both sides of the marketplace:

- riders book faster
- captains get clearer route context
- payment closure becomes faster
- repeat usage becomes easier without discounts

---

## Proposed Feature: Saved Routes

**Saved Routes** lets users save frequent routes with custom pickup and drop tags, default ride mode, and preferred UPI payment.

### Example Saved Route Card

```text
College Morning Ride

Next to Nath Paan Vala
→ Mechanical Engineering Dept, DTU

Bike · UPI · Usually ₹45–₹60

[Book Now]
```

When the rider opens Rapido near the saved origin, Rapido can surface:

```text
You’re near “Next to Nath Paan Vala.”
Book your usual bike ride to Mechanical Engineering Dept?
```

The rider still confirms before booking.

---

## Core Components

### 1. Custom Route Tags

Users can save their own pickup and drop labels on top of GPS.

| Field | Saved Value |
|---|---|
| Route name | College Morning Ride |
| Pickup tag | Next to Nath Paan Vala |
| Drop tag | Mechanical Engineering Dept, DTU |
| Mode | Bike |
| Payment | UPI |

The captain receives both:

- map location
- rider-written pickup / drop note

This reduces repeated explanation.

---

### 2. Preferred Mode

The saved route remembers the user’s usual ride mode.

| Route | Default Mode |
|---|---|
| Hostel → College | Bike |
| College → Home | Auto |
| Office → PG | Bike |

The app should prefill the mode, not force it. The rider can change the ride mode before confirming.

---

### 3. UPI-First Payment

For saved routes, Rapido can preselect UPI and open the exact-fare payment flow at ride completion.

### Payment Flow

1. Ride ends.
2. Fare is calculated.
3. UPI payment flow opens for the exact amount.
4. Rider approves the payment.
5. Captain receives payment confirmation.

Payment should never happen without rider approval.

---

## MVP Scope

### Included

- Save route after completed ride
- Create route manually from Saved Routes
- Add custom pickup and drop tags
- Save default ride mode
- Save UPI as preferred payment method
- Show saved route card near saved origin
- Send custom tags to captain
- Trigger exact-fare UPI payment flow after ride
- Allow edit, delete, and fallback to normal booking

### Excluded

- Group rides
- Fare splitting
- Under-18 guardian flows
- New ride categories
- Automatic payment without approval
- New metro infrastructure
- Helmet-related features

---

## Execution Feasibility

This feature is feasible because it builds on existing ride-hailing primitives.

| Existing Primitive | Extension Needed |
|---|---|
| Ride history | Detect repeat origin-destination pairs |
| Saved locations | Save route-level intent |
| GPS / maps | Store route coordinates |
| Captain app | Display custom pickup / drop tags |
| Payment methods | Preselect UPI for saved route |
| Home screen cards | Surface saved route near origin |

### Moderate Complexity Areas

- repeat-route detection
- location-triggered surfacing
- payment fallback handling

### Simpler Build Areas

- custom tags
- preferred mode storage
- route card UI
- captain-side note display

---

## Success Metrics

### North Star Metric

**Repeat bookings through Saved Routes**

---

### Input Metrics

- Saved route creation rate
- Saved route reuse rate
- Custom tag completion rate
- Preferred mode save rate
- UPI preference save rate
- Saved route card click-through rate

---

### Output Metrics

- Decrease in time-to-booking
- Increase in repeat-route booking rate
- Decrease in rider-captain clarification calls
- Decrease in ride-end payment completion time
- Increase in repeat ride frequency among saved-route users

---

### Guardrail Metrics

- No drop in booking conversion
- No rise in accidental bookings
- No increase in UPI failures
- No increase in support tickets
- No increase in captain complaints about unclear notes

---

## Experiment Plan

### Hypothesis

If frequent 18–25 riders can save routes with pickup/drop tags, preferred mode, and UPI payment, then repeat bookings will become faster and more frequent without hurting booking conversion.

---

### Test Group

18–25 riders who have taken similar origin-destination trips at least 2–3 times in the last 14–30 days.

---

### Control Group

Users continue with the existing booking flow.

---

### Duration

6–8 weeks.

---

### Success Criteria

- Saved routes are reused
- Time-to-booking decreases
- Repeat-route bookings increase
- Payment completion time decreases
- Booking conversion does not drop

---

### Failure Criteria

- Users save routes but do not reuse them
- Route cards are dismissed often
- Accidental bookings increase
- UPI failures increase
- Captains find custom tags confusing

---

## Risk Assessment

| Risk | Severity | Mitigation |
|---|---:|---|
| Wrong route card appears | Medium | Trigger only when location confidence is high |
| Custom tag is unclear | Medium | Add examples and character limits |
| User forgets to update stale route | Medium | Prompt review after repeated manual edits |
| Captain ignores note | Medium | Show note prominently in captain app |
| UPI payment fails | Medium | Keep QR, cash, and alternate UPI fallback |
| User expects automatic payment | High | Make approval step explicit |
| Too many prompts annoy users | Medium | Trigger only after repeated route behaviour |

---

## Why This Fits Rapido

Rapido’s existing product already supports:

- ride history
- GPS-based pickup and drop
- multiple ride modes
- captain-side coordination
- digital payments

Saved Routes does not ask Rapido to become a different product. It improves the repeat-use layer of the existing ride-hailing journey.

| Rider Benefit | Captain / Marketplace Benefit |
|---|---|
| Faster repeat booking | Clearer pickup/drop context |
| Less retyping | Fewer clarification calls |
| Preferred mode saved | Better demand predictability |
| UPI preselected | Faster ride closure |
| Stronger habit formation | Higher repeat booking |

This is stronger than a discount-led retention strategy because it improves convenience and marketplace efficiency at the same time.

---

## Final Recommendation

Rapido should build **Saved Routes** for 18–25 riders.

The strongest use case is a student or young worker who repeats the same route often and wants to save time while booking, coordinating pickup/drop, and paying.

The feature should let the rider save:

- where they actually stand
- where they actually want to go
- what they call those places
- which mode they usually take
- how they usually pay

This is a focused, feasible product bet. It avoids unnecessary new categories and instead improves a repeated behaviour that already exists inside the Rapido journey.

> **Final insight:** For youth riders, the best mobility feature is not more choice. It is less repeated effort.

---

## References

1. [Rapido Google Play Listing](https://play.google.com/store/apps/details?id=com.rapido.passenger)
2. [Economic Times: Rapido FY25 Revenue](https://m.economictimes.com/tech/startups/rapido-fy25-revenue-jumps-44-to-rs-934-crore-loss-narrows-30-to-rs-258-crore/articleshow/126933160.cms)
3. [MediaNama: Rapido FY25 Revenue and Cost Structure](https://www.medianama.com/2026/01/223-rapido-fy25-revenue-jumps-44-percent-loss-narrows/)
4. [Google Maps Platform: Rapido Pickup Clarity Case Study](https://mapsplatform.google.com/resources/blog/how-rapido-is-building-customer-and-rider-trust-in-india-with-google-maps/)
5. [NPCI UPI Product Reference](https://www.npci.org.in/product/upi)
