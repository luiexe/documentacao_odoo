# Product Replenish — `product.replenish`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `product_tmpl_id` **(many2one)** — Product Template ⚠️ obrigatório → `product.template`
- `product_has_variants` **(boolean)** — Has variants ⚠️ obrigatório
- `product_uom_id` **(many2one)** — Unity of measure ⚠️ obrigatório → `uom.uom`
- `quantity` **(float)** — Quantity ⚠️ obrigatório
- `date_planned` **(datetime)** — Scheduled Date ⚠️ obrigatório
  > Date at which the replenishment should take place.
- `warehouse_id` **(many2one)** — Warehouse ⚠️ obrigatório → `stock.warehouse`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `route_id` **(many2one)** — Preferred Route → `stock.route`
  > Apply specific route for the replenishment instead of product's default routes.
- `allowed_route_ids` **(many2many)** — Allowed Route 🔒 readonly → `stock.route`
- `bom_id` **(many2one)** — Bill of Material → `mrp.bom`
- `supplier_id` **(many2one)** — Vendor → `product.supplierinfo`
- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `forecast_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.
- `company_id` **(many2one)** — Company → `res.company`

## Campos Calculados (readonly)

- `show_bom` **(boolean)** — Show Bom 🔒 readonly
- `show_vendor` **(boolean)** — Show Vendor 🔒 readonly
- `forecasted_quantity` **(float)** — Forecasted Quantity 🔒 readonly
