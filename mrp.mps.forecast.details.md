# Forecast Demand Details — `mrp.mps.forecast.details`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `move_ids` **(many2many)** — Move 🔒 readonly → `stock.move`
- `purchase_order_line_ids` **(many2many)** — Purchase Order Line 🔒 readonly → `purchase.order.line`

## Campos Calculados (readonly)

- `rfq_qty` **(integer)** — Quantity from RFQ 🔒 readonly
- `moves_qty` **(integer)** — Quantity from Incoming Moves 🔒 readonly
- `manufacture_qty` **(integer)** — Quantity from Manufacturing Order 🔒 readonly
- `total_qty` **(integer)** — Actual Replenishment 🔒 readonly
- `rfq_string` **(char)** — Rfq String 🔒 readonly
- `moves_string` **(char)** — Moves String 🔒 readonly
- `manufacture_string` **(char)** — Manufacture String 🔒 readonly
