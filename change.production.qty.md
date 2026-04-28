# Change Production Qty — `change.production.qty`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mo_id` **(many2one)** — Manufacturing Order ⚠️ obrigatório → `mrp.production`
- `product_qty` **(float)** — Quantity To Produce ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
