# Conflict in Inventory — `stock.inventory.conflict`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `quant_ids` **(many2many)** — Quants → `stock.quant`
- `quant_to_fix_ids` **(many2many)** — Conflicts → `stock.quant`
