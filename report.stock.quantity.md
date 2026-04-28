# Stock Quantity Report — `report.stock.quantity`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Date 🔒 readonly
- `state` **(selection)** — State 🔒 readonly
  > Opções: `forecast` (Forecasted Stock), `in` (Forecasted Receipts), `out` (Forecasted Deliveries)
- `product_qty` **(float)** — Quantity 🔒 readonly

## Relacionamentos

- `product_tmpl_id` **(many2one)** — Product Tmpl 🔒 readonly → `product.template`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `warehouse_id` **(many2one)** — Warehouse 🔒 readonly → `stock.warehouse`
