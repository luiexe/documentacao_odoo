# Product Line — `approval.product.line`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `approval_request_id` **(many2one)** — Approval Request ⚠️ obrigatório → `approval.request`
- `description` **(char)** — Description ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `quantity` **(float)** — Quantity
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `product_id` **(many2one)** — Products → `product.product`
- `product_uom_id` **(many2one)** — Unit → `uom.uom`
- `purchase_order_line_id` **(many2one)** — Purchase Order Line → `purchase.order.line`
- `product_template_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `seller_id` **(many2one)** — Vendors → `product.supplierinfo`
- `warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`

## Campos Calculados (readonly)

- `po_uom_qty` **(float)** — Purchase Unit Quantity 🔒 readonly
  > The quantity converted into the Unit used by the product in Purchase Order.
- `has_no_seller` **(boolean)** — Has No Seller 🔒 readonly
