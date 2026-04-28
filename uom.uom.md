# Product Unit of Measure — `uom.uom`

**Ordenação padrão:** `sequence, relative_uom_id, id`

---

## Campos Obrigatórios

- `name` **(char)** — Unit Name ⚠️ obrigatório
- `relative_factor` **(float)** — Contains ⚠️ obrigatório
  > How much bigger or smaller this unit is compared to the reference UoM for this unit

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
  > Uncheck the active field to disable a unit of measure without deleting it.
- `factor` **(float)** — Absolute Quantity 🔒 readonly
- `parent_path` **(char)** — Parent Path
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `timesheet_widget` **(char)** — Widget

## Relacionamentos

- `relative_uom_id` **(many2one)** — Reference Unit → `uom.uom`
- `related_uom_ids` **(one2many)** — Related UoMs → `uom.uom`
- `product_uom_ids` **(one2many)** — Barcodes → `product.uom`
- `package_type_id` **(many2one)** — Package Type → `stock.package.type`
- `route_ids` **(many2many)** — Routes 🔒 readonly → `stock.route`
  > Routes propagated from the package type

## Campos Calculados (readonly)

- `rounding` **(float)** — Rounding Precision 🔒 readonly
- `fiscal_country_codes` **(char)** — Fiscal Country Codes 🔒 readonly
