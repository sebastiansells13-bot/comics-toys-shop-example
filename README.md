# comics-toys-shop-example

A live, deployed example ecommerce site for a fictional shop — **Rusty Robot Comics &
Toys** — built from [client-site-starter](https://github.com/sebastiansells13-bot/client-site-starter),
demonstrating the template extended with a real cart, a working shipping calculator,
and a CMS-editable product catalog.

**Live site:** https://sebastiansells13-bot.github.io/comics-toys-shop-example/

## What's real here, and what's a labeled demo

- **The product catalog, cart, and shipping calculator are fully functional.** Add to
  cart, adjust quantities, and the shipping estimate is genuinely computed client-side
  from each product's weight and a simulated carrier zone (see
  `src/_includes/js/cart.js`) — no external API, no backend, works entirely offline
  once the page loads.
- **Checkout is a labeled demo, not a real payment flow.** There's no Stripe/Square
  integration and no way to actually charge a card here — I don't have (and won't
  create) payment-processor credentials for a demo site. "Place Order" on the checkout
  page simulates a confirmation and clears the cart; the page says so explicitly. For a
  real store, that one step gets replaced with a real payment processor — the cart and
  shipping logic underneath it need no changes to keep working.
- **The shop name, products, and blog posts are fictional** but not placeholder-style
  bracketed text like the realty-agent-example — there's no real trademarked brand or
  real person's identity involved here, so real-looking (but invented) content was fine
  to use throughout, the same way the coffee-shop example did.

## What's different from the template

- New `products` content type (`src/_data/products.json`) — category, condition,
  price, weight (used by the shipping calculator), stock status, featured flag
- New pages: `/shop/` (catalog), `/cart/`, `/checkout/`
- `src/_includes/js/cart.js` — cart state (localStorage) + shipping estimator, loaded
  on every page via `src/products-data.njk` (serializes `products.json` into a JS file
  the cart script reads)
- A `money` and `json` Nunjucks filter added in `eleventy.config.cjs`
- "Services"/"Team" removed — not relevant to this business type
- `pathPrefix` and sitemap/feed hostnames point at
  `sebastiansells13-bot.github.io/comics-toys-shop-example` — needed only because this
  demo lives at a GitHub Pages *project* URL rather than a custom domain

See [CREDITS.md](CREDITS.md) for photo sourcing, including images considered and
rejected during sourcing (a specific trademarked toy character, and why real comic
cover photography was avoided in favor of an original graphic).

## Local development

```bash
npm install
npm start
```
