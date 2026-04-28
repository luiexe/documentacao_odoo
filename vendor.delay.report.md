# Vendor Delay Report — `vendor.delay.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(datetime)** — Effective Date 🔒 readonly
- `qty_total` **(float)** — Total Quantity 🔒 readonly
- `qty_on_time` **(float)** — On-Time Quantity 🔒 readonly
- `on_time_rate` **(float)** — On-Time Delivery Rate 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Vendor 🔒 readonly → `res.partner`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `category_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
