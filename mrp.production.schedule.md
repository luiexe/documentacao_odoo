# Schedule the production of Product in a warehouse — `mrp.production.schedule`

**Ordenação padrão:** `warehouse_id, mps_sequence, product_id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `warehouse_id` **(many2one)** — Production Warehouse ⚠️ obrigatório → `stock.warehouse`
- `replenish_trigger` **(selection)** — Replenishment Trigger ⚠️ obrigatório
  > Manual: Product to be replenished manually from MPS. Automatic: Product replenished automatically via scheduled action. Never: Product is not replenished from MPS.
  > Opções: `manual` (Manual), `automated` (Automatic), `never` (Never)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `forecast_target_qty` **(float)** — Safety Stock Target
  > This is the minimum free stock you want to keep for that product at all times.
- `min_to_replenish_qty` **(float)** — Minimum to Replenish
  > Unless the demand is 0, Odoo will always at least replenish this quantity.
- `replenish_state` **(selection)** — Replenish State
  > Technical field to support filtering by replenish state
  > Opções: `to_replenish` (To Replenish), `under_replenishment` (Under Replenishment), `excessive_replenishment` (Excessive Replenishment), `low_forecast` (Forecast Too Low)
- `mps_sequence` **(integer)** — Sequence
- `is_indirect` **(boolean)** — Indirect demand product
  > When checked, this product will not appear in the 'To Forecast' filter.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `route_id` **(many2one)** — Preferred Route → `stock.route`
  > Route to replenish your product.
- `allowed_route_ids` **(many2many)** — Allowed Route 🔒 readonly → `stock.route`
- `bom_id` **(many2one)** — Bill of Materials → `mrp.bom`
  > If set, the bill of materials components will also be imported.
- `supplier_id` **(many2one)** — Vendor → `product.supplierinfo`
- `forecast_ids` **(one2many)** — Forecasted quantity at date → `mrp.product.forecast`
- `company_id` **(many2one)** — Company → `res.company`
- `product_tmpl_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `product_category_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `product_uom_id` **(many2one)** — Product UoM 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.

## Campos Calculados (readonly)

- `show_bom` **(boolean)** — Show Bom 🔒 readonly
- `show_vendor` **(boolean)** — Show Vendor 🔒 readonly
- `is_manufacture_route` **(boolean)** — Is Manufacture Route 🔒 readonly
