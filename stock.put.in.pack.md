# Put In Pack Wizard — `stock.put.in.pack`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `shipping_weight` **(float)** — Shipping Weight
- `package_carrier_type` **(char)** — Carrier Type

## Relacionamentos

- `location_dest_id` **(many2one)** — Destination → `stock.location`
- `move_line_ids` **(many2many)** — Move lines → `stock.move.line`
- `package_ids` **(many2many)** — Packages → `stock.package`
- `package_type_id` **(many2one)** — Package Type → `stock.package.type`
- `package_type_sequence_id` **(many2one)** — Reference Sequence 🔒 readonly → `ir.sequence`
- `result_package_id` **(many2one)** — Package → `stock.package`
- `origin_package_ids` **(many2many)** — Origin Package 🔒 readonly → `stock.package`

## Campos Calculados (readonly)

- `weight_uom_name` **(char)** — Weight unit of measure label 🔒 readonly
