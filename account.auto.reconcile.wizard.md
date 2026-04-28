# Account automatic reconciliation wizard — `account.auto.reconcile.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `to_date` **(date)** — To ⚠️ obrigatório
- `search_mode` **(selection)** — Reconcile ⚠️ obrigatório
  > Reconcile journal items with opposite balance or clear accounts with a zero balance
  > Opções: `one_to_one` (Perfect Match), `zero_balance` (Clear Account)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `from_date` **(date)** — From
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `line_ids` **(many2many)** — Line → `account.move.line`
- `account_ids` **(many2many)** — Accounts → `account.account`
- `partner_ids` **(many2many)** — Partners → `res.partner`
