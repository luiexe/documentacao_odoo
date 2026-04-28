# Bank Account Allocation Wizard — `hr.bank.account.allocation.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `allocation_ids` **(one2many)** — Allocations → `hr.bank.account.allocation.wizard.line`
