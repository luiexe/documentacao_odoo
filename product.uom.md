# Link between products and their UoMs — `product.uom`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `barcode` **(char)** — Barcode ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
