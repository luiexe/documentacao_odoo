# Accounting Report Budget Item — `account.report.budget.item`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `budget_id` **(many2one)** — Budget ⚠️ obrigatório → `account.report.budget`
- `account_id` **(many2one)** — Account ⚠️ obrigatório → `account.account`
- `date` **(date)** — Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount` **(float)** — Amount
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
