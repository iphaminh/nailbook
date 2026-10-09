# NailBook — project notes

Where the booking product stands, what selling it would take, and how it got
here. Update it at the end of every working session (`/wrap-up`).

**Notion:** https://app.notion.com/p/3f493414a32c81da853ad95d2d831247 — the same notes, under Projects. This file is the source of truth.

---

## Where we are — 9 October 2026

**The engine is real and in use; the product isn't for sale yet.**

- **Live at one salon.** NailBook's booking engine runs Dream Nails & Spa's
  online booking at dreamnails.phaminh.com. Clients have made 8 bookings
  through it, the most recent on **8 October**. It lives in the salon platform,
  `iphaminh/naildesk`.
- **Everything the landing page promises is built:** 24/7 booking from a link,
  per-slot capacity (no double-booking), no app, a text to the owner for every
  booking, loyalty points, and an inspo step where the client picks a style or
  uploads a photo.
- **The landing page** (`landing/`) collects interest through `mailto:` links
  to nailbyminh@gmail.com. Where it's hosted isn't recorded here.
- **This repository** was split out of `nail-pos-system` on 9 October with the
  landing page's history (one commit, 4 August).

---

## Next

1. **Decide whether NailBook is a product or a feature.** As a feature, it's
   simply the booking side of NailDesk and nothing more is needed. As a product
   sold to other salons, see "What selling it would take" below — scope that
   before promising anyone access.
2. **Check the landing page's links.** It links to `nailmind.phaminh.com` and
   `naildesk.phaminh.com`. NailMind's real address is now `nailmind.app`;
   confirm the others resolve before sharing the page.
3. **Answer early-access emails** to nailbyminh@gmail.com — they are the only
   demand signal NailBook has.

---

## What selling it to other salons would take

The code serves **one salon per deployment**: there's no salon id on any table,
and the salon's name, hours and rules are single global settings. To offer
NailBook to a second salon, pick one:

- **A deployment per salon** — copy the app and give each salon its own
  database. Fastest to start, but every update has to be shipped N times.
- **Multi-tenancy** — add a salon id to every table and query, per-salon
  settings, sign-up and onboarding, and billing. The right long-term shape and
  a substantial project.

Either way it would also need per-salon branding on the booking page, a way for
a salon to load its own menu and techs, and Terms and a Privacy Policy written
for salons as customers.

---

## Decisions, and why

- **The engine stays in NailDesk** (Oct 2026). Booking shares customers, techs
  and services with the POS, and a booking becomes a POS ticket. Copying it here
  would mean two versions of the same tables drifting apart. This repo holds the
  product — positioning, page, plans — not a second copy of the code.

---

## History

**4 August 2026.** The landing page is in the first commit of the shared
codebase. By then the booking engine was already running at Dream Nails.

**9 October 2026.** Split into this repository. Confirmed the engine is in live
use (8 bookings, latest 8 October).

**Related, older work** — not part of NailBook's code: an earlier booking site,
`iphaminh/nails-by-minh-booking` (public, last pushed July 2026), and a paused
Supabase project named `Nailbyminh`.
