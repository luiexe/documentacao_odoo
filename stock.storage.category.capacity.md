# Storage Category Capacity — `stock.storage.category.capacity`

**Ordenação padrão:** `storage_category_id`

---

## Campos Obrigatórios

- `storage_category_id` **(many2one)** — Storage Category ⚠️ obrigatório → `stock.storage.category`
- `quantity` **(float)** — Quantity ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_id` **(many2one)** — Product → `product.product`
- `package_type_id` **(many2one)** — Package Type → `stock.package.type`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
