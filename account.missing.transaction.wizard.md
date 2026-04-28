# Wizard for missing transactions — `account.missing.transaction.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Starting Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `journal_id` **(many2one)** — Journal → `account.journal`
