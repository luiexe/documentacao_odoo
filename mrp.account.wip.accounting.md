# Wizard to post Manufacturing WIP account move — `mrp.account.wip.accounting`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `reversal_date` **(date)** — Reversal Date ⚠️ obrigatório
- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Date
- `reference` **(char)** — Reference
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `line_ids` **(one2many)** — WIP accounting lines → `mrp.account.wip.accounting.line`
- `mo_ids` **(many2many)** — Mo → `mrp.production`
