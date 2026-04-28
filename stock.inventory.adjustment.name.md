# Inventory Adjustment Reference / Reason — `stock.inventory.adjustment.name`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `inventory_adjustment_name` **(char)** — Inventory Reason
- `counting_date` **(datetime)** — Counting Date
  > Date at which the resulting moves will be dated.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `accounting_date` **(date)** — Accounting Date
  > Date at which the accounting entries will be created in case of automated inventory valuation. If empty, the inventory date will be used.

## Relacionamentos

- `quant_ids` **(many2many)** — Quant → `stock.quant`

## Campos Calculados (readonly)

- `should_show_accounting_date` **(boolean)** — Should Show Accounting Date 🔒 readonly
