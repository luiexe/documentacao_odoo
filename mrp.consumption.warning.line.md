# Line of issue consumption — `mrp.consumption.warning.line`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mrp_consumption_warning_id` **(many2one)** — Parent Wizard ⚠️ obrigatório 🔒 readonly → `mrp.consumption.warning`
- `mrp_production_id` **(many2one)** — Manufacturing Order ⚠️ obrigatório 🔒 readonly → `mrp.production`
- `product_id` **(many2one)** — Product ⚠️ obrigatório 🔒 readonly → `product.product`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `product_consumed_qty_uom` **(float)** — Consumed 🔒 readonly
- `product_expected_qty_uom` **(float)** — To Consume 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.

## Campos Calculados (readonly)

- `consumption` **(selection)** — Consumption 🔒 readonly
  > Opções: `flexible` (Allowed), `warning` (Allowed with warning), `strict` (Blocked)
