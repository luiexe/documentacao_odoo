# Scrap — `stock.scrap`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Reference ⚠️ obrigatório 🔒 readonly
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
- `location_id` **(many2one)** — Source Location ⚠️ obrigatório → `stock.location`
- `scrap_location_id` **(many2one)** — Scrap Location ⚠️ obrigatório → `stock.location`
- `scrap_qty` **(float)** — Quantity ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `_barcode_scanned` **(char)** — Barcode Scanned
  > Value of the last barcode scanned.
- `origin` **(char)** — Source Document
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Draft), `done` (Done)
- `date_done` **(datetime)** — Date 🔒 readonly
- `should_replenish` **(boolean)** — Replenish Quantities
  > Trigger replenishment for scrapped products
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `product_barcode` **(char)** — Barcode
  > International Article Number used for product identification.

## Relacionamentos

- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `lot_id` **(many2one)** — Lot/Serial → `stock.lot`
- `package_id` **(many2one)** — Package → `stock.package`
- `owner_id` **(many2one)** — Owner → `res.partner`
- `move_ids` **(one2many)** — Move → `stock.move`
- `picking_id` **(many2one)** — Picking → `stock.picking`
- `scrap_reason_tag_ids` **(many2many)** — Scrap Reason → `stock.scrap.reason.tag`
- `production_id` **(many2one)** — Manufacturing Order → `mrp.production`
- `workorder_id` **(many2one)** — Work Order → `mrp.workorder`
- `product_template` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `bom_id` **(many2one)** — Kit → `mrp.bom`

## Campos Calculados (readonly)

- `tracking` **(selection)** — Product Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `product_is_kit` **(boolean)** — Is Kits 🔒 readonly
