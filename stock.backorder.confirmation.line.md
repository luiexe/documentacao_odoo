# Backorder Confirmation Line — `stock.backorder.confirmation.line`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `to_backorder` **(boolean)** — To Backorder
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `backorder_confirmation_id` **(many2one)** — Immediate Transfer → `stock.backorder.confirmation`
- `picking_id` **(many2one)** — Transfer → `stock.picking`
