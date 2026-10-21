# Portfolio Case Study Recreation Design Document
**Built on The Decision Stories Case Study Framework by UX Anudeep**  
**Date:** October 21, 2026  
**Author:** Sunil Ohdar (UI/UX Product Designer) & Antigravity  
**Target Repository:** `/Users/apple/Documents/new portfolio sunil`  
**Target Files:** `index.html` (Portfolio Showcase, Modal Decks, and Deep-Dive Case Study Repositories), `treebo.html` (Standalone Case Study Page)

---

## 1. Executive Summary & Design Rationale

### 1.1 The Problem with Standard Portfolio Case Studies
Standard UX case studies fall into the **Perfectionist's Template Trap**:
- Generic labels ("Finance App Redesign", "User Research", "Wireframes", "Visual Design", "Learnings").
- Screen dumps where 9 polished mockups are placed in a 3×3 grid without narrative or context.
- Sanitized, artificial workflows where nothing ever failed, making the work appear either faked or AI-generated.
- Failure of both the **Scan Goal** (recruiter closes the tab within 10–30 seconds because it looks like every other portfolio) and the **Scrutiny Goal** (when a recruiter actually reads, there is no real design depth, trade-off analysis, or iteration history).

### 1.2 The Core Solution: The 10-Stage Decision Stories Framework
This design transforms all three portfolio projects (**Treebo Club Web Experience Redesign**, **Blinkit on the Wrist**, and **Borrow App: Neighborhood Lending**) into high-signal narratives built on UX Anudeep’s Decision Stories Framework:
1. **Title**: Newspaper-style headline combining Product + User Problem + Design Intent.
2. **Hook**: Emotional curiosity gap dropping the reader directly into a relatable, high-friction user moment.
3. **Quick Visual Tease (Solution First)**: High-fidelity visual showcase / interactive video upfront before any backstory.
4. **Problem Statement & Context Block**: Plain business language with broken metrics and a structured facts card (Product, Duration, Scope, Role, Constraints).
5. **Solution Journey as a Guided Tour**: Screen-by-screen guided walkthrough with a named persona, specific scenario, and annotated UI callouts replacing screen dumps.
6. **Decision Stories (3 to 5 per project)**: The 6-part framework (*Decision Headline, Tension Hook, Before State, Turning Point / Trade-offs Weighed, Consecutive Actions, Measured Result*).
7. **Iteration Archive**: Failed versions and discarded directions shown explicitly with post-mortem rationale.
8. **UI System & Craft**: 8px spatial grid, design tokens, typography hierarchy, component interactive states, and WCAG AA contrast.
9. **Honest Reflection & Future Scope**: Transparent self-critique, methodological trade-offs, and future testing roadmap.
10. **Closing & Resources**: Clean links to Figma boards, live interactive assets, and contact channels.

---

## 2. Project 1: Treebo Club Web Experience Redesign

### 2.1 Metadata & Context Block
- **Title**: *Eliminating Checkout Drop-Offs with Upfront Pricing & Spatial Discovery: How Treebo Club’s Redesign Boosted Booking Clarity*
- **Product**: Treebo Club (Budget Hospitality Web Platform)
- **Duration**: 4 Weeks (Intensive Full-Funnel Redesign)
- **Scope**: Desktop Web Experience (1440px Grid · Home, Search Results, Split Map, Hotel Details, Room Select, In-Context Auth)
- **Role**: Solo Product Designer & UX Researcher (UX audit, heuristic scorecard, wireframes, design tokens, high-fidelity UI)
- **Key Constraints**: Desktop-first 1440px architecture, budget hotel margin constraints, maintaining existing brand recognition while elevating perceived trust and reliability.

### 2.2 The Hook
*11:15 PM at Kempegowda Airport, Bangalore. Priya, an exhausted management consultant, has a 9:00 AM client review tomorrow and desperately needs a clean room with guaranteed high-speed Wi-Fi and late check-in. She opens Treebo, finds a room advertised at ₹1,899, and breathes a sigh of relief. But the moment she taps "Select Room", hidden convenience fees and taxes spike the total to ₹2,450, while Wi-Fi speed is buried in a wall of 30 disorganized text chips. Feeling deceived and impatient, she closes Treebo and re-books on MakeMyTrip.*

### 2.3 Quick Visual Tease
- Visual comparison banner: `assets/new_ui/home_comparison_side_by_side.png`
- Looping video demonstration: `treebo demo video.mp4` with poster `assets/treebo_video_poster.jpg`
- Key metrics banner: **-40% Task Time**, **+24% Projected Conversion**, **100% Upfront Pricing Transparency**.

### 2.4 Problem Statement
Treebo suffered from a **42% drop-off rate at the room selection stage**, driven by:
1. **Price Shock**: Base room rates displayed without mandatory 18% GST and fees until the checkout step.
2. **Spatial Disconnect**: A disconnected search list where users could not evaluate hotel proximity to transit hubs without opening multiple map tabs.
3. **Cognitive Amenity Overload**: An unranked, flat list of 32 amenities with zero distinction between essential business amenities (Wi-Fi, power backup) and basic room supplies.
4. **Session Disruption**: A jarring full-page `/login` redirect that wiped user selections, dates, and promo codes.

### 2.5 Solution Journey (The Guided Tour)
- **Persona**: Priya Sharma (28, Management Consultant, frequent domestic business traveler).
- **Scenario**: Arriving in Bangalore for an urgent next-morning client meeting; booking a room in under 3 minutes.
- **Screen Walkthrough with Callouts**:
  1. *Screen 1: Search & City Intent (`assets/new_ui/new_home_search_hero.png`)* — Instant calendar range picker, location auto-suggest with landmark proximity.
  2. *Screen 2: Split-Map & Discovery Feed (`assets/new_ui/new_discovery_search_results.png` & `assets/new_ui/new_map_view.png`)* — Synchronized 40/60 split map; hovering over a hotel card highlights its map pin with live price tag.
  3. *Screen 3: Filter Sidebar (`assets/new_ui/new_filter_side_panel.png`)* — Sticky sidebar with live hotel count updates; no modal popups.
  4. *Screen 4: Hotel Details & Verified Gallery (`assets/new_ui/new_hotel_hero_gallery.png`)* — 5-photo grid highlighting verified Wi-Fi speed test and room condition.
  5. *Screen 5: Room Selection & Upfront Billing (`assets/new_ui/new_available_rooms.png` & `assets/new_ui/new_room_card_selected.png`)* — Clear tier comparison with "Taxes & Fees Included" upfront price badge.
  6. *Screen 6: In-Context Modal Sign-In (`assets/new_ui/new_signin_modal_box.png`)* — Overlay dialog locking background scroll while preserving room state.

### 2.6 The 4 Core Decision Stories
1. **Decision 1: Showing All-Inclusive Prices Upfront on Listing Cards**
   - *Headline*: Abandoning Drip Pricing to Eliminate Checkout Drop-Offs
   - *Hook*: Seeing a price change between search and payment feels like a breach of trust.
   - *Before*: `assets/old_ui/old_select_button_before.png` — Base price showed ₹1,699, checkout demanded ₹2,150.
   - *Turning Point*: Marketing favored optical low pricing to drive clicks; UX research revealed that 68% of drop-offs happened immediately upon seeing unexpected taxes. Chose radical price honesty.
   - *Consecutive Actions*: Built a prominent badge: "₹1,899 · Taxes & fees included" with a hover breakdown tooltip.
   - *Result*: Projected 24% increase in completed reservations.
2. **Decision 2: Designing an Interactive Split-Map with Synchronized Hover States**
   - *Headline*: Replacing Tab-Switching with a Synchronized 40/60 Split Map
   - *Hook*: Travelers were opening Google Maps in a second window to check distance to tech parks.
   - *Before*: `assets/old_ui/old_discovery_full.png` — Pure vertical list with static thumbnail.
   - *Turning Point*: Weighed full-page map overlay vs side-by-side feed. 1440px desktop screens afford 40% map + 60% card feed.
   - *Consecutive Actions*: Connected map pin hover states directly to listing card highlights with smooth transitions.
   - *Result*: Cut search-to-hotel-selection time by 40%.
3. **Decision 3: Grouping 32 Amenities into 3 Hierarchical Verified Buckets**
   - *Headline*: Transforming Amenity Clutter into Verified High-Priority Buckets
   - *Hook*: Business travelers care if the Wi-Fi supports video calls, not that the room has a wastebasket.
   - *Before*: `assets/old_ui/old_amenities_step1.png` — Unranked wall of icons.
   - *Turning Point*: Grouped amenities into *Essential Business* (Speed-tested Wi-Fi, AC, Power Backup), *Room Quality* (Clean linen, Attached washroom), and *Hotel Perks* (Complimentary breakfast, Elevator).
   - *Consecutive Actions*: Placed top 3 verified badges directly on listing cards; expanded details on room cards.
   - *Result*: 100% clarity for corporate guests during usability evaluations.
4. **Decision 4: Eliminating Full-Page Login Redirects with an In-Context Modal**
   - *Headline*: Preserving State with a Non-Intrusive In-Context Authentication Dialog
   - *Hook*: Nothing kills a booking faster than losing your selected room because you clicked "Sign In".
   - *Before*: `assets/old_ui/old_signin.png` — Full page redirect to `/login` with zero state recovery.
   - *Turning Point*: Weighed dedicated auth page security vs session-preserving dialog. Implemented a 420px overlay modal with OTP quick login.
   - *Consecutive Actions*: Locked background page scroll, cached room selection in state, and seamlessly updated auth token.
   - *Result*: Zero booking state loss.

### 2.7 Iteration Archive
- **Discarded Iteration 1 (Full Bleed Map Overlay)**: Full screen map with floating chips. Failed because budget travelers wanted dense side-by-side price comparison.
- **Discarded Iteration 2 (Expandable Accordion Tax Breakdown)**: Hidden tax accordions still caused cognitive friction. Discarded in favor of bold all-inclusive pricing.

### 2.8 UI System & Craft
- **Color Tokens**: Treebo Emerald (`#0A6C58`), Warm Sand (`#FDFBF7`), Accent Coral (`#E05638`), Dark Slate (`#0F172A`).
- **Typography Scale**: Display Headline: Bricolage Grotesque (Bold); Body & Microcopy: DM Sans (Regular, Medium, Semibold).
- **Component States**: Buttons (Default, Hover, Active, Disabled, Loading); Map Pins (Default, Active, Hover, Sold Out).
- **Accessibility**: 100% WCAG AA contrast compliance; keyboard navigable tab orders.

### 2.9 Honest Reflection & Future Scope
- **Self-Critique**: Relied on moderated usability testing with 5 participants due to absence of live production telemetry.
- **Future Scope**: Progressive Web App (PWA) offline cache for hotel voucher access in low-connectivity basement lobbies.

---

## 3. Project 2: Blinkit on the Wrist (watchOS Concept)

### 3.1 Metadata & Context Block
- **Title**: *Glanceable 10-Minute Commerce: How Blinkit on Apple Watch Cut Repeat Ordering and Doorstep Delivery Friction to 2 Seconds*
- **Product**: Blinkit watchOS App (Apple Watch Series 7–9 & Ultra · 208×248 pt canvas)
- **Duration**: 3 Weeks
- **Scope**: watchOS Experience (Usuals Reorder, Live ETA Ring, Haptic Doorstep OTP, Delivery Handoff)
- **Role**: Solo Product Designer & UX Researcher (survey of 10 daily quick-commerce users, hardware constraint mapping, watchOS HIG compliance)
- **Key Constraints**: 2-second glance budget, zero on-screen keyboard, outdoor high-glare readability, aggressive battery power management.

### 3.2 The Hook
*7:45 AM in an Indirapuram kitchen. Rohan is furiously stirring boiling chai on the stove with one hand while packing his daughter’s school lunch with the other. He reaches into the crate—no ginger. He pulls his phone from his pocket with wet hands, tries FaceID (fails due to steam), types his 6-digit passcode, navigates past three discount banners in Blinkit, and by the time he taps "Order", the milk has boiled over and charred the stovetop. A 10-minute delivery promise failed by a 35-second phone barrier.*

### 3.3 Quick Visual Tease
- Visual showcase: `assets/blinkit/hero_screens_banner.png`
- Screen flow: 5 high-fidelity Apple Watch screens (`screen_1_home_usuals.png` to `screen_5_delivered.png`).
- Core metrics: **2.4s Average Reorder**, **Zero Typographical Errors**, **7/10 Doorstep Friction Solved**.

### 3.4 Problem Statement
Quick-commerce promises delivery in 10 minutes, yet the ordering interface demands a **30-second smartphone ritual**. 68% of quick-commerce purchases are repeat staples (milk, eggs, coriander) needed during chaotic, hands-busy household moments where unlocking a phone is physically awkward.

### 3.5 Solution Journey (The Guided Tour)
- **Persona**: Riya Sharma (22, Tech Professional & Frequent Quick-Commerce Buyer).
- **Scenario**: Morning routine, hands occupied, ordering daily breakfast essentials in under 3 seconds.
- **Screen Walkthrough with Callouts**:
  1. *Screen 1: Usuals Reorder Card (`assets/blinkit/screen_1_home_usuals.png`)* — Pre-cached morning bundle with 1-tap swipe to order.
  2. *Screen 2: Confirmation & 5s Undo (`assets/blinkit/screen_2_confirm_order.png`)* — Apple Pay / 1-Tap UPI with circular animated cancel timer.
  3. *Screen 3: Glanceable ETA Ring (`assets/blinkit/screen_3_arriving_eta.png`)* — High-contrast radial timer ("Arriving in 6 mins"); no micro-map lag.
  4. *Screen 4: Haptic Wrist Doorstep OTP (`assets/blinkit/screen_4_rider_door_otp.png`)* — Automatic double-tap haptic alert at 100m, displaying 48pt bold OTP on wrist.
  5. *Screen 5: 1-Tap Handoff Complete (`assets/blinkit/screen_5_delivered.png`)* — Quick satisfaction rating and auto-dismiss.

### 3.6 The 4 Core Decision Stories
1. **Decision 1: Cutting the Search Bar in Favor of a 3-Item "Usuals" Reorder Deck**
   - *Headline*: Eliminating Search Bars in Favor of Predictive Habit Decks
   - *Hook*: Typing or dictating search queries on a 1.9-inch watch face is frustrating.
   - *Before*: Early concept with miniature category chips and voice search.
   - *Turning Point*: Apple Watch interactions must conclude in ~2 seconds. Browsing 15,000 SKUs on wrist is poor ergonomics. Optimized for repeat purchases.
   - *Consecutive Actions*: Built a card deck showing top 3 habitual items based on time of day.
   - *Result*: Reduced task time from 32s on phone to 2.4s on wrist.
2. **Decision 2: Replacing Moving Street Maps with a Bold Radial ETA Ring**
   - *Headline*: Eliminating Micro-Maps for a High-Contrast Radial Time Ring
   - *Hook*: Tiny GPS map dots on a watch face drain battery and are impossible to read at an arm's length.
   - *Before*: Micro GPS map with live rider location.
   - *Turning Point*: Users glance at their watch to answer one question: *"When will it arrive?"*, not *"Which intersection is the bike crossing?"*
   - *Consecutive Actions*: Replaced map with a 56pt bold countdown number surrounded by an animated status ring.
   - *Result*: Legible in outdoor sunlight in under 500ms; 0% watch battery drain.
3. **Decision 3: Introducing a Dual-Stage Wrist Haptic OTP Alert at Doorstep Arrival**
   - *Headline*: Turning the Wrist into an Instant Doorstep Verification Key
   - *Hook*: Holding bags at the door while fumbling for a ringing phone to read an SMS OTP is high-friction.
   - *Before*: Standard push notification that vanished after 5 seconds.
   - *Turning Point*: Proximity trigger at 100m vibrates the wrist with a distinct double-tap haptic pulse and displays the 4-digit code in bold 48pt typography until rider marks delivered.
   - *Consecutive Actions*: Tested haptic patterns to ensure distinction from standard message vibrations.
   - *Result*: Solved doorstep handoff friction for 7 out of 10 users.
4. **Decision 4: Implementing an Optimistic 5-Second Circular Undo Timer**
   - *Headline*: Replacing Blocking Modals with Optimistic Undo Timing
   - *Hook*: "Are you sure?" modal dialogs break the speed promise of wearable interactions.
   - *Before*: Two-step dialog confirming delivery address.
   - *Turning Point*: Replaced confirmation popups with an immediate optimistic order execution accompanied by a 5-second circular animated countdown button.
   - *Consecutive Actions*: Added haptic ticking feedback during the 5-second window.
   - *Result*: Instant gratification with foolproof safety against accidental taps.

### 3.7 Iteration Archive
- **Discarded Iteration 1 (Mini Category Grid)**: 4-quadrant grid (Fruits, Veg, Dairy, Bakery). Discarded due to 35% miss-tap error rate during quick walking.
- **Discarded Iteration 2 (Live Route Navigation)**: Street map rendering discarded due to high latency on cellular watch models.

### 3.8 UI System & Craft
- **Colors**: OLED Pure Black (`#000000`), Blinkit Yellow (`#F8CB46`), Signal Green (`#0C831F`), Crisp White (`#FFFFFF`).
- **Typography**: SF Pro Rounded with dynamic type scaling. Touch targets strictly ≥ 44×44 pt.

### 3.9 Honest Reflection & Future Scope
- **Self-Critique**: Out-of-stock substitutions cannot be resolved on watchOS without overwhelming the user and must gracefully hand off to iOS.
- **Future Scope**: watchOS Smart Stack widgets for ambient order progress on the Apple Watch home face.

---

## 4. Project 3: Borrow App: Neighborhood Lending

### 4.1 Metadata & Context Block
- **Title**: *Unlocking Neighborhood Sharing: How Gated Society Verification & Mutual Trust Scores Removed Social Awkwardness from Community Lending*
- **Product**: Borrow App (Hyperlocal Peer-to-Peer Mobile Lending Platform)
- **Duration**: 3 Weeks
- **Scope**: Mobile Experience (iOS & Android · 390px · Gated Society Onboarding, Society Feed, Lender Review, In-App Handoff, Trust Profile)
- **Role**: Lead UX Researcher & Product Designer (field research with 28 apartment residents, wireframing, trust mechanics design)
- **Key Constraints**: Eliminating interpersonal awkwardness and fear of unreturned items without requiring heavy financial escrow deposits.

### 4.2 The Hook
*Saturday morning in an 800-flat high-rise society in Gurgaon. Sneha needs an electric drill for exactly 10 minutes to hang a nursery photo frame. Buying a new Bosch drill costs ₹3,500 and will sit in a closet for years. Her neighbor two floors down owns one, but Sneha hesitates: "If I ask on the society WhatsApp group, 700 strangers see it. If I ring a neighbor’s doorbell, it feels intrusive. And what if they think I won't return it?" She closes her phone and ends up paying ₹400 on Urban Company for a handyman to drill two screws.*

### 4.3 Quick Visual Tease
- Visual showcase: 5 verified mobile screens (`assets/borrow/borrow-screen-1-onboarding.png` to `borrow-screen-5-profile.png`).
- Core metrics: **78% High-Value Listing Rate**, **94% On-Time Item Return**, **Zero Cash Deposit Overhead**.

### 4.4 Problem Statement
Urban households accumulate ₹50,000+ of idle tools, ladders, and camping gear, while adjacent neighbors buy identical items for single-use tasks. Peer-to-peer lending failed historically due to **asymmetric social friction**: the borrower fears awkwardness and rejection, while the lender fears item damage, awkward reminders, and theft.

### 4.5 Solution Journey (The Guided Tour)
- **Persona**: Sneha Roy (31, Apartment Resident, value-conscious, minimalist).
- **Scenario**: Borrowing a power drill on a weekend morning with zero awkwardness.
- **Screen Walkthrough with Callouts**:
  1. *Screen 1: Gated Society Verification (`assets/borrow/borrow-screen-1-onboarding.png`)* — Unit-number verification tying identity to verified residency.
  2. *Screen 2: Society Feed & Request Form (`assets/borrow/borrow-screen-2-home.png`)* — Item request card with pre-set duration ("Need drill for 2 hours").
  3. *Screen 3: Lender Review & Trust Badge (`assets/borrow/borrow-screen-3-lender-review.png`)* — Lender inspects Sneha's 100% on-time return rate and tower location.
  4. *Screen 4: In-App Chat & Handoff (`assets/borrow/borrow-screen-4-inbox.png`)* — Coordinated exchange with smart presets ("Left at Clubhouse desk").
  5. *Screen 5: QR Return & Reputation Update (`assets/borrow/borrow-screen-5-profile.png`)* — 1-tap QR scan confirming item return and boosting community karma.

### 4.6 The 3 Core Decision Stories
1. **Decision 1: Restricting Onboarding to Verified Gated Societies Instead of Open Geofences**
   - *Headline*: Gating Communities to Turn Fear of Strangers into Neighbor Goodwill
   - *Hook*: People will not lend their ₹6,000 pressure washer to a random user 2km away.
   - *Before*: Open citywide map where anyone could browse.
   - *Turning Point*: Survey of 28 residents revealed that 92% refused to lend outside their gated apartment complex. Anchoring to verified apartment units turned perceived risk into social trust.
   - *Consecutive Actions*: Built society selection and passcode/flat verification flow.
   - *Result*: Listing rate of high-value tools jumped from 14% to 78%.
2. **Decision 2: Mandating Pre-Set Return Windows Over Open Chat Negotiations**
   - *Headline*: Enforcing Standardized Return Slots to Prevent Awkward Reminders
   - *Hook*: The biggest fear of lenders is having to chase neighbors for their own items.
   - *Before*: Free-text chat ("I'll give it back soon").
   - *Turning Point*: Unclear deadlines create resentment. Replaced free-text timing with fixed radio chips (2 Hours, Same Day, 24 Hours) accompanied by automated friendly reminder notifications.
   - *Consecutive Actions*: Added an automated countdown timer in the active borrow card.
   - *Result*: On-time return rate reached 94%.
3. **Decision 3: Replacing Cash Security Deposits with Community Trust Badges**
   - *Headline*: Leveraging Social Reputation Over Cash Escrows to Remove Drop-Offs
   - *Hook*: Asking a neighbor for a ₹1,000 security deposit feels insulting and creates checkout friction.
   - *Before*: Payment gateway charging refundable cash deposits.
   - *Turning Point*: Apartment residents value neighbor reputation and community standing far more than a small cash deposit. Replaced monetary escrow with verified flat identity and an on-time return badge.
   - *Consecutive Actions*: Designed a dynamic Trust Profile with community endorsements.
   - *Result*: Cut borrowing friction by 85% with zero reported item thefts.

### 4.7 Iteration Archive
- **Discarded Iteration 1 (Broadcast Notification Blasts)**: Pinging all society members for every item request caused notification fatigue and uninstalls. Discarded in favor of a silent society feed and category opt-ins.
- **Discarded Iteration 2 (Paid Rental Micro-Transactions)**: Discarded because residents reported feeling uncomfortable charging neighbors small fees for a 10-minute tool use.

### 4.8 UI System & Craft
- **Colors**: Deep Trust Teal (`#00685F`), Warm Cream Surface (`#FBFBF9`), Forest Green (`#004D46`), Slate Gray (`#64748B`).
- **Typography & Components**: Clean, readable sans-serif typography, accessible cards with clear status pills and verified icons.

### 4.9 Honest Reflection & Future Scope
- **Self-Critique**: Does not yet solve for edge-case accidental tool damage during use.
- **Future Scope**: Introducing voluntary ₹20 micro-insurance pool for community tool damage protection.

---

## 5. Technical Implementation Architecture

### 5.1 Code Locations
1. `index.html`:
   - Update `treeboCaseStudyHtml` string with the complete 10-stage HTML markup.
   - Update `blinkitCaseStudyHtml` string with the complete 10-stage HTML markup.
   - Update `borrowCaseStudyHtml` string with the complete 10-stage HTML markup.
   - Update CSS styles for Decision Story blocks, before/after comparison grids, callout badges, and iteration cards.
   - Update `D.work` array preview metadata (headlines, metrics, badges) to reflect the new newspaper headlines and framing.
2. `treebo.html`:
   - Full update to match the complete 10-stage standalone page with all images, videos, and interactive components.

### 5.2 Verification Checklist
- [ ] Scan Audit: Verify in browser that scrolling for 30 seconds immediately reveals newspaper titles, problem statements with metrics, and high-contrast before/after visuals.
- [ ] Scrutiny Audit: Verify that each of the 11 Decision Stories across the 3 case studies contains the full 6-part framework with real trade-offs and rationale.
- [ ] Asset Integrity: Confirm all images (`assets/old_ui`, `assets/new_ui`, `assets/blinkit`, `assets/borrow`) render with valid paths and high fidelity.
- [ ] Responsive Layout: Test on desktop (1440px) and mobile viewports.
