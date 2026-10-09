# NailBook — notes for Claude

NailBook is the **online-booking product for nail salons**: clients book 24/7
from a link or QR code, no double-booking, no app to install, text alerts for
the salon, loyalty points, and clients can attach their inspo photo.

**This repository holds the product's landing page and notes, not its engine.**
The booking engine runs inside the salon platform in `iphaminh/naildesk`:

- `cloud/public/index.html` — the client booking page
- `/api/public/info`, `services`, `techs`, `slots`, `book` — public API
- `/api/appointments` — staff side, in the admin

Don't copy booking code into this repo: it shares customers, techs and services
with the POS in naildesk, and a booking becomes a POS ticket there.

**Start every task by reading the top of `PROJECT.md`.**

## Working with Minh

Minh is a working nail technician, not a developer. Explain each step and why,
name exact places, don't skip steps. If Minh pastes a key or password into the
chat, don't use it — say it's exposed and how to revoke it.

## Layout

```
landing/index.html   the NailBook marketing page (static, self-contained)
landing/img/         its images
PROJECT.md           product notes: where it stands, what selling it would take
```

"Get early access" and "Book a walkthrough" are `mailto:` links to
nailbyminh@gmail.com — there is no form backend.
