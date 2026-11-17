# AGENTS.md — signeting.com marketing site

Read this file before doing anything in this repo. Folder-level `AGENTS.md` files in `components/` and `content/` add local rules.

## What this repo is
The **marketing website** for Signeting (signeting.com), an email signature creation and analytics platform.
- This repo is marketing only. Never touch the product app (app.signeting.com), the API (api.signeting.com), DNS, or hosting from here.
- signeting.com currently runs on Webflow, with DNS on Cloudflare. Deployment of this site is a later decision for Dev.

## Product facts (do not invent beyond these; ask Dev)
- Create email signatures from a 40-template library, with field icons and a banner add-on, and track them with analytics.
- Plans: Free, Pro, Team. Monthly and yearly billing. A free Pro trial is offered.
- Team can upgrade to an Organization workspace (Signeting Enterprise: Google Workspace + Microsoft 365).
- Primary audience: individuals and freelancers. Main goal: paid conversions (start free Pro trial).
- Markets: global and India, equally weighted. Pricing must show INR and USD.

Never invent prices, stats, customer logos, testimonials, or integrations. If it isn't in `meta/`, ask.

## Brand
- Logo: circular pen-nib mark + "Signeting" wordmark (light and dark versions; Dev provides the files).
- Colours: the current variables are in the Figma file **"Signeting-Individual"**. Read them from there or ask Dev. Do not reuse older brand colours from old code or memory.
- Font: ABC Diatype (licensed). Dev supplies the font files for `public/fonts/`. Never substitute another font silently.
- Page designs are made in **Paper**. Links go in `meta/design-links.md`.

## Workflow: phases and gates
Every phase ends at a GATE: stop, show Dev the output, and wait for approval.

| Phase | Output | Gate |
|---|---|---|
| 0. Setup | Review this skeleton, propose the stack, log it in `decisions.md` | Dev approves the stack |
| 1. Strategy | `meta/00-context.md`, `meta/strategy/*` | Dev approves the strategy |
| 2. Plan | `sitemap.md`, `roadmap.md`, first `brief.md`, `styles/tokens.css` | Dev approves the plan |
| 3. Build | One cycle per page in `meta/cycles/` | Dev approves each page's PR |

## Cycle order (one cycle per page)
Copy `meta/cycles/_template/` to `meta/cycles/YYYY-MM-<page>/`. Lock each step before the next starts:
1. `brief.md` approved
2. `copy.md` written from `meta/strategy/messaging.md`, then approved by Dev
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
- No paid services, tracking scripts, or third-party accounts without Dev's approval.
- Never ask for or store passwords, tokens, or keys in chat or in the repo.
- Small commits with clear messages.
