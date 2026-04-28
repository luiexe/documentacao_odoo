# Payment Terms — `account.payment.term`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Payment Terms ⚠️ obrigatório
- `sequence` **(integer)** — Sequence ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If the active field is set to False, it will allow you to hide the payment terms without removing it.
- `note` **(html)** — Description on the Invoice
- `display_on_invoice` **(boolean)** — Show installment dates
- `example_date` **(date)** — Date example
- `discount_percentage` **(float)** — Discount %
  > Early Payment Discount granted for this payment term
- `discount_days` **(integer)** — Discount Days
  > Number of days before the early payment proposition expires
- `early_pay_discount_computation` **(selection)** — Cash Discount Tax Reduction
  > Opções: `included` (On early payment), `excluded` (Never), `mixed` (Always (upon invoice))
- `early_discount` **(boolean)** — Early Discount
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `line_ids` **(one2many)** — Terms → `account.payment.term.line`
- `company_id` **(many2one)** — Company → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `fiscal_country_codes` **(char)** — Fiscal Country Codes 🔒 readonly
- `example_amount` **(monetary)** — Example Amount 🔒 readonly
- `example_invalid` **(boolean)** — Example Invalid 🔒 readonly
- `example_preview` **(html)** — Example Preview 🔒 readonly
- `example_preview_discount` **(html)** — Example Preview Discount 🔒 readonly
