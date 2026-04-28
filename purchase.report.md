# Purchase Report — `purchase.report`

**Ordenação padrão:** `date_order desc, price_total desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_order` **(datetime)** — Order Date 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Draft RFQ), `sent` (RFQ Sent), `to approve` (To Approve), `purchase` (Purchase Order), `cancel` (Cancelled)
- `date_approve` **(datetime)** — Confirmation Date 🔒 readonly
- `delay` **(float)** — Days to Confirm 🔒 readonly
  > Amount of time between purchase approval and order by date.
- `delay_pass` **(float)** — Days to Receive 🔒 readonly
  > Amount of time between date planned and order by date for each purchase order line.
- `price_total` **(monetary)** — Total 🔒 readonly
- `price_average` **(monetary)** — Average Cost 🔒 readonly
- `nbr_lines` **(integer)** — # of Lines 🔒 readonly
- `weight` **(float)** — Gross Weight 🔒 readonly
- `volume` **(float)** — Volume 🔒 readonly
- `untaxed_total` **(monetary)** — Untaxed Total 🔒 readonly
- `qty_ordered` **(float)** — Qty Ordered 🔒 readonly
- `qty_received` **(float)** — Qty Received 🔒 readonly
- `qty_billed` **(float)** — Qty Billed 🔒 readonly
- `qty_to_be_billed` **(float)** — Qty to be Billed 🔒 readonly
- `effective_date` **(datetime)** — Effective Date
- `days_to_arrival` **(float)** — Effective Days To Arrival 🔒 readonly

## Relacionamentos

- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `partner_id` **(many2one)** — Vendor 🔒 readonly → `res.partner`
- `product_uom_id` **(many2one)** — Reference Unit of Measure 🔒 readonly → `uom.uom`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `user_id` **(many2one)** — Buyer 🔒 readonly → `res.users`
- `category_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `product_tmpl_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `country_id` **(many2one)** — Partner Country 🔒 readonly → `res.country`
- `fiscal_position_id` **(many2one)** — Fiscal Position 🔒 readonly → `account.fiscal.position`
- `commercial_partner_id` **(many2one)** — Commercial Entity 🔒 readonly → `res.partner`
- `order_id` **(many2one)** — Order 🔒 readonly → `purchase.order`
- `picking_type_id` **(many2one)** — Warehouse 🔒 readonly → `stock.warehouse`
