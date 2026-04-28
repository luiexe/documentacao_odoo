# Account move line to be created when posting WIP account move — `mrp.account.wip.accounting.line`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `label` **(char)** — Label
- `debit` **(monetary)** — Debit
- `credit` **(monetary)** — Credit
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_id` **(many2one)** — Account → `account.account`
- `currency_id` **(many2one)** — Currency → `res.currency`
- `wip_accounting_id` **(many2one)** — WIP accounting wizard → `mrp.account.wip.accounting`
