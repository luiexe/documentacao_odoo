# Lot/Serial — `stock.lot`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Lot/Serial Number ⚠️ obrigatório
  > Unique Lot/Serial Number
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `ref` **(char)** — Internal Reference
  > Internal reference number in case it differs from the manufacturer's lot/serial number
- `note` **(html)** — Description
- `lot_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `standard_price` **(float)** — Cost
  > Value of the lot (automatically computed in AVCO).         Used to value the product when the purchase cost is not known (e.g. inventory adjustment).         Used to compute margins on sale orders.

## Relacionamentos

- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.
- `quant_ids` **(one2many)** — Quants 🔒 readonly → `stock.quant`
- `company_id` **(many2one)** — Company → `res.company`
- `delivery_ids` **(many2many)** — Transfers 🔒 readonly → `stock.picking`
- `partner_ids` **(many2many)** — Partner 🔒 readonly → `res.partner`
- `location_id` **(many2one)** — Location → `stock.location`
- `company_currency_id` **(many2one)** — Valuation Currency 🔒 readonly → `res.currency`
- `purchase_order_ids` **(many2many)** — Purchase Orders 🔒 readonly → `purchase.order`
- `sale_order_ids` **(many2many)** — Sales Orders 🔒 readonly → `sale.order`

## Campos Calculados (readonly)

- `product_qty` **(float)** — On Hand Quantity 🔒 readonly
- `display_complete` **(boolean)** — Display Complete 🔒 readonly
- `delivery_count` **(integer)** — Delivery order count 🔒 readonly
- `lot_valuated` **(boolean)** — Valuation by Lot/Serial 🔒 readonly
  > If checked, the valuation will be specific by Lot/Serial number.
- `avg_cost` **(monetary)** — Average Cost 🔒 readonly
- `total_value` **(monetary)** — Total Value 🔒 readonly
- `purchase_order_count` **(integer)** — Purchase order count 🔒 readonly
- `quality_check_qty` **(integer)** — Quality Check Qty 🔒 readonly
- `quality_alert_qty` **(integer)** — Quality Alert Qty 🔒 readonly
- `sale_order_count` **(integer)** — Sale order count 🔒 readonly
