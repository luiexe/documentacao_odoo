# Warehouse — `stock.warehouse`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `name` **(char)** — Warehouse ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
  > The company is automatically set from your user preferences.
- `view_location_id` **(many2one)** — View Location ⚠️ obrigatório → `stock.location`
- `lot_stock_id` **(many2one)** — Location Stock ⚠️ obrigatório → `stock.location`
- `code` **(char)** — Short Name ⚠️ obrigatório
  > Short name used to identify your warehouse
- `reception_steps` **(selection)** — Incoming Shipments ⚠️ obrigatório
  > Default incoming route to follow
  > Opções: `one_step` (Receive and Store (1 step)), `two_steps` (Receive then Store (2 steps)), `three_steps` (Receive, Quality Control, then Store (3 steps))
- `delivery_steps` **(selection)** — Outgoing Shipments ⚠️ obrigatório
  > Default outgoing route to follow
  > Opções: `ship_only` (Deliver (1 step)), `pick_ship` (Pick then Deliver (2 steps)), `pick_pack_ship` (Pick, Pack, then Deliver (3 steps))
- `manufacture_steps` **(selection)** — Manufacture ⚠️ obrigatório
  > 1 Step: Consume components from stock and produce.               2 Steps: Pick components from stock and then produce.               3 Steps: Pick components from stock, produce, and then move final product(s) from production area to stock.
  > Opções: `mrp_one_step` (Manufacture (1 step)), `pbm` (Pick components then manufacture (2 steps)), `pbm_sam` (Pick components, manufacture, then store products (3 steps))

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
  > Gives the sequence of this line when displaying the warehouses.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `manufacture_to_resupply` **(boolean)** — Manufacture to Resupply
  > When products are manufactured, they can be manufactured in this warehouse.
- `subcontracting_to_resupply` **(boolean)** — Resupply Subcontractors
- `buy_to_resupply` **(boolean)** — Buy to Resupply
  > When products are bought, they can be delivered to this warehouse

## Relacionamentos

- `partner_id` **(many2one)** — Address → `res.partner`
- `route_ids` **(many2many)** — Routes → `stock.route`
  > Defaults routes through the warehouse
- `wh_input_stock_loc_id` **(many2one)** — Input Location → `stock.location`
- `wh_qc_stock_loc_id` **(many2one)** — Quality Control Location → `stock.location`
- `wh_output_stock_loc_id` **(many2one)** — Output Location → `stock.location`
- `wh_pack_stock_loc_id` **(many2one)** — Packing Location → `stock.location`
- `mto_pull_id` **(many2one)** — MTO rule → `stock.rule`
- `pick_type_id` **(many2one)** — Pick Type → `stock.picking.type`
- `pack_type_id` **(many2one)** — Pack Type → `stock.picking.type`
- `out_type_id` **(many2one)** — Out Type → `stock.picking.type`
- `in_type_id` **(many2one)** — In Type → `stock.picking.type`
- `int_type_id` **(many2one)** — Internal Type → `stock.picking.type`
- `qc_type_id` **(many2one)** — Quality Control Type → `stock.picking.type`
- `store_type_id` **(many2one)** — Storage Type → `stock.picking.type`
- `xdock_type_id` **(many2one)** — Cross Dock Type → `stock.picking.type`
- `reception_route_id` **(many2one)** — Receipt Route → `stock.route`
- `delivery_route_id` **(many2one)** — Delivery Route → `stock.route`
- `resupply_wh_ids` **(many2many)** — Resupply From → `stock.warehouse`
  > Routes will be created automatically to resupply this warehouse from the warehouses ticked
- `resupply_route_ids` **(one2many)** — Resupply Routes → `stock.route`
  > Routes will be created for these resupply warehouses and you can select them on products and product categories
- `manufacture_pull_id` **(many2one)** — Manufacture Rule → `stock.rule`
- `manufacture_mto_pull_id` **(many2one)** — Manufacture MTO Rule → `stock.rule`
- `pbm_mto_pull_id` **(many2one)** — Picking Before Manufacturing MTO Rule → `stock.rule`
- `sam_rule_id` **(many2one)** — Stock After Manufacturing Rule → `stock.rule`
- `manu_type_id` **(many2one)** — Manufacturing Operation Type → `stock.picking.type`
- `pbm_type_id` **(many2one)** — Picking Before Manufacturing Operation Type → `stock.picking.type`
- `sam_type_id` **(many2one)** — Stock After Manufacturing Operation Type → `stock.picking.type`
- `pbm_route_id` **(many2one)** — Picking Before Manufacturing Route → `stock.route`
- `pbm_loc_id` **(many2one)** — Picking before Manufacturing Location → `stock.location`
- `sam_loc_id` **(many2one)** — Stock after Manufacturing Location → `stock.location`
- `subcontracting_mto_pull_id` **(many2one)** — Subcontracting MTO Rule → `stock.rule`
- `subcontracting_pull_id` **(many2one)** — Subcontracting MTS Rule → `stock.rule`
- `subcontracting_route_id` **(many2one)** — Resupply Subcontractor → `stock.route`
- `subcontracting_type_id` **(many2one)** — Subcontracting Operation Type → `stock.picking.type`
- `subcontracting_resupply_type_id` **(many2one)** — Subcontracting Resupply Operation Type → `stock.picking.type`
- `buy_pull_id` **(many2one)** — Buy rule → `stock.rule`
- `opening_hours` **(many2one)** — Opening Hours → `resource.calendar`
