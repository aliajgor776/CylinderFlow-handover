# CylinderFlow Delivery TODO

- Customer app: customer can select branch, browse products with brand/size/price/stock/exchange policy, add to cart, place Cash on Delivery order, view due, and see order status.
- Admin dashboard: admin can view today's metrics, branch comparison, orders, products, customers, due balances, stock alerts, and report summaries.
- Multi-branch: branches show branch code, service area, stock, sales, and active order workload; admin can switch the selected branch context.
- Product controls: product name, Bengali name, brand, cylinder size, SKU, selling price, cost price visibility note, stock, delivery estimate, exchange policy, and active state are represented.
- Order workflow: Pending, Confirmed, Preparing, Assigned, Out for delivery, Delivered, Cancelled and Rejected states are represented with status actions.
- Due management: customer-wise due list, branch/date filters, manual payment methods, partial/full settlement controls, and audit-friendly ledger presentation are represented.
- Staff permissions: staff roles, branch assignment, sales-price permission, report permission, customer-data permission, and cost-price restriction are represented.
- Reports: daily, custom date range, branch, product and customer sales summaries plus due/stock/profit cards are represented.
- Settings/QR: business name, support number, business hours, holidays, language, app-store links and QR download configuration are represented.
- Localization: Bengali/English switcher changes primary navigation and content labels.
- Mobile UX: customer surface uses touch-friendly cards and bottom navigation at mobile widths; admin surface remains responsive.
- Preview contract: `GET /manus-routes.json` serves the declared routes; `/api/health` remains healthy.
- Handover: include source, deployment notes, demo credentials/data notes, and limitations in the ZIP.
