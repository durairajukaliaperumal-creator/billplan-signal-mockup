# Bill Plan — Signal Design System Mockup

Redesign mockup of the Exotel **Bill Plan** page (`my.exotel.com/&lt;account&gt;/billing`) as part of the Billix → Zuora migration. Built against Exotel's **Signal design system** component contracts (`PageHeader`, `Tabs`, `Alert`, `Card`, `Accordion`, `Chip`), pulled live from the `signal-storybook` MCP server — not guessed. Pricing shown is pulled live from **Zuora UAT, tenant 10004316**.

This is a static HTML mockup for design review — not a React build (it can't import the private `@exotel-npm-dev/signal-design-system` package), and not wired to any backend.

## Live

**Nav + accordion view:** https://durairajukaliaperumal-creator.github.io/billplan-signal-mockup/

Toggle between "Today's live page" (reference screenshot) and "Zuora UAT" (the redesign) at the top. Click a product pill to jump to that category; click a line item to expand its rate-plan tiers and Zuora product/charge codes.

**Box / dashboard view:** https://durairajukaliaperumal-creator.github.io/billplan-signal-mockup/box.html

Alternative layout — every category and every SKU visible on the page at once as a masonry grid of boxes, no click-to-expand or jump-nav required. Trade-off: denser page, more scrolling than clicking.

## Context

- PRD: [Bill Plan Page — Obelix Billix → Zuora Migration](https://exotel.atlassian.net/wiki/spaces/BIL/pages/2107277599/PRD+Bill+Plan+Page+Obelix+Billix+Zuora+Migration)
- Related epic: [BILLOPS-2083](https://exotel.atlassian.net/browse/BILLOPS-2083)

## What's real vs. illustrative

- **Real**: Zuora product/rate-plan/charge structure and list prices (pulled live from tenant 10004316, 10 Oct 2026), Signal component props/variants (pulled live from the Signal MCP).
- **Not real**: any specific customer's subscribed plan — these are catalog list prices, not one account's negotiated rate. The exact brand hex for Signal's `palette.primary.*` is also approximated (resolved at runtime from the live theme, not exposed as static text by the docs server).
