# Production readiness notes

## What is ready in this handover

The customer and admin flows are wired as an immediately testable mobile-first preview. Visual hierarchy, responsive layouts, route manifest, PWA metadata, demo data, status states, branch context, due/report/permissions surfaces and the Webdev server/build contracts are present. `pnpm check` and `pnpm build` pass.

## Required before accepting real orders

1. Replace demo arrays/local UI actions with Drizzle/MySQL tables and tRPC procedures for branches, customers, products, stock movements, orders, due transactions, staff roles, audit logs and settings.
2. Enable real Manus OAuth application sessions and map the primary admin/staff roles to database records.
3. Add object-storage uploads for product/brand images and validate image type/size server-side.
4. Add push/SMS integrations only after the business selects providers and supplies credentials.
5. Add bKash/Nagad/Rocket gateway credentials and webhook validation when online payments are enabled.
6. Configure production domain, HTTPS, database backup policy and store links in Admin → Settings & QR.
7. Complete device testing on a representative Android and iOS handset, then create signed native builds with the business's Play Console/App Store Connect accounts.

The preview deliberately does not pretend that real payment, real customer identity, real persistence or store publication is active. These are protected production steps and should be configured after the business rules and credentials are confirmed.
