# Review checklist

The single standard for every page review. The reviewer must be a separate agent that did not build the page. Mark each item ✅ / ❌ with a note in the cycle's `review.md`.

## Design
- [ ] Matches the Paper design on desktop (1440)
- [ ] Matches the Paper design on mobile (390)
- [ ] Uses tokens only; no raw colours, spacing, or font values

## Copy
- [ ] Text matches the approved `copy.md` word for word
- [ ] No invented prices, stats, logos, or testimonials
- [ ] Pricing shows correct INR and USD values

## Function
- [ ] Primary CTA works and fires its analytics event
- [ ] All links work (no 404s, no placeholder `#` links)
- [ ] No console errors

## SEO
- [ ] Unique title and meta description
- [ ] OG image set
- [ ] One H1; headings in order

## Accessibility
- [ ] Text contrast meets WCAG AA
- [ ] Every meaningful image has alt text
- [ ] All interactive elements reachable and visible with the keyboard

## Performance
- [ ] Images optimised and sized
- [ ] Fonts loaded from `public/fonts/` without layout shift
