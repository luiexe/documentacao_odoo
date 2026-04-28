# Return Picking Line — `stock.return.picking.line`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `quantity` **(float)** — Quantity ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `to_refund` **(boolean)** — Update quantities on SO/PO
  > Trigger a decrease of the delivered/received quantity in the associated Sale Order/Purchase Order

## Relacionamentos

- `uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
- `wizard_id` **(many2one)** — Wizard → `stock.return.picking`
- `move_id` **(many2one)** — Move → `stock.move`

## Campos Calculados (readonly)

- `move_quantity` **(float)** — Move Quantity 🔒 readonly
