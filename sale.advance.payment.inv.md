# Sales Advance Payment Invoice — `sale.advance.payment.inv`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `advance_payment_method` **(selection)** — Create Invoice ⚠️ obrigatório
  > A standard invoice is issued with all the order lines ready for invoicing,according to their invoicing policy (based on ordered or delivered quantity).
  > Opções: `delivered` (Regular invoice), `percentage` (Down payment (percentage)), `fixed` (Down payment (fixed amount))

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `deduct_down_payments` **(boolean)** — Deduct down payments
- `amount` **(float)** — Down Payment
  > The percentage of amount to be invoiced in advance.
- `fixed_amount` **(monetary)** — Down Payment Amount (Fixed)
  > The fixed amount to be invoiced in advance.
- `consolidated_billing` **(boolean)** — Consolidated Billing
  > Create one invoice for all orders related to same customer, same invoicing address and same delivery address.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `date_start_invoice_timesheet` **(date)** — Start Date
  > Only timesheets not yet invoiced (and validated, if applicable) from this period will be invoiced. If the period is not indicated, all timesheets not yet invoiced (and validated, if applicable) will be invoiced without distinction.
- `date_end_invoice_timesheet` **(date)** — End Date
  > Only timesheets not yet invoiced (and validated, if applicable) from this period will be invoiced. If the period is not indicated, all timesheets not yet invoiced (and validated, if applicable) will be invoiced without distinction.
- `invoicing_timesheet_enabled` **(boolean)** — Invoicing Timesheet Enabled 🔒 readonly

## Relacionamentos

- `sale_order_ids` **(many2many)** — Sale Order → `sale.order`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `count` **(integer)** — Order Count 🔒 readonly
- `has_down_payments` **(boolean)** — Has down payments 🔒 readonly
- `amount_invoiced` **(monetary)** — Already invoiced 🔒 readonly
  > Only confirmed down payments are considered.
- `display_draft_invoice_warning` **(boolean)** — Display Draft Invoice Warning 🔒 readonly
- `has_timer_running` **(boolean)** — Has Timer Running 🔒 readonly
