# AGENTS.md — signeting.com marketing site

Read this file before doing anything in this repo. Folder-level `AGENTS.md` files in `components/` and `content/` add local rules.

## What this repo is
The **marketing website** for Signeting (signeting.com), an email signature creation and analytics platform.
- This repo is marketing only. Never touch the product app (app.signeting.com), the API (api.signeting.com), DNS, or hosting from here.
- signeting.com currently runs on Webflow, with DNS on Cloudflare. Deployment of this site is a later decision for Suraj.

## Product facts (do not invent beyond these; ask Suraj)
Signeting is an email signature product **for companies**. Its value:
- **Banner campaigns** in email signatures, with **click analytics**.
- **Click-to-CRM insight**: see which clicks lead to CRM outcomes.
- **Contact enrichment**.
- **Team control** over signatures across the company.

The site's goal and primary audience are set in `meta/00-context.md`.

**Old, from the individual product. Unconfirmed; do not use without asking Suraj:** the 40-template library, plans Free / Pro / Team, the free Pro trial, the Organization/Enterprise upgrade, and the individuals-and-freelancers audience. Any page, brief or copy built on these is **old** and gets reworked page by page, one cycle at a time.

Never invent prices, stats, customer logos, testimonials, or integrations. If it isn't in `meta/`, ask.

## Brand
- Logo: circular pen-nib mark + "Signeting" wordmark (light and dark versions; Suraj provides the files).
- Colours: Figma file **"Signeting-Individual"** is the source of brand colours **only until `styles/tokens.css` is written**. Once the tokens file exists, remove every Figma reference from the repo. Do not reuse older brand colours from old code or memory.
- Font: ABC Diatype (licensed). Suraj supplies the font files for `public/fonts/`. Never substitute another font silently.
- **Page designs are made in Paper, not Figma.** Links go in `meta/design-links.md`; exported images go in the cycle's `design/` folder.

## Workflow: phases and gates
Every phase ends at a GATE: stop, show Suraj the output, and wait for approval.

| Phase | Output | Gate |
|---|---|---|
| 0. Setup | Review this skeleton, propose the stack, log it in `decisions.md` | Suraj approves the stack |
| 1. Strategy | `meta/00-context.md`, `meta/strategy/*` | Suraj approves the strategy |
| 2. Plan | `sitemap.md`, `roadmap.md`, first `brief.md`, `styles/tokens.css` | Suraj approves the plan |
| 3. Build | One cycle per page in `meta/cycles/` | Suraj approves each page's PR |

## Cycle order (one cycle per page)
Copy `meta/cycles/_template/` to `meta/cycles/YYYY-MM-DD-<page>/`. Lock each step before the next starts:
1. `brief.md` approved
2. `copy.md` written from `meta/strategy/messaging.md`, then approved by Suraj
3. Paper design exported to `design/` (desktop and mobile)
4. Build: text in `content/`, sections in `components/sections/`, route in `app/`. Reuse components before creating new ones.
5. Final screenshots (desktop 1440, mobile 390) in `screenshots/`
6. A **separate reviewer agent** that did not build the page writes `review.md` against `meta/review-checklist.md`
7. Fix the issues, update `summary.md`, open a PR

**Cycle 0 is always "foundation"**: tokens, header, footer, buttons, page shell, SEO helper, analytics events. No page cycle starts before it is merged.

## Hard rules
- Text never lives inside components. It lives in `content/`.
- Styles use tokens only. No raw hex colours, px spacing, or font values outside `styles/tokens.css`.
- Keep each cycle's `summary.md` current, so any agent can resume.
- Log every locked choice in `meta/decisions.md` (date, decision, reason).
- No paid services, tracking scripts, or third-party accounts without Suraj's approval.
- Never ask for or store passwords, tokens, or keys in chat or in the repo.
- Small commits with clear messages.

## Threads and roles
Work is split across separate Amp threads. A thread does not see other threads' chats; it works only from the files in this repo. Handoffs happen through files, and each thread adds a line to the History section of the cycle's `summary.md` when it finishes a step.

| Thread | Owns | Does not touch |
|---|---|---|
| **Strategy & Design** | `meta/00-context.md`, `meta/strategy/*`, each cycle's `copy.md`, Paper designs, `meta/design-links.md`, exports in `design/` | `app/`, `components/`, `styles/tokens.css`, `sitemap.md`, `roadmap*.md` |
| **Planning & Roadmap** | `meta/sitemap.md`, `meta/roadmap*.md`, each cycle's `brief.md` and `summary.md`, `meta/decisions.md`, stack proposal | copy, designs, code |
| **Implementation** | `app/`, `components/`, `content/` (approved copy only, unchanged), `lib/`, `styles/tokens.css`, `screenshots/`, the PR | strategy, copy text, designs, plans |
| **Reviewer** (a fresh thread per page, never the one that built it) | the cycle's `review.md` | everything else |

- If a thread needs a change in a file it does not own, it writes the request in the cycle's `summary.md` under "Blocked on" and stops. It does not edit the file.
- Order inside a cycle stays as in "Cycle order" above: brief (Planning), copy and design (Strategy & Design), build (Implementation), review (Reviewer).
- Every thread starts by reading `AGENTS.md`, the cycle's `summary.md`, and the files it owns. Suraj approves every gate; no thread approves another thread's work.

## Git and approval
- One branch per page, named for its cycle (e.g. `page/home`). Setup work uses `setup/<topic>`.
- `main` holds approved work only. Nothing merges to `main` until Suraj approves the PR.
- The reviewer step (`review.md`) never replaces Suraj's approval; it comes before it.
- Commit only when Suraj says so.
