# Discount Wizard — `sale.order.discount`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `sale_order_id` **(many2one)** — Sale Order ⚠️ obrigatório → `sale.order`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `discount_amount` **(monetary)** — Amount
- `discount_percentage` **(float)** — Percentage
- `discount_type` **(selection)** — Discount Type
  > Opções: `sol_discount` (On All Order Lines), `so_discount` (Global Discount), `amount` (Fixed Amount)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
