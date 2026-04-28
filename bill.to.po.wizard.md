# Bill to Purchase Order — `bill.to.po.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `purchase_order_id` **(many2one)** — Purchase Order → `purchase.order`
- `partner_id` **(many2one)** — Partner → `res.partner`
