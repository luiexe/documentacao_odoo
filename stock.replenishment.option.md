# Stock warehouse replenishment option — `stock.replenishment.option`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `route_id` **(many2one)** — Route → `stock.route`
- `product_id` **(many2one)** — Product → `product.product`
- `replenishment_info_id` **(many2one)** — Replenishment Info → `stock.replenishment.info`
- `location_id` **(many2one)** — Location Stock 🔒 readonly → `stock.location`
- `warehouse_id` **(many2one)** — Supplying Warehouse 🔒 readonly → `stock.warehouse`

## Campos Calculados (readonly)

- `uom` **(char)** — Unit Name 🔒 readonly
- `qty_to_order` **(float)** — To Order 🔒 readonly
- `free_qty` **(float)** — Free Qty 🔒 readonly
- `lead_time` **(char)** — Lead Time 🔒 readonly
- `warning_message` **(char)** — Warning Message 🔒 readonly
