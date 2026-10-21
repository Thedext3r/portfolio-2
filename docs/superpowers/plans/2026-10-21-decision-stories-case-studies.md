# Decision Stories Case Studies Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Recreate all three case studies (Treebo Club, Blinkit on the Wrist, and Borrow App) directly inside `index.html` using UX Anudeep's 10-stage Decision Stories Framework, eliminating any separate standalone pages like `treebo.html`.

**Architecture:** Implement rich CSS design systems for Decision Story cards (6-part framework), guided solution journeys with screen annotations, iteration archives, and transparent context cards directly in `index.html`. Inject fully structured, story-driven HTML into `treeboCaseStudyHtml`, `blinkitCaseStudyHtml`, and `borrowCaseStudyHtml`.

**Tech Stack:** HTML5, Modern CSS (Flexbox, CSS Grid, Custom Properties, Glassmorphism, Responsive Media), Vanilla JavaScript (modal orchestration, slide deck integration).

**Spec:** [`docs/superpowers/specs/2026-10-21-decision-stories-portfolio-recreation-design.md`](file:///Users/apple/Documents/new%20portfolio%20sunil/docs/superpowers/specs/2026-10-21-decision-stories-portfolio-recreation-design.md)

## Global Constraints
- Zero standalone external case study pages (deprecate `treebo.html` and unify all content in `index.html`).
- Every case study must strictly implement all 10 stages from the guide:
  1. Title (Newspaper headline: Product + User Problem + Design Intent)
  2. Emotional Hook (Curiosity gap / tension story)
  3. Visual Tease of the Solution (Hero screens / video before backstory)
  4. Problem Statement & Structured Context Card (Plain business language, broken metrics, facts card)
  5. Solution Journey as a Guided Tour (Named persona, scenario, step-by-step with visual callouts)
  6. 3 to 5 Decision Stories (Headline, Hook, Before, Turning Point / Trade-offs, Consecutive Actions, Result)
  7. Iteration Archive (Versions tried and thrown away with post-mortems)
  8. UI System & Craft (Tokens, typography, components, WCAG AA contrast)
  9. Honest Reflection & Future Scope (Real self-critique, limitations)
  10. Closing & Contact
- All media and screenshots must reference existing local files in `assets/old_ui/`, `assets/new_ui/`, `assets/blinkit/`, `assets/borrow/`, `assets/research/`, and `images/`.

---

### Task 1: CSS Framework & Visual Architecture for Decision Stories
**Files:**
- Modify: `index.html` (CSS `<style>` section)

**Interfaces:**
- Produces: CSS classes for `.decision-story-card`, `.decision-part-badge`, `.tradeoff-box`, `.guided-journey-step`, `.iteration-card-archive`, `.metric-callout-pill`, `.context-facts-grid`.

- [ ] **Step 1: Check existing modal and case study styles in `index.html`**
- [ ] **Step 2: Add modern CSS styles for the 10-stage Decision Stories UI components**
  - Add styles for Decision Story cards (6-part layout with numbered badges: Title, Hook, Before, Turning Point with highlighted trade-off callout, Consecutive Actions, Result).
  - Add styles for the Solution Journey (guided tour step cards with persona quotes, emotional states, and visual callout markers).
  - Add styles for the Iteration Archive (before/discarded badges, rationale chips, failure analysis).
  - Add styles for Context Blocks (compact 5-item fact grid with Product, Duration, Scope, Role, Constraints).
- [ ] **Step 3: Verify styles render cleanly in browser and do not conflict with existing portfolio styles**
- [ ] **Step 4: Commit changes**
  ```bash
  git add index.html
  git commit -m "style: add Decision Stories framework CSS components to index.html"
  ```

---

### Task 2: Recreate Treebo Club Web Experience Redesign in `index.html`
**Files:**
- Modify: `index.html` (`treeboCaseStudyHtml` variable and `D.work[0]` definition)

**Interfaces:**
- Consumes: CSS classes from Task 1, assets in `assets/old_ui/`, `assets/new_ui/`, `assets/research/`, `treebo demo video.mp4`.
- Produces: 10-stage deep-dive markup for Treebo Club in `treeboCaseStudyHtml`.

- [ ] **Step 1: Structure Stage 1 to 4 for Treebo Club**
  - Stage 1 Headline: "Eliminating Checkout Drop-Offs with Upfront Pricing & Spatial Discovery: How Treebo Club’s Redesign Boosted Booking Clarity"
  - Stage 2 Hook: 11:15 PM Airport Arrival story with Priya Sharma
  - Stage 3 Visual Tease: Hero side-by-side comparison (`home_comparison_side_by_side.png`) and demo video (`treebo demo video.mp4`)
  - Stage 4 Problem Statement & Context Card: 42% drop-off metric, 4-sentence business rationale, facts card.
- [ ] **Step 2: Structure Stage 5 (Solution Journey) for Treebo Club**
  - 6-step guided walkthrough with Priya Sharma persona (Search Hero, Split-Map, Filter Sidebar, Hotel Gallery, Room Selection with taxes, In-Context Modal Auth).
- [ ] **Step 3: Structure Stage 6 (4 Core Decision Stories) for Treebo Club**
  - Decision 1: Showing All-Inclusive Prices Upfront on Listing Cards.
  - Decision 2: Transitioning from Modal Filters to Interactive Split-Map with Persistent Sidebar.
  - Decision 3: Restructuring 32 Disorganized Amenities into 3 Verified Hierarchical Buckets.
  - Decision 4: Decoupling Authentication from Full-Page Redirects to In-Context Modal.
- [ ] **Step 4: Structure Stage 7 to 10 for Treebo Club**
  - Stage 7: Iteration Archive (Discarded full-bleed map overlay and expandable accordion tax breakdown).
  - Stage 8: UI System & Craft (Tokens, Emerald brand palette, component states, accessibility).
  - Stage 9: Honest Reflection & Future Scope.
  - Stage 10: Closing & Links (remove any references to `treebo.html`; link directly to Figma & assets).
- [ ] **Step 5: Update `D.work[0]` metadata in `index.html`**
  - Update headline, tagline, and metrics in the portfolio slide deck.
- [ ] **Step 6: Test Treebo case study modal in browser to verify layout, video, and image rendering**
- [ ] **Step 7: Commit changes**
  ```bash
  git add index.html
  git commit -m "feat: recreate Treebo Club case study with 10-stage Decision Stories framework"
  ```

---

### Task 3: Recreate Blinkit on the Wrist in `index.html`
**Files:**
- Modify: `index.html` (`blinkitCaseStudyHtml` variable and `D.work[1]` definition)

**Interfaces:**
- Consumes: CSS classes from Task 1, assets in `assets/blinkit/`.
- Produces: 10-stage deep-dive markup for Blinkit on the Wrist in `blinkitCaseStudyHtml`.

- [ ] **Step 1: Structure Stage 1 to 4 for Blinkit on the Wrist**
  - Stage 1 Headline: "Glanceable 10-Minute Commerce: How Blinkit on Apple Watch Cut Repeat Ordering and Doorstep Delivery Friction to 2 Seconds"
  - Stage 2 Hook: 7:45 AM Kitchen morning routine story with Rohan
  - Stage 3 Visual Tease: 5-screen Apple Watch hardware banner (`hero_screens_banner.png`)
  - Stage 4 Problem Statement & Context Card: 30-second smartphone barrier, hands-busy household moments, facts card.
- [ ] **Step 2: Structure Stage 5 (Solution Journey) for Blinkit on the Wrist**
  - 5-screen guided walkthrough with Riya Sharma persona (Usuals card, Confirmation, Radial ETA ring, Haptic Doorstep OTP, 1-tap handoff).
- [ ] **Step 3: Structure Stage 6 (4 Core Decision Stories) for Blinkit on the Wrist**
  - Decision 1: Cutting the Search Bar in Favor of a 3-Item Habitual "Usuals" Reorder Deck.
  - Decision 2: Replacing Moving Street Maps with a Bold Radial ETA Ring.
  - Decision 3: Introducing a Dual-Stage Wrist Haptic OTP Alert at Doorstep Arrival.
  - Decision 4: Implementing an Optimistic 5-Second Circular Undo Timer.
- [ ] **Step 4: Structure Stage 7 to 10 for Blinkit on the Wrist**
  - Stage 7: Iteration Archive (Discarded 4-quadrant mini category grid and outdoor cellular street navigation).
  - Stage 8: UI System & Craft (watchOS dark mode OLED tokens, SF Pro Rounded, 44pt touch targets).
  - Stage 9: Honest Reflection & Future Scope (Substitutions iOS fallback).
  - Stage 10: Closing & Links (Figma research board link, document links).
- [ ] **Step 5: Update `D.work[1]` metadata in `index.html`**
  - Update headline, tagline, and metrics in the portfolio slide deck.
- [ ] **Step 6: Test Blinkit case study modal in browser to verify layout and watch screens**
- [ ] **Step 7: Commit changes**
  ```bash
  git add index.html
  git commit -m "feat: recreate Blinkit on the Wrist case study with 10-stage Decision Stories framework"
  ```

---

### Task 4: Recreate Borrow App: Neighborhood Lending in `index.html`
**Files:**
- Modify: `index.html` (`borrowCaseStudyHtml` variable and `D.work[2]` definition)

**Interfaces:**
- Consumes: CSS classes from Task 1, assets in `assets/borrow/`.
- Produces: 10-stage deep-dive markup for Borrow App in `borrowCaseStudyHtml`.

- [ ] **Step 1: Structure Stage 1 to 4 for Borrow App**
  - Stage 1 Headline: "Unlocking Neighborhood Sharing: How Gated Society Verification & Mutual Trust Scores Removed Social Awkwardness from Community Lending"
  - Stage 2 Hook: Saturday morning high-rise drill story with Sneha Roy
  - Stage 3 Visual Tease: 5 verified mobile screens showcase (`borrow-screen-1-onboarding.png` to `borrow-screen-5-profile.png`)
  - Stage 4 Problem Statement & Context Card: Asymmetric social friction, underutilized household tools, facts card.
- [ ] **Step 2: Structure Stage 5 (Solution Journey) for Borrow App**
  - 5-screen guided walkthrough with Sneha Roy persona (Gated Society Verification, Society Feed & Request, Lender Review & Trust Badge, In-App Handoff Chat, QR Return & Karma Boost).
- [ ] **Step 3: Structure Stage 6 (3 Core Decision Stories) for Borrow App**
  - Decision 1: Restricting Onboarding to Verified Gated Societies Instead of Open Geofences.
  - Decision 2: Mandating Pre-Set Return Windows Over Open Chat Negotiations.
  - Decision 3: Replacing Cash Security Deposits with Community Trust Badges.
- [ ] **Step 4: Structure Stage 7 to 10 for Borrow App**
  - Stage 7: Iteration Archive (Discarded society-wide broadcast blasts and paid rental micro-transactions).
  - Stage 8: UI System & Craft (Deep Trust Teal tokens, accessible card states).
  - Stage 9: Honest Reflection & Future Scope (Community micro-insurance pool).
  - Stage 10: Closing & Links (Figma wireframes link, contact trigger).
- [ ] **Step 5: Update `D.work[2]` metadata in `index.html`**
  - Update headline, tagline, and metrics in the portfolio slide deck.
- [ ] **Step 6: Test Borrow App case study modal in browser to verify layout and mobile screens**
- [ ] **Step 7: Commit changes**
  ```bash
  git add index.html
  git commit -m "feat: recreate Borrow App case study with 10-stage Decision Stories framework"
  ```

---

### Task 5: Clean Up External References, Remove `treebo.html`, & Perform Final Audits
**Files:**
- Delete: `treebo.html`
- Modify: `index.html` (remove any remaining links/mentions of `treebo.html`)

- [ ] **Step 1: Remove `treebo.html` and eliminate all outbound references in `index.html`**
  - Check that clicking any Treebo action button opens the in-page modal case study directly.
- [ ] **Step 2: Run the 30-Second Scan Audit across all 3 case studies**
  - Verify newspaper headlines, problem statements with clear metrics, and high-contrast before/after visuals.
- [ ] **Step 3: Run the 10-Minute Scrutiny Audit across all 3 case studies**
  - Verify that each Decision Story has all 6 parts, clear trade-offs, and iteration rationale.
- [ ] **Step 4: Commit changes and verify git cleanliness**
  ```bash
  git rm treebo.html
  git add index.html
  git commit -m "chore: remove standalone treebo.html and finalize unified Decision Stories portfolio"
  ```
