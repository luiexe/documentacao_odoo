# Warn Insufficient Quantity — `stock.warn.insufficient.qty`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `location_id` **(many2one)** — Location ⚠️ obrigatório → `stock.location`
- `quantity` **(float)** — Quantity ⚠️ obrigatório
- `product_uom_name` **(char)** — Unit ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `quant_ids` **(many2many)** — Quant 🔒 readonly → `stock.quant`
