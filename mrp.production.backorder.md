# Wizard to mark as done or create back order — `mrp.production.backorder`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `mrp_production_ids` **(many2many)** — Mrp Production → `mrp.production`
- `mrp_production_backorder_line_ids` **(one2many)** — Backorder Confirmation Lines → `mrp.production.backorder.line`

## Campos Calculados (readonly)

- `show_backorder_lines` **(boolean)** — Show backorder lines 🔒 readonly
