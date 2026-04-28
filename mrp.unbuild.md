# Unbuild Order — `mrp.unbuild`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `product_qty` **(float)** — Quantity ⚠️ obrigatório
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
- `location_id` **(many2one)** — Source Location ⚠️ obrigatório → `stock.location`
  > Location where the product you want to unbuild is.
- `location_dest_id` **(many2one)** — Destination Location ⚠️ obrigatório → `stock.location`
  > Location where you want to send the components resulting from the unbuild order.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Reference 🔒 readonly
- `state` **(selection)** — Status
  > Opções: `draft` (Draft), `done` (Done)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `bom_id` **(many2one)** — Bill of Material 🔒 readonly → `mrp.bom`
- `mo_id` **(many2one)** — Manufacturing Order → `mrp.production`
- `mo_bom_id` **(many2one)** — Bill of Material used on the Production Order 🔒 readonly → `mrp.bom`
  > Bills of Materials, also called recipes, are used to autocomplete components and work order instructions.
- `lot_producing_ids` **(many2many)** — Lot/Serial Numbers 🔒 readonly → `stock.lot`
- `lot_id` **(many2one)** — Lot/Serial Number → `stock.lot`
- `consume_line_ids` **(one2many)** — Consumed Disassembly Lines 🔒 readonly → `stock.move`
- `produce_line_ids` **(one2many)** — Processed Disassembly Lines 🔒 readonly → `stock.move`

## Campos Calculados (readonly)

- `has_tracking` **(selection)** — Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
