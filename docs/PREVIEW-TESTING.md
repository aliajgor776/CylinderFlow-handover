# Preview testing guide

## Customer flow

Open `/` and select a branch, search a product, click **Add**, then use **Place COD order**. Open **Orders** in the bottom navigation to see the order timeline. Open **Account** to inspect the saved address and current due panel.

## Multi-branch verification

Open `/admin`, choose **Branches** in the left rail, and verify Dhanmondi, Mirpur and Uttara cards. The top branch selector changes the selected branch context. Each card shows code, service area, sales, stock and active orders.

## Staff permission verification

Choose **Staff & access**. The panel shows staff role, branch, permission summary and active state. The guardrails explicitly show cost price as admin-only, reports admin-by-default, customer data grantable, and sale-price editing grantable.

## Due customer verification

Choose **Due ledger**. Verify total outstanding, collection summary and three customer balances. Click **Quick settle ৳2,900** or a row’s **Record payment** button; the preview updates the outstanding metric and shows a success toast. The supported manual methods are shown as Cash / bKash / Nagad.

## Reporting verification

Choose **Reports**, select a date range, and click **Generate report**. Verify branch sales bars, category summary, gross profit, CSV action and the report access policy. Profit/cost data is clearly marked as primary-admin-only.

## Expected health checks

- `GET /api/health` returns `{"status":"ok"}`.
- `GET /manus-routes.json` returns routes for `/` and `/admin`.
- `pnpm check` passes.
- `pnpm build` passes.
