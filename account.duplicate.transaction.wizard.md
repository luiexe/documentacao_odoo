# Wizard for duplicate transactions — `account.duplicate.transaction.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Starting Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `journal_id` **(many2one)** — Journal → `account.journal`
- `transaction_ids` **(one2many)** — Transaction 🔒 readonly → `account.bank.statement.line`
- `provider_duplicate_ids` **(one2many)** — Provider Duplicate 🔒 readonly → `account.bank.statement.line`

## Campos Calculados (readonly)

- `first_ids_in_group` **(json)** — First Ids In Group 🔒 readonly
