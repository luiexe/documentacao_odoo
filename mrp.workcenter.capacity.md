# Work Center Capacity — `mrp.workcenter.capacity`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `workcenter_id` **(many2one)** — Work Center ⚠️ obrigatório → `mrp.workcenter`
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `capacity` **(float)** — Capacity
  > Number of pieces that can be produced in parallel for this product or for all, depending on the unit.
- `time_start` **(float)** — Setup Time (minutes)
  > Time in minutes for the setup.
- `time_stop` **(float)** — Cleanup Time (minutes)
  > Time in minutes for the cleaning.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_id` **(many2one)** — Product → `product.product`
