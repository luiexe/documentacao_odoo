# Invoices Statistics — `account.invoice.report`

**Ordenação padrão:** `invoice_date desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `move_type` **(selection)** — Move Type 🔒 readonly
  > Opções: `out_invoice` (Customer Invoice), `in_invoice` (Vendor Bill), `out_refund` (Customer Credit Note), `in_refund` (Vendor Credit Note)
- `state` **(selection)** — Invoice Status 🔒 readonly
  > Opções: `draft` (Draft), `posted` (Open), `cancel` (Cancelled)
- `payment_state` **(selection)** — Payment Status 🔒 readonly
  > Opções: `not_paid` (Not Paid), `in_payment` (In Payment), `paid` (Paid), `partial` (Partially Paid), `reversed` (Reversed), `blocked` (Blocked), `invoicing_legacy` (Invoicing App Legacy)
- `invoice_date` **(date)** — Invoice Date 🔒 readonly
- `quantity` **(float)** — Product Quantity 🔒 readonly
- `invoice_date_due` **(date)** — Due Date 🔒 readonly
- `price_subtotal_currency` **(float)** — Untaxed Amount in Currency 🔒 readonly
- `price_subtotal` **(float)** — Untaxed Amount 🔒 readonly
- `price_total` **(float)** — Total 🔒 readonly
- `price_total_currency` **(float)** — Total in Currency 🔒 readonly
- `price_average` **(float)** — Average Price 🔒 readonly
- `price_margin` **(float)** — Margin 🔒 readonly
- `inventory_value` **(float)** — Inventory Value 🔒 readonly

## Relacionamentos

- `move_id` **(many2one)** — Move 🔒 readonly → `account.move`
- `journal_id` **(many2one)** — Journal 🔒 readonly → `account.journal`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
- `commercial_partner_id` **(many2one)** — Main Partner → `res.partner`
- `country_id` **(many2one)** — Country → `res.country`
- `invoice_user_id` **(many2one)** — Salesperson 🔒 readonly → `res.users`
- `fiscal_position_id` **(many2one)** — Fiscal Position 🔒 readonly → `account.fiscal.position`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
- `product_categ_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `account_id` **(many2one)** — Revenue/Expense Account 🔒 readonly → `account.account`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `l10n_latam_document_type_id` **(many2one)** — Document Type → `l10n_latam.document.type`
- `team_id` **(many2one)** — Sales Team → `crm.team`
