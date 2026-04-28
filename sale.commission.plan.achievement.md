# Commission Plan Achievement — `sale.commission.plan.achievement`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `plan_id` **(many2one)** — Plan ⚠️ obrigatório → `sale.commission.plan`
- `type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `amount_invoiced` (Amount Invoiced), `amount_sold` (Amount Sold), `qty_invoiced` (Quantity Invoiced), `qty_sold` (Quantity Sold), `margin` (Margin)
- `rate` **(float)** — Rate ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_id` **(many2one)** — Product → `product.product`
- `product_categ_id` **(many2one)** — Category → `product.category`
