# Multicurrency Revaluation Wizard — `account.multicurrency.revaluation.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`
- `date` **(date)** — Date ⚠️ obrigatório
- `reversal_date` **(date)** — Reversal Date ⚠️ obrigatório
- `expense_provision_account_id` **(many2one)** — Expense Account ⚠️ obrigatório → `account.account`
- `income_provision_account_id` **(many2one)** — Income Account ⚠️ obrigatório → `account.account`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `show_warning_move_id` **(many2one)** — Show Warning Move 🔒 readonly → `account.move`

## Campos Calculados (readonly)

- `preview_data` **(text)** — Preview Data 🔒 readonly
