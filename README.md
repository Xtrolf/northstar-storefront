# Northstar — Curated Commerce Experience

A responsive editorial storefront built with semantic HTML, CSS and vanilla JavaScript.

## Design direction
Premium editorial commerce with a dark ink / warm ivory palette, acid-lime accents, oversized serif typography, curated photography and mobile-first interactions.

## Features
- Responsive editorial homepage and category discovery
- Product catalogue with category filtering, search and sorting
- Product quick-view modal
- Persistent shopping bag with quantity controls and remove actions
- Persistent wishlist saved on the current device
- Side-by-side product comparison (up to 3 products)
- Recently viewed product tracking
- Keyboard shortcut: `/` or `Ctrl/Cmd + K` to focus search
- Newsletter demo interaction with local-device storage
- Accessible labels, empty states, reduced-motion support and safe text rendering
- No build step or third-party JavaScript dependencies

## Run locally
Open `index.html` in a modern browser.

## Data and commerce limitations
This is still a front-end portfolio prototype. Product catalogue, ratings, prices and inventory are sample data. Cart, wishlist and newsletter demo state use browser localStorage only. No real customer accounts, cross-device sync, database, live inventory, order management, email delivery, checkout or payment processing is connected. Do not accept real orders or payments through this demo.

## Planned production backend
A production version can connect to Supabase for Postgres catalogue/inventory, Auth, customer profiles, wishlist and order persistence, with strict Row Level Security. Payment processing should be added through a trusted payment provider and server-side order validation; never expose secret keys in the browser.
