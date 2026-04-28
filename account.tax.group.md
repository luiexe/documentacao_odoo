# Tax Group — `account.tax.group`

**Ordenação padrão:** `sequence asc, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `preceding_subtotal` **(char)** — Preceding Subtotal
  > If set, this value will be used on documents as the label of a subtotal excluding this tax group before displaying it. If not set, the tax group will be displayed after the 'Untaxed amount' subtotal.
- `pos_receipt_label` **(char)** — PoS receipt label
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `tax_payable_account_id` **(many2one)** — Tax Payable Account → `account.account`
  > Tax current account used as a counterpart to the Tax Closing Entry when in favor of the authorities.
- `tax_receivable_account_id` **(many2one)** — Tax Receivable Account → `account.account`
  > Tax current account used as a counterpart to the Tax Closing Entry when in favor of the company.
- `advance_tax_payment_account_id` **(many2one)** — Tax Advance Account → `account.account`
  > Downpayments posted on this account will be considered by the Tax Closing Entry.
- `country_id` **(many2one)** — Country → `res.country`
  > The country for which this tax group is applicable.

## Campos Calculados (readonly)

- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
