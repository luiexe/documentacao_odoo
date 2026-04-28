# Warn Insufficient Unbuild Quantity — `stock.warn.insufficient.qty.unbuild`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `location_id` **(many2one)** — Location ⚠️ obrigatório → `stock.location`
- `quantity` **(float)** — Quantity ⚠️ obrigatório
- `product_uom_name` **(char)** — Unit ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `quant_ids` **(many2many)** — Quant 🔒 readonly → `stock.quant`
- `unbuild_id` **(many2one)** — Unbuild → `mrp.unbuild`
