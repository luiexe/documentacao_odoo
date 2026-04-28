# Backorder Confirmation Line — `mrp.production.backorder.line`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mrp_production_backorder_id` **(many2one)** — MO Backorder ⚠️ obrigatório → `mrp.production.backorder`
- `mrp_production_id` **(many2one)** — Manufacturing Order ⚠️ obrigatório 🔒 readonly → `mrp.production`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `to_backorder` **(boolean)** — To Backorder
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
