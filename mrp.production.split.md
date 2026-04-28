# Wizard to Split a Production — `mrp.production.split`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `max_batch_size` **(float)** — Max Batch Size
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `production_split_multi_id` **(many2one)** — Split Productions → `mrp.production.split.multi`
- `production_id` **(many2one)** — Manufacturing Order 🔒 readonly → `mrp.production`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
- `production_detailed_vals_ids` **(one2many)** — Split Details → `mrp.production.split.line`

## Campos Calculados (readonly)

- `product_qty` **(float)** — Quantity To Produce 🔒 readonly
- `production_capacity` **(float)** — Production Capacity 🔒 readonly
  > Quantity that can be produced with the current stock of components
- `valid_details` **(boolean)** — Valid 🔒 readonly
- `num_splits` **(integer)** — # Splits 🔒 readonly
