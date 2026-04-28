# Expense Approve Duplicate — `hr.expense.approve.duplicate`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `expense_ids` **(many2many)** — Expense 🔒 readonly → `hr.expense`
