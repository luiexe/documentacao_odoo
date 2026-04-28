# Accrued Orders Wizard — `account.accrued.orders.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`
- `date` **(date)** — Date ⚠️ obrigatório
- `reversal_date` **(date)** — Reversal Date ⚠️ obrigatório
- `account_id` **(many2one)** — Accrual Account ⚠️ obrigatório → `account.account`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount` **(monetary)** — Amount
  > Specify an arbitrary value that will be accrued on a         default account for the entire order, regardless of the products on the different lines.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
  > Utility field to express amount currency

## Campos Calculados (readonly)

- `preview_data` **(text)** — Preview Data 🔒 readonly
- `display_amount` **(boolean)** — Display Amount 🔒 readonly
