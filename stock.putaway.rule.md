# Putaway Rule — `stock.putaway.rule`

**Ordenação padrão:** `sequence,product_id`

---

## Campos Obrigatórios

- `location_in_id` **(many2one)** — When product arrives in ⚠️ obrigatório → `stock.location`
- `location_out_id` **(many2one)** — Store to sublocation ⚠️ obrigatório → `stock.location`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Priority
  > Give to the more specialized category, a higher priority to have them in top of the list.
- `active` **(boolean)** — Active
- `sublocation` **(selection)** — Sublocation
  > Opções: `no` (No), `last_used` (Last Used), `closest_location` (Closest Location)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_id` **(many2one)** — Product → `product.product`
- `category_id` **(many2one)** — Product Category → `product.category`
- `package_type_ids` **(many2many)** — Package Type → `stock.package.type`
- `storage_category_id` **(many2one)** — Storage Category → `stock.storage.category`
