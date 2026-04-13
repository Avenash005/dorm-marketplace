🧭 1. Scope Cut (What We Are NOT Building)
Online Payments
Not included because this MVP focuses only on in-person exchanges and adding payments increases complexity.
Live Chat System
Real-time messaging is not necessary for Day 1; coordination can happen outside the app.
Advanced Search & Filters
Basic listing view is enough for MVP; advanced filtering is scope creep at this stage.
🚀 2. MVP Features (What We ARE Building)
Item Listing
Students can list items with title, description, and optional price (or mark as free).
View Available Items
Users can browse all currently available items in the marketplace.
Claim Item Flow
A user can claim an item, temporarily locking it until pickup is confirmed or expires.
✅ 3. Acceptance Criteria (Claim Item Flow)
Scenario 1 — Successful Claim
Given an item is available
When a user clicks "Claim Item"
Then the item status changes to "Reserved" and becomes unavailable to others
Scenario 2 — Concurrency Collision
Given two users attempt to claim the same item at the same time
When both requests are processed
Then only one claim succeeds and the other user sees "Item no longer available"
Scenario 3 — Ghost Buyer (Claim Expiry)
Given an item is reserved by a user
When the user does not confirm pickup within the time limit
Then the claim expires and the item becomes available again
⚙️ Additional System Rules (Important for Real Usage)
🔁 Claim Expiration Logic
Each claim has a timer (e.g., 2–5 minutes in prototype)
After expiry → item returns to "Available"
🔒 Single Active Claim Rule
Only one active claim per item at any time
🧑‍💼 Seller Override (Hallway Sale Scenario)
Seller can:
Mark item as "Sold"
Remove listing anytime
This overrides any active claim
🧠 MVP Philosophy

This MVP focuses on:

Core usability (list → view → claim)
Handling real-world messy scenarios
Keeping logic correct without adding unnecessary complexity
📌 Summary

Dorm Marketplace MVP enables:

Simple campus-based item exchange
No payments, no shipping, no complexity
Strong handling of real-world edge cases like:
concurrency conflicts
inactive buyers
off-platform sales
