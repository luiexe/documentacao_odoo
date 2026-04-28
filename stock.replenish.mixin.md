# Product Replenish Mixin — `stock.replenish.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `route_id` **(many2one)** — Preferred Route → `stock.route`
  > Apply specific route for the replenishment instead of product's default routes.
- `allowed_route_ids` **(many2many)** — Allowed Route 🔒 readonly → `stock.route`
- `bom_id` **(many2one)** — Bill of Material → `mrp.bom`
- `supplier_id` **(many2one)** — Vendor → `product.supplierinfo`

## Campos Calculados (readonly)

- `show_bom` **(boolean)** — Show Bom 🔒 readonly
- `show_vendor` **(boolean)** — Show Vendor 🔒 readonly
