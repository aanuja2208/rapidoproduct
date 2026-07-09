# Rapido Saved Routes

A product case study and MVP prototype for helping frequent Rapido riders book repeated trips faster by saving route-level context.

Lovable Live Prototype: https://route-rapido.lovable.app
Detailed Case Study: rapido-youth-mobility-case-study (1).md

---

## 1. Product Summary

**Saved Routes** is a proposed Rapido feature that allows frequent riders to save common routes with pickup, drop, ride mode, payment preference, and local landmark context.

Instead of making users repeat the same booking steps every time, Rapido can recognize repeated travel behavior and surface the right saved route when the rider is near a frequent pickup point.

The core idea:

> For frequent youth riders, the best mobility feature is not more choice. It is less repeated effort.

---

## 2. Problem Statement

Many Rapido users take the same trips multiple times a week.

For example:

```text
Next to Nath Paan Vala
→ Mechanical Engineering Dept, DTU
```

Even though the rider already knows the route, the current booking flow still makes them repeatedly:

* set the pickup location
* correct the destination
* select the same ride mode
* explain the same landmark to the captain
* complete the same UPI payment flow

The problem is not route discovery.

The problem is repeated manual effort in a high-frequency use case.

---

## 3. Target Users

Saved Routes is designed mainly for **18–25-year-old frequent riders**, including:

* college students
* interns
* coaching students
* first earners
* young professionals living in PGs or hostels

These users often travel on predictable routes such as:

| User Type        | Common Repeated Route                |
| ---------------- | ------------------------------------ |
| College student  | Hostel → College department          |
| Intern           | Metro station → Office               |
| Coaching student | Home → Coaching centre               |
| First earner     | PG → Workplace                       |
| Student commuter | College gate → Nearby metro/bus stop |

---

## 4. User Insight

Frequent riders do not want to make a new decision every time they book the same trip.

They want Rapido to remember:

* where they usually stand
* where they usually go
* what they call those places
* which ride mode they prefer
* how they usually pay

Saved locations are useful, but they do not fully solve the problem because a repeated ride is not just a place. It is a route with context.

---

## 5. Why Saved Locations Are Not Enough

A saved location stores only a place.

A repeated ride needs more context.

| Route Detail        | Why It Matters                                               |
| ------------------- | ------------------------------------------------------------ |
| Pickup point        | Helps the rider start from the correct place                 |
| Drop point          | Avoids wrong gates, nearby defaults, and inaccurate map pins |
| Pickup note         | Helps the captain find the rider faster                      |
| Drop note           | Helps the captain understand the exact destination           |
| Preferred ride mode | Saves repeated bike, auto, or cab selection                  |
| Payment preference  | Makes ride completion faster                                 |
| Usual route context | Helps Rapido surface the right route at the right time       |

Saved Routes stores the full repeated ride pattern instead of only saving isolated locations.

---

## 6. Proposed Solution

Rapido should introduce **Saved Routes** as a lightweight repeat-booking feature.

A saved route can include:

* route name
* pickup location
* drop location
* custom pickup tag
* custom drop tag
* preferred ride mode
* preferred payment method
* usual route context

Example saved route card:

```text
College Morning Ride

Next to Nath Paan Vala
→ Mechanical Engineering Dept, DTU

Bike · UPI · Usually ₹45–₹60

[Book Now]
```

The feature reduces repeated booking effort while keeping the rider in control.

Rapido should never book automatically. The rider must always confirm before a ride is placed.

---

## 7. Product Hypothesis

If frequent 18–25-year-old riders can save routes with pickup/drop tags, preferred ride mode, and UPI payment preference, then repeat bookings will become faster and more frequent without reducing booking conversion.

---

## 8. Jobs To Be Done

### Primary Job

When I am taking a route I have already taken before, I want Rapido to remember the important details so that I can book faster without repeating the same setup every time.

### Supporting Jobs

* When I am standing near a familiar pickup point, I want Rapido to show my usual route first.
* When I book from a confusing location, I want the captain to see the landmark I usually explain verbally.
* When my ride ends, I want to pay the exact fare quickly through UPI.
* When my routine changes, I want to edit or delete the saved route easily.

---

## 9. Core Feature Experience

### 9.1 Save a Route After a Completed Ride

After a rider completes the same or similar route multiple times, Rapido can prompt:

```text
You have taken this route 3 times recently.
Save it as a frequent route?
```

The rider can then:

* name the route
* edit pickup and drop tags
* choose preferred ride mode
* save preferred payment method

Example:

```text
Route Name: College Morning Ride
Pickup Tag: Next to Nath Paan Vala
Drop Tag: Mechanical Engineering Dept, DTU
Mode: Bike
Payment: UPI
```

---

### 9.2 Surface the Route Automatically

When Rapido detects that the rider is near a saved pickup point, the app can move the relevant route card to the top of the home or booking screen.

Example:

```text
You’re near “Next to Nath Paan Vala.”
Book your usual bike ride to Mechanical Engineering Dept?
```

This should happen only when location confidence is high.

The goal is to assist the rider, not take control away from them.

---

### 9.3 Book in Fewer Steps

The saved route card already contains:

* pickup
* destination
* ride mode
* payment preference

The rider can tap **Book Now**, review the details, and confirm.

The ride is placed only after explicit confirmation.

---

### 9.4 Share Pickup and Drop Notes With the Captain

Indian pickup and drop contexts often depend on local landmarks.

Examples:

```text
Next to Nath Paan Vala
Opposite the photocopy shop
Near the side gate
Mechanical Engineering Dept, not the main gate
```

Saved Routes allows riders to store these notes once and reuse them.

The captain receives:

* map location
* rider-written pickup note
* rider-written drop note

This can reduce repeated calls, pickup confusion, and delays.

---

### 9.5 UPI-First Payment Flow

For saved routes, Rapido can preselect UPI as the preferred payment method.

Payment flow:

1. Ride ends.
2. Fare is calculated.
3. UPI opens for the exact fare.
4. Rider approves the payment.
5. Captain receives payment confirmation.

Payment should never happen automatically without rider approval.

---

## 10. MVP Scope

### Included in MVP

* Save route after a completed ride
* Create a route manually from Saved Routes
* Add custom pickup and drop tags
* Save preferred ride mode
* Save UPI as preferred payment method
* Show saved route card near saved origin
* Move relevant saved route to the top when the rider is near a frequent pickup location
* Send pickup and drop tags to the captain
* Trigger exact-fare UPI payment flow after ride completion
* Allow users to edit saved routes
* Allow users to delete saved routes
* Allow fallback to normal booking flow

### Excluded From MVP

* Group rides
* Fare splitting
* Under-18 guardian flows
* New ride categories
* Automatic payment without approval
* Metro infrastructure integrations
* Helmet-related features
* Fully automated booking

---

## 11. Key Product Principles

### 11.1 Reduce Repeated Effort

Saved Routes should remove unnecessary repeated actions from the booking flow.

### 11.2 Keep the Rider in Control

The feature should suggest and prefill, not auto-book.

### 11.3 Use Local Context

Pickup and drop tags should reflect how Indian riders and captains actually communicate locations.

### 11.4 Avoid Over-Prompting

Rapido should show saved route prompts only when route frequency and location confidence are strong.

### 11.5 Preserve Normal Booking Flexibility

The rider should always be able to change pickup, drop, ride mode, or payment method before confirming.

---

## 12. Suggested MVP Screens

The prototype should demonstrate the following screens:

1. **Home Screen**

   * Shows saved route card near the top
   * Highlights the most relevant saved route based on current location

2. **Saved Route Card**

   * Route name
   * Pickup tag
   * Drop tag
   * Preferred mode
   * Payment preference
   * Book Now CTA

3. **Saved Route Details Page**

   * Full pickup and drop details
   * Editable tags
   * Preferred ride mode
   * Preferred payment method

4. **Edit Route Page**

   * Rename route
   * Edit pickup note
   * Edit drop note
   * Change preferred mode
   * Change payment preference

5. **Booking Confirmation Screen**

   * Shows pickup, drop, mode, and payment
   * Allows last-minute edits
   * Requires explicit confirmation

6. **Captain-Facing Notes**

   * Displays pickup note clearly
   * Displays drop note clearly
   * Keeps map pin visible

7. **UPI Payment Prompt**

   * Opens after ride completion
   * Shows exact fare
   * Requires rider approval

---

## 13. Product Logic

### Route Creation Trigger

Rapido can suggest saving a route when:

```text
Same or similar origin-destination pair is detected
AND the ride has occurred 2–3 times
AND the pattern appears within the last 14–30 days
```

### Route Surfacing Trigger

Rapido can surface a saved route when:

```text
User opens the app
AND current location is near saved pickup point
AND location confidence is high
AND route has recent reuse history
```

### Prompt Suppression Rules

Rapido should avoid showing saved route prompts when:

* location confidence is low
* user has dismissed the route repeatedly
* route has not been used recently
* pickup/drop pattern is inconsistent
* the user is already in an active booking flow

---

## 14. Success Metrics

### North Star Metric

**Repeat bookings through Saved Routes**

This measures whether users are actually using Saved Routes to complete repeated rides.

---

### Input Metrics

| Metric                     | What It Measures                                    |
| -------------------------- | --------------------------------------------------- |
| Saved route creation rate  | Whether users find the save route prompt useful     |
| Saved route reuse rate     | Whether saved routes become part of repeat behavior |
| Custom tag completion rate | Whether users value pickup/drop notes               |
| Preferred mode save rate   | Whether riders want route-level mode memory         |
| UPI preference save rate   | Whether payment preference is useful                |
| Saved route card CTR       | Whether surfaced route cards are relevant           |

---

### Output Metrics

| Metric                                        | Expected Direction |
| --------------------------------------------- | ------------------ |
| Time-to-booking                               | Decrease           |
| Repeat-route booking rate                     | Increase           |
| Rider-captain clarification calls             | Decrease           |
| Ride-end payment completion time              | Decrease           |
| Repeat ride frequency among saved-route users | Increase           |

---

### Guardrail Metrics

| Metric                                 | Risk Being Monitored        |
| -------------------------------------- | --------------------------- |
| Booking conversion                     | Should not decrease         |
| Accidental bookings                    | Should not increase         |
| UPI failures                           | Should not increase         |
| Support tickets                        | Should not increase         |
| Captain complaints about unclear notes | Should not increase         |
| Route card dismissals                  | Should not become excessive |

---

## 15. Experiment Plan

### Hypothesis

If frequent riders can save routes with pickup/drop tags, preferred mode, and UPI preference, then repeat bookings will become faster and more frequent without hurting conversion.

### Test Group

18–25-year-old riders who have taken similar origin-destination trips at least 2–3 times in the last 14–30 days.

### Control Group

Users who continue with the existing booking flow.

### Duration

6–8 weeks.

### Primary Success Criteria

* Saved routes are reused
* Time-to-booking decreases
* Repeat-route bookings increase
* Payment completion time decreases
* Booking conversion does not drop

### Failure Criteria

* Users save routes but do not reuse them
* Route cards are dismissed often
* Accidental bookings increase
* UPI failures increase
* Captains find custom tags confusing
* Users continue editing the route every time before booking

---

## 16. Risk Assessment

| Risk                               | Severity | Mitigation                                       |
| ---------------------------------- | -------: | ------------------------------------------------ |
| Wrong route card appears           |   Medium | Trigger only when location confidence is high    |
| Custom tag is unclear              |   Medium | Add examples, placeholders, and character limits |
| User forgets to update stale route |   Medium | Prompt review after repeated manual edits        |
| Captain ignores note               |   Medium | Show note prominently in captain app             |
| UPI payment fails                  |   Medium | Keep QR, cash, and alternate UPI fallback        |
| User expects automatic payment     |     High | Make approval step explicit                      |
| Too many prompts annoy users       |   Medium | Trigger only after repeated route behavior       |
| User books wrong saved route       |     High | Add confirmation screen before booking           |

---

## 17. Product Impact

### Rider Impact

Saved Routes improves the rider experience by reducing repeated work.

Expected benefits:

* faster repeat booking
* less typing
* fewer pickup corrections
* fewer drop corrections
* fewer captain calls
* smoother ride-end payment
* stronger habit formation around repeated routes

---

### Captain Impact

Captains benefit from clearer route context.

Expected benefits:

* clearer pickup instructions
* clearer drop instructions
* fewer clarification calls
* faster rider pickup
* lower confusion around landmarks
* smoother payment closure

---

### Business Impact

Saved Routes can improve repeat usage without relying only on discounts.

Expected benefits:

* higher repeat-route bookings
* improved booking convenience
* better retention through product utility
* fewer failed or delayed pickups
* faster payment completion
* stronger marketplace efficiency

This matters because discount-led retention can become expensive. Saved Routes creates retention by reducing friction instead of simply lowering price.

---

## 18. Why This Feature Makes Sense for Rapido

Rapido already serves frequent mobility use cases.

Saved Routes improves an existing behavior instead of creating a new product category.

The feature is practical because it works within Rapido’s current ride-hailing journey:

```text
Open app → Select route → Confirm ride → Complete trip → Pay
```

Saved Routes improves the repeat-use version of this journey:

```text
Open app → Tap saved route → Confirm ride → Complete trip → Approve UPI payment
```

This is a product utility bet, not a novelty feature.

---

## 19. Final Recommendation

Rapido should build Saved Routes as a focused MVP for frequent 18–25-year-old riders.

The feature should let riders save:

* where they actually stand
* where they actually want to go
* what they call those places
* which ride mode they usually take
* how they usually pay

The strongest part of the proposal is **location-aware surfacing**.

When Rapido detects that a rider is near a frequent saved pickup point, the relevant saved route should automatically move to the top of the app experience.

This reduces effort while keeping the rider in control.

Saved Routes is a practical product bet because it improves repeated behavior inside Rapido’s existing ride-hailing journey instead of adding a broad youth, social, or discount-led feature.

---

## 20. Prototype Coverage

The prototype demonstrates the MVP experience for Saved Routes.

It includes:

* home screen with saved route card
* automatic surfacing of relevant route near frequent pickup point
* saved route details page
* editable pickup and drop tags
* preferred ride mode selection
* UPI preference selection
* confirmation screen before booking
* captain-facing pickup/drop notes
* UPI-first payment prompt after ride completion

The prototype focuses on product clarity, user control, and repeat-booking convenience.

---

## 21. References

* Rapido Google Play listing:
  https://play.google.com/store/apps/details?id=com.rapido.passenger

* Economic Times: Rapido FY25 revenue:
  https://m.economictimes.com/tech/startups/rapido-fy25-revenue-jumps-44-to-rs-934-crore-loss-narrows-30-to-rs-258-crore/articleshow/126933160.cms

* MediaNama: Rapido FY25 revenue and cost structure:
  https://www.medianama.com/2026/01/223-rapido-fy25-revenue-jumps-44-percent-loss-narrows/

* Google Maps Platform: Rapido pickup clarity case study:
  https://mapsplatform.google.com/resources/blog/how-rapido-is-building-customer-and-rider-trust-in-india-with-google-maps/

* NPCI UPI product reference:
  https://www.npci.org.in/product/upi
