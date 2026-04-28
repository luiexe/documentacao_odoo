# Inventory Routes — `stock.route`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Route ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If the active field is set to False, it will allow you to hide the route without removing it.
- `sequence` **(integer)** — Sequence
- `product_selectable` **(boolean)** — Applicable on Product
  > When checked, the route will be selectable in the Inventory tab of the Product form.
- `product_categ_selectable` **(boolean)** — Applicable on Product Category
  > When checked, the route will be selectable on the Product Category.
- `warehouse_selectable` **(boolean)** — Applicable on Warehouse
  > When a warehouse is selected for this route, this route should be seen as the default route when products pass through this warehouse.
- `package_type_selectable` **(boolean)** — Applicable on Package Type
  > When checked, the route will be selectable on package types
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `sale_selectable` **(boolean)** — Selectable on Sales Order Line
- `shipping_selectable` **(boolean)** — Applicable on Shipping Methods

## Relacionamentos

- `rule_ids` **(one2many)** — Rules → `stock.rule`
- `supplied_wh_id` **(many2one)** — Supplied Warehouse → `stock.warehouse`
- `supplier_wh_id` **(many2one)** — Supplying Warehouse → `stock.warehouse`
- `company_id` **(many2one)** — Company → `res.company`
  > Leave this field empty if this route is shared between all companies
- `product_ids` **(many2many)** — Products → `product.template`
- `categ_ids` **(many2many)** — Product Categories → `product.category`
- `warehouse_domain_ids` **(one2many)** — Warehouse Domain 🔒 readonly → `stock.warehouse`
- `warehouse_ids` **(many2many)** — Warehouses → `stock.warehouse`
