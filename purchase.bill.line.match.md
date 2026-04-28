# Purchase Line and Vendor Bill line matching view — `purchase.bill.line.match`

**Ordenação padrão:** `product_id, aml_id, pol_id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `line_qty` **(float)** — Line Qty 🔒 readonly
- `qty_invoiced` **(float)** — Qty Invoiced 🔒 readonly
- `qty_to_invoice` **(float)** — Qty to invoice 🔒 readonly
- `line_amount_untaxed` **(monetary)** — Line Amount Untaxed 🔒 readonly
- `state` **(char)** — State 🔒 readonly
- `product_uom_qty` **(float)** — Product Uom Qty
- `product_uom_price` **(float)** — Product Uom Price

## Relacionamentos

- `pol_id` **(many2one)** — Pol 🔒 readonly → `purchase.order.line`
- `aml_id` **(many2one)** — Aml 🔒 readonly → `account.move.line`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `line_uom_id` **(many2one)** — Line Uom 🔒 readonly → `uom.uom`
- `purchase_order_id` **(many2one)** — Purchase Order 🔒 readonly → `purchase.order`
- `account_move_id` **(many2one)** — Account Move 🔒 readonly → `account.move`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.

## Campos Calculados (readonly)

- `billed_amount_untaxed` **(monetary)** — Billed Amount Untaxed 🔒 readonly
- `purchase_amount_untaxed` **(monetary)** — Purchase Amount Untaxed 🔒 readonly
- `reference` **(char)** — Reference 🔒 readonly
