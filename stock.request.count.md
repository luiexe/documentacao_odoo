# Stock Request an Inventory Count — `stock.request.count`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `inventory_date` **(date)** — Scheduled at ⚠️ obrigatório
  > Choose a date to get the inventory at that date

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `show_expected_quantity` **(boolean)** — Show Expected Quantity
  > If the user can see the expected quantity or not
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — Assign to → `res.users`
- `quant_ids` **(many2many)** — Quant → `stock.quant`
