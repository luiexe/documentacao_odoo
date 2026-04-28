# Account Journal Group — `account.journal.group`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Ledger group ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
  > Define which company can select the multi-ledger in report filters. If none is provided, available for all companies
- `excluded_journal_ids` **(many2many)** — Excluded Journals → `account.journal`
