# Sale Order Coupon Points - Keeps track of how a sale order impacts a coupon — `sale.order.coupon.points`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `order_id` **(many2one)** — Order ⚠️ obrigatório → `sale.order`
- `coupon_id` **(many2one)** — Coupon ⚠️ obrigatório → `loyalty.card`
- `points` **(float)** — Points ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
