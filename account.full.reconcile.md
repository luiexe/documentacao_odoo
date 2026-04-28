# Full Reconcile — `account.full.reconcile`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partial_reconcile_ids` **(one2many)** — Reconciliation Parts → `account.partial.reconcile`
- `reconciled_line_ids` **(one2many)** — Matched Journal Items → `account.move.line`
