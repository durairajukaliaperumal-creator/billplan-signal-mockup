# Bill Plan — Signal Design System Mockup

Redesign mockup of the Exotel **Bill Plan** page (`my.exotel.com/&lt;account&gt;/billing`) as part of the Billix → Zuora migration. Built against Exotel's **Signal design system** component contracts (`PageHeader`, `Tabs`, `Alert`, `Card`, `Accordion`, `Chip`), pulled live from the `signal-storybook` MCP server — not guessed. Pricing shown is pulled live from **Zuora UAT, tenant 10004316**.

This is a static HTML mockup for design review — not a React build (it can't import the private `@exotel-npm-dev/signal-design-system` package), and not wired to any backend.

## Live

**Nav + accordion view:** https://durairajukaliaperumal-creator.github.io/billplan-signal-mockup/

Toggle between "Today's live page" (reference screenshot) and "Zuora UAT" (the redesign) at the top. Click a product pill to jump to that category; click a line item to expand its rate-plan tiers and Zuora product/charge codes.

**Box / dashboard view:** https://durairajukaliaperumal-creator.github.io/billplan-signal-mockup/box.html

Alternative layout — every category and every SKU visible on the page at once as a masonry grid of boxes, no click-to-expand or jump-nav required. Trade-off: denser page, more scrolling than clicking.

**At real scale (130 SKUs):** https://durairajukaliaperumal-creator.github.io/billplan-signal-mockup/at-scale.html

The legacy page hard-codes 12 SKUs. A real enterprise Exotel account can have 100+ active rate plans across a dozen product families — at that scale, fixed category cards stop working. This view uses a searchable, filterable list instead (category breakdown and SKU names reflect a real account's actual scale; **prices are hand-picked illustrative examples, not any real customer's billing** — see caveat below).

## Brand color

Accent color (`#0074E8`) and the "flag"/attention color were pulled directly from `exotel.com`'s own production CSS rather than guessed — the Exotel wordmark itself is a flat charcoal (`#231F20`) with no brand hue of its own, so the blue is what's actually used site-wide as the accent.

## Context

- PRD: [Bill Plan Page — Obelix Billix → Zuora Migration](https://exotel.atlassian.net/wiki/spaces/BIL/pages/2107277599/PRD+Bill+Plan+Page+Obelix+Billix+Zuora+Migration)
- Related epic: [BILLOPS-2083](https://exotel.atlassian.net/browse/BILLOPS-2083)

## What's real vs. illustrative

- **Real**: Zuora product/rate-plan/charge structure and list prices on the first two pages (pulled live from UAT tenant 10004316, 10 Oct 2026), Signal component props/variants (pulled live from the Signal MCP), Exotel's accent color (pulled from `exotel.com`'s own CSS).
- **Not real**: any specific customer's subscribed plan on the first two pages — these are catalog list prices, not one account's negotiated rate. The `at-scale.html` page's category breakdown and SKU count are modeled on one real production account's actual scale, but every price shown there is a hand-authored illustrative example — not that account's or any customer's actual billing.
