# CylinderFlow Implementation Plan

## Product scope
CylinderFlow is a multi-branch LPG cylinder home-delivery management system with a customer mobile-first ordering experience and a responsive admin backend. The first delivered build is a production-oriented web/PWA-compatible implementation that can be opened on Android/iOS browsers and later wrapped or connected to native Flutter/React Native clients through the same API boundary.

## Implementation approach
- React + TypeScript + Tailwind for a responsive customer/admin experience.
- Express/tRPC/Drizzle starter retained for a server/database-ready architecture.
- Demo data and local persistence make the preview immediately testable without requiring real business credentials.
- Domain modules represented in the UI: branches, products, inventory, customers, orders, due ledger, staff/permissions, reports, settings, and QR download configuration.
- All business-facing settings are editable in the admin Settings surface rather than hard-coded in copy.
- COD is active; online payments and delivery-charge calculation are intentionally future-ready and visibly marked as disabled for the first release.

## Design direction
- **Movement:** operational clarity meets modern logistics dashboard.
- **Principles:** fast scanning, strong hierarchy, calm confidence, mobile-first touch targets.
- **Color philosophy:** #0268F1 is the signature action blue; warm white surfaces keep the experience approachable while navy text improves legibility.
- **Layout paradigm:** split workspaces: a compact operations rail for admin and a bottom-navigation mobile shell for customers.
- **Signature elements:** blue status rail, cylinder-inspired rounded cards, metric chips and timeline states.
- **Interaction:** direct actions, visible status, confirmation-friendly controls, no hidden business rules.
- **Animation:** short 160–220ms fades/slide-ups only for views and status changes.
- **Typography:** system sans stack with strong numeric hierarchy for operational values; Bengali text remains readable with fallback system fonts.
- **Brand essence:** dependable cylinder delivery operations for growing local businesses. Personality: dependable, clear, capable.
- **Brand voice:** practical and reassuring. Example: “আজকের ডেলিভারি এক নজরে” and “Confirm করুন, আমরা ডেলিভারি পাঠিয়ে দিচ্ছি।”
- **Wordmark:** “CylinderFlow” with a blue circular cylinder mark and a forward-flow notch.

## Project structure
- `client/src/pages/Home.tsx`: customer and admin experience shell, demo data workflows, responsive screens.
- `client/src/App.tsx`: route manifest for customer/admin views.
- `client/src/index.css`: application design system.
- `server/`: existing Express/tRPC foundation for future persistence and authentication.
- `drizzle/`: existing MySQL schema foundation; extended production migrations can be added next.
- `public/manus-routes.json`: preview route declaration.

## Production path
This build is preview-ready and organized for production hardening: replace demo persistence with the existing Drizzle/MySQL layer, connect Manus OAuth/role records, add object storage for product images, and add platform-specific native app shells once Play Store/App Store identities and signing accounts are supplied.
