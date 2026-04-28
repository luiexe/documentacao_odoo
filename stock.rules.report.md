# Stock Rules report — `stock.rules.report`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `product_tmpl_id` **(many2one)** — Product Template ⚠️ obrigatório → `product.template`
- `warehouse_ids` **(many2many)** — Warehouses ⚠️ obrigatório → `stock.warehouse`
  > Show the routes that apply on selected warehouses.
- `product_has_variants` **(boolean)** — Has variants ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `so_route_ids` **(many2many)** — Apply specific routes → `stock.route`
  > Choose to apply SO lines specific routes.
