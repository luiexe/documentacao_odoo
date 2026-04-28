# Partial Reconcile — `account.partial.reconcile`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `debit_move_id` **(many2one)** — Debit Move ⚠️ obrigatório → `account.move.line`
- `credit_move_id` **(many2one)** — Credit Move ⚠️ obrigatório → `account.move.line`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `draft_caba_move_vals` **(json)** — Values that created the draft cash-basis entry
- `amount` **(monetary)** — Amount
  > Always positive amount concerned by this matching expressed in the company currency.
- `debit_amount_currency` **(monetary)** — Debit Amount Currency
  > Always positive amount concerned by this matching expressed in the debit line foreign currency.
- `credit_amount_currency` **(monetary)** — Credit Amount Currency
  > Always positive amount concerned by this matching expressed in the credit line foreign currency.
- `max_date` **(date)** — Max Date of Matched Lines 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `full_reconcile_id` **(many2one)** — Full Reconcile → `account.full.reconcile`
- `exchange_move_id` **(many2one)** — Exchange Move → `account.move`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
  > Utility field to express amount currency
- `debit_currency_id` **(many2one)** — Currency of the debit journal item. 🔒 readonly → `res.currency`
- `credit_currency_id` **(many2one)** — Currency of the credit journal item. 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company → `res.company`
