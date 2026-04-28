# Expense Split Wizard — `hr.expense.split.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `expense_id` **(many2one)** — Expense ⚠️ obrigatório → `hr.expense`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `expense_split_line_ids` **(one2many)** — Expense Split Line → `hr.expense.split`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `total_amount_currency` **(monetary)** — Total Amount 🔒 readonly
- `total_amount_currency_original` **(monetary)** — Total amount original 🔒 readonly
  > Total amount of the original Expense that we are splitting
- `tax_amount_currency` **(monetary)** — Taxes 🔒 readonly
- `split_possible` **(boolean)** — Split Possible 🔒 readonly
  > The sum of after split shut remain the same
