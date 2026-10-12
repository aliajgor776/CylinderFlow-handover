# CylinderFlow Multi-Branch LPG Delivery

CylinderFlow is a mobile-first multi-branch LPG cylinder delivery operations preview. It includes a customer ordering surface and an admin workspace for branches, products/stock, orders, customers, due ledger, reports, staff permissions, settings and QR download configuration.

This project keeps the React / Express / tRPC / Drizzle starter foundation so the demo UI can be connected to managed MySQL and real auth without changing the product shell.

- `pnpm dev`: development server; honors `PORT` (default 3000).
- `pnpm build` / `pnpm start`: build and serve `dist/index.js` and `dist/public/`.
- `pnpm db:migrate`: apply checked-in migrations. `pnpm db:push`: generate and apply new schema changes.
- `pnpm check` / `pnpm test`: types and application tests.

Start with the Webdev skill's default-template guide. Platform login, storage, payments and service contracts live in its shared references; read the relevant capability before extending its helper.

## Run locally

```bash
pnpm install
pnpm dev
```

Open `http://localhost:3000` for the customer app and `http://localhost:3000/admin` for the admin workspace.

## Included preview modules

Customer branch selection, catalogue search, product cards, cart, COD order action, order history/status timeline, address/due view and Bengali/English switcher are included. Admin includes overview metrics, sales chart, branches, orders, products/stock, customers, due ledger, reports, staff/access guardrails, business settings and QR configuration.

The first release intentionally keeps Cash on Delivery enabled and online checkout/delivery-charge calculation disabled but future-ready in the UI. The preview uses realistic demo data; it does not collect real customer credentials or accept real orders.

## Production handover notes

See [`docs/PRODUCTION-READINESS.md`](docs/PRODUCTION-READINESS.md) for the required database/auth/storage/payment/native-release steps. The responsive customer surface is PWA-ready for Android/iOS browser installation. Signed Google Play/App Store binaries require the business's store accounts, bundle identifiers, signing certificates and final backend URLs; those credentials are intentionally not embedded.

`server/_core/publicConfig.ts` exposes only named public runtime values. Private keys stay server-side. The platform serves managed `/manus-storage/` assets; the application does not register a second proxy.

Platform configuration is readable and editable through `webdev.config`. Default settings are initial values, not enforced constraints. The agent may modify the files, commands and configuration or follow the flexible guide for another stack.
