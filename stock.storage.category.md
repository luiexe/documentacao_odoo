# Storage Category — `stock.storage.category`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Storage Category ⚠️ obrigatório
- `allow_new_product` **(selection)** — Allow New Product ⚠️ obrigatório
  > Opções: `empty` (If the location is empty), `same` (If all products are same), `mixed` (Allow mixed products)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `max_weight` **(float)** — Max Weight
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `capacity_ids` **(one2many)** — Capacity → `stock.storage.category.capacity`
- `product_capacity_ids` **(one2many)** — Product Capacity → `stock.storage.category.capacity`
- `package_capacity_ids` **(one2many)** — Package Capacity → `stock.storage.category.capacity`
- `location_ids` **(one2many)** — Location → `stock.location`
- `company_id` **(many2one)** — Company → `res.company`

## Campos Calculados (readonly)

- `weight_uom_name` **(char)** — Weight unit 🔒 readonly
