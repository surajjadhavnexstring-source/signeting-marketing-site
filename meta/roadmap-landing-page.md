# Roadmap: landing page (Home, `/`)

> Plan only. No copy, design or code yet. Suraj approves each gate before the next step starts.
> Product facts come from `AGENTS.md`: Signeting is an email signature product for companies (banner campaigns with click analytics, click-to-CRM insight, contact enrichment, team control).
> Cycle folder: `meta/cycles/2026-11-17-home/`. Branch: `page/home`.
> **History:** after every step or decision, add a line to the History section of that folder's `summary.md` (date, what happened, who approved). That file is how any agent resumes the work.

## Steps

| # | Step | Output | Depends on | Gate (Suraj approves) | Status |
|---|---|---|---|---|---|
| 1 | Stack decision | Stack proposed and logged in `decisions.md` | none | Stack approved | not started |
| 2 | Strategy | `meta/00-context.md` rewritten for companies; `meta/strategy/positioning.md`, `audience.md`, `messaging.md` | none (can run alongside 1) | Strategy approved | not started |
| 3 | Plan | `sitemap.md` and `roadmap.md` updated for the company product; `design-links.md` row for Home | 2 | Plan approved | not started |
| 4 | Foundation (cycle 0) | Tokens, header, footer, buttons, page shell, SEO helper, analytics events; `styles/tokens.css` written, Figma references removed | 1, brand colours from Figma, logo and ABC Diatype font files from Suraj | Foundation PR approved and merged | not started |
| 5 | Brief | `brief.md`: goal, audience, primary CTA, section list, proof needed | 2, 3 | Brief approved | not started |
| 6 | Copy | `copy.md` written from `messaging.md` | 5 | Copy approved | not started |
| 7 | Design | Paper design, desktop and mobile; link in `design-links.md`; exports in `design/` | 5, 6 | Design approved | not started |
| 8 | Build | Text in `content/home.md`; sections in `components/sections/`; route in `app/` | 4, 6, 7 | none (goes to review) | not started |
| 9 | Screenshots | Desktop 1440 and mobile 390 in `screenshots/` | 8 | none | not started |
| 10 | Review | `review.md` by a separate agent against `meta/review-checklist.md`; issues fixed; `summary.md` updated | 9 | Reviewer verdict: ready | not started |
| 11 | PR and approval | PR on `page/home` using the PR template | 10 | Suraj approves; merge to `main` | not started |

Steps 1 to 4 are shared with every other page. Step 5 onward is specific to the landing page.

## Proposed sections (to be decided in step 5, not final)
Order and content are set in the brief. Starting points, based only on the confirmed product value:
1. Hero with the primary CTA
2. Banner campaigns and click analytics
3. Click-to-CRM insight
4. Contact enrichment
5. Team control
6. Proof (only real, verifiable proof; none exists in the repo yet)
7. Closing CTA
8. FAQ (only if the audience research shows it is needed)

## Decisions needed from Suraj before the brief
- **The one action** on the landing page. The old action was "start free Pro trial", which belongs to the individual product. What should a company visitor do?
- **Who visits.** Which roles (for example marketing, sales, IT, operations)?
- **Markets.** Are global and India still equal, and does the landing page show pricing at all?
- **Proof.** Which customer names, numbers or integrations may we show? None may be invented.
- **Stack.** Approve or change the proposed default (Next.js App Router, TypeScript, MDX).
- **Brand inputs.** Logo files, ABC Diatype files, and brand colours from Figma.

## Definition of done
The Home page is merged to `main` with approved copy, matching the Paper design on desktop and mobile, a working primary CTA with its analytics event, all items in `meta/review-checklist.md` passing, and `summary.md` current.
