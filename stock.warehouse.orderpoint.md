# Minimum Inventory Rule — `stock.warehouse.orderpoint`

**Ordenação padrão:** `location_id,company_id,id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório 🔒 readonly
- `trigger` **(selection)** — Trigger ⚠️ obrigatório
  > Opções: `auto` (Auto), `manual` (Manual)
- `warehouse_id` **(many2one)** — Warehouse ⚠️ obrigatório → `stock.warehouse`
- `location_id` **(many2one)** — Location ⚠️ obrigatório → `stock.location`
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `product_min_qty` **(float)** — Min Quantity ⚠️ obrigatório
  > The minimum Stock level that will trigger a replenishment.
- `product_max_qty` **(float)** — Max Quantity ⚠️ obrigatório
  > Stock level to reach when replenishing.
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If the active field is set to False, it will allow you to hide the orderpoint without removing it.
- `snoozed_until` **(date)** — Snoozed
  > Hidden until next scheduler.
- `qty_to_order` **(float)** — To Order
- `qty_to_order_computed` **(float)** — To Order Computed 🔒 readonly
- `qty_to_order_manual` **(float)** — To Order Manual
- `deadline_date` **(date)** — Deadline 🔒 readonly
  > Date before which you should order to avoid falling below the minimum. If you have nothing to order while a deadline is found, it may be because a future arrival is expected after the minimum quantity is reached (potential stockout). Check the Forecast Report.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_tmpl_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `product_category_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `product_uom` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.
- `allowed_replenishment_uom_ids` **(many2many)** — Allowed Replenishment Uom 🔒 readonly → `uom.uom`
- `replenishment_uom_id` **(many2one)** — Multiple → `uom.uom`
  > The procurement quantity will be rounded up to a multiple of this unit/packaging. If it is not set, it is not rounded.
- `allowed_location_ids` **(one2many)** — Allowed Location 🔒 readonly → `stock.location`
- `rule_ids` **(many2many)** — Rules used 🔒 readonly → `stock.rule`
- `route_id` **(many2one)** — Route → `stock.route`
- `effective_route_id` **(many2one)** — Effective Route 🔒 readonly → `stock.route`
  > Either the route set directly or the one computed to be used by this replenishment
- `bom_id` **(many2one)** — Bill of Materials → `mrp.bom`
- `effective_bom_id` **(many2one)** — Effective Bill of Materials 🔒 readonly → `mrp.bom`
  > Either the Bill of Materials set directly or the one computed to be used by this replenishment
- `supplier_id` **(many2one)** — Vendor Pricelist → `product.supplierinfo`
- `vendor_ids` **(one2many)** — Vendors 🔒 readonly → `product.supplierinfo`
- `effective_vendor_id` **(many2one)** — Effective Vendor 🔒 readonly → `res.partner`
  > Either the vendor set directly or the one computed to be used by this replenishment
- `available_vendor` **(many2one)** — Available Vendor → `res.partner`
  > Any vendor on the product's pricelist

## Campos Calculados (readonly)

- `product_uom_name` **(char)** — Product unit of measure label 🔒 readonly
- `replenishment_uom_id_placeholder` **(char)** — Replenishment Uom Id Placeholder 🔒 readonly
- `lead_horizon_date` **(date)** — Lead Horizon Date 🔒 readonly
- `lead_days` **(float)** — Lead Days 🔒 readonly
- `route_id_placeholder` **(char)** — Route Id Placeholder 🔒 readonly
- `qty_on_hand` **(float)** — On Hand 🔒 readonly
- `qty_forecast` **(float)** — Forecast 🔒 readonly
- `days_to_order` **(float)** — Days To Order 🔒 readonly
  > Numbers of days  in advance that replenishments demands are created.
- `unwanted_replenish` **(boolean)** — Unwanted Replenish 🔒 readonly
- `show_supply_warning` **(boolean)** — Show Supply Warning 🔒 readonly
- `show_bom` **(boolean)** — Show BoM column 🔒 readonly
- `bom_id_placeholder` **(char)** — Bom Id Placeholder 🔒 readonly
- `show_supplier` **(boolean)** — Show supplier column 🔒 readonly
- `supplier_id_placeholder` **(char)** — Supplier Id Placeholder 🔒 readonly
