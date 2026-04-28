# Stock Report — `stock.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_done` **(datetime)** — Transfer Date 🔒 readonly
- `creation_date` **(datetime)** — Creation Date 🔒 readonly
- `scheduled_date` **(datetime)** — Expected Date 🔒 readonly
- `delay` **(float)** — Delay (Days) 🔒 readonly
- `cycle_time` **(float)** — Cycle Time (Days) 🔒 readonly
- `picking_type_code` **(selection)** — Type 🔒 readonly
  > Opções: `incoming` (Vendors), `outgoing` (Customers), `internal` (Internal)
- `picking_name` **(char)** — Picking Name 🔒 readonly
- `reference` **(char)** — Reference 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (New), `cancel` (Cancelled), `waiting` (Waiting Another Move), `confirmed` (Waiting Availability), `partially_available` (Partially Available), `assigned` (Available), `done` (Done)
- `is_backorder` **(boolean)** — Is a Backorder 🔒 readonly
- `product_qty` **(float)** — Product Quantity 🔒 readonly
- `is_late` **(boolean)** — Is Late 🔒 readonly

## Relacionamentos

- `operation_type_id` **(many2one)** — Operation Type 🔒 readonly → `stock.picking.type`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `picking_id` **(many2one)** — Transfer Reference 🔒 readonly → `stock.picking`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `categ_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
