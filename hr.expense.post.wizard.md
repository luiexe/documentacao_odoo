# Expense Posting Wizard — `hr.expense.post.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `accounting_date` **(date)** — Accounting Date
  > Specify the bill date of the related vendor bill.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `employee_journal_id` **(many2one)** — Journal → `account.journal`
  > The journal used when the expense is paid by employee.
