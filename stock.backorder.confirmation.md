# Backorder Confirmation — `stock.backorder.confirmation`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `show_transfers` **(boolean)** — Show Transfers
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `pick_ids` **(many2many)** — Pick → `stock.picking`
- `backorder_confirmation_line_ids` **(one2many)** — Backorder Confirmation Lines → `stock.backorder.confirmation.line`

## Campos Calculados (readonly)

- `empty_move_count` **(integer)** — Empty Move Count 🔒 readonly
- `partial_move_count` **(integer)** — Partial Move Count 🔒 readonly
