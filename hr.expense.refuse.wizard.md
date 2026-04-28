# Expense Refuse Reason Wizard — `hr.expense.refuse.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `reason` **(char)** — Reason ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `expense_ids` **(many2many)** — Expense → `hr.expense`
