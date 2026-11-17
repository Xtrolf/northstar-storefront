# Northstar — Curated Commerce Experience

Northstar is a responsive editorial storefront prototype with a premium, youth-oriented visual identity. The live catalogue is served from Supabase; cart and wishlist interactions remain device-local until account UI and sync are completed.

## Live links
- Production storefront: https://northstar-storefront-ten.vercel.app
- GitHub repository: https://github.com/Xtrolf/northstar-storefront

## Frontend
- Responsive editorial homepage and category discovery
- Product catalogue loaded from Supabase PostgREST
- Category filtering, search and sorting
- Product quick-view modal
- Shopping bag with quantity controls
- Wishlist saved on the current device
- Product comparison (up to 3 products)
- Recently viewed tracking
- Keyboard shortcut: `/` or `Ctrl/Cmd + K` to focus search
- Reduced-motion support, accessible labels and safe text rendering
- Static HTML/CSS/vanilla JavaScript; no frontend build step

## Supabase backend
Project: `northstar-commerce`  
Region: `ap-south-1` (Mumbai)  
Database: PostgreSQL 17

Tables:
- `categories`, `products`
- `profiles`
- `carts`, `cart_items`, `wishlist_items`
- `orders`, `order_items`
- `coupons`

Security:
- Row Level Security enabled on all public tables
- Public read access limited to catalogue data
- User-owned profile, cart and wishlist policies
- User order visibility is scoped to the authenticated owner
- Admin write policies rely on the server-controlled `app_metadata.role = 'admin'` claim
- Browser uses only the Supabase publishable key; never place a service-role or secret key in frontend code
- Supabase security advisor currently reports no findings

## Current limitations — not production checkout
The 12 seeded products, prices, ratings, review counts and stock values are sample/demo data. They are flagged `is_demo_data = true`. They are not verified inventory or genuine customer reviews.

This is not yet a complete commerce system:
- Sign-up, login and account UI are not wired into the storefront
- Cart and wishlist are stored in browser localStorage, not synced across devices
- Newsletter signup is local demo state; no email is sent
- No checkout/order-creation flow is exposed to customers
- No payment provider is connected
- No shipping, tax, refunds, notifications or order fulfilment integrations exist

Do not accept real orders or payments through this prototype. Before launch, implement authenticated customer flows, server-side price/stock validation, secure order creation, payment-provider webhooks, inventory reservation, admin operations and end-to-end tests.

## Run locally
Open `index.html` in a modern browser. The public catalogue request requires an internet connection.

## Data API
The browser queries the public products endpoint using the publishable key. Row Level Security limits visible rows to published products. The publishable key is designed for public clients; privileged keys must remain server-side.
