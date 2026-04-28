# Product Moves (Stock Move Line) — `stock.move.line`

**Ordenação padrão:** `result_package_id desc, id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
- `date` **(datetime)** — Date ⚠️ obrigatório
  > Creation date of this move line until updated due to: quantity being increased, 'picked' status has updated, or move line is done.
- `location_id` **(many2one)** — From ⚠️ obrigatório → `stock.location`
- `location_dest_id` **(many2one)** — To ⚠️ obrigatório → `stock.location`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `quantity` **(float)** — Quantity
- `quantity_product_uom` **(float)** — Quantity in Product UoM 🔒 readonly
- `picked` **(boolean)** — Picked
- `lot_name` **(char)** — Lot/Serial Number Name
- `is_entire_pack` **(boolean)** — Is added through entire package
- `state` **(selection)** — Status 🔒 readonly
  > * New: The stock move is created but not confirmed. * Waiting Another Move: A linked stock move should be done before this one. * Waiting: The stock move is confirmed but the product can't be reserved. * Available: The product of the stock move is reserved. * Done: The product has been transferred and the transfer has been confirmed.
  > Opções: `draft` (New), `waiting` (Waiting Another Move), `confirmed` (Waiting), `partially_available` (Partially Available), `assigned` (Available), `done` (Done), `cancel` (Cancelled)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `location_processed` **(boolean)** — Location Processed
- `dummy_id` **(char)** — Dummy
- `qty_done` **(float)** — Qty Done

## Relacionamentos

- `picking_id` **(many2one)** — Transfer → `stock.picking`
  > The stock operation where the packing has been made
- `move_id` **(many2one)** — Stock Operation → `stock.move`
- `product_id` **(many2one)** — Product → `product.product`
- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `package_id` **(many2one)** — Source Package → `stock.package`
- `lot_id` **(many2one)** — Lot/Serial Number → `stock.lot`
- `result_package_id` **(many2one)** — Destination Package → `stock.package`
  > If set, the operations are packed into this package
- `package_history_id` **(many2one)** — Package History → `stock.package.history`
- `owner_id` **(many2one)** — From Owner → `res.partner`
  > When validating the transfer, the products will be taken from this owner.
- `picking_partner_id` **(many2one)** — Contact 🔒 readonly → `res.partner`
- `move_partner_id` **(many2one)** — Destination Address  🔒 readonly → `res.partner`
  > Optional address where goods are to be delivered, specifically used for allotment
- `picking_type_id` **(many2one)** — Operation type 🔒 readonly → `stock.picking.type`
- `scrap_id` **(many2one)** — Scrap operation 🔒 readonly → `stock.scrap`
- `consume_line_ids` **(many2many)** — Consume Line → `stock.move.line`
- `produce_line_ids` **(many2many)** — Produce Line → `stock.move.line`
- `quant_id` **(many2one)** — Pick From → `stock.quant`
- `picking_location_id` **(many2one)** — Source Location 🔒 readonly → `stock.location`
- `picking_location_dest_id` **(many2one)** — Destination Location 🔒 readonly → `stock.location`
- `workorder_id` **(many2one)** — Work Order → `mrp.workorder`
- `production_id` **(many2one)** — Production Order → `mrp.production`
- `parent_location_id` **(many2one)** — Parent Location 🔒 readonly → `stock.location`
- `parent_location_dest_id` **(many2one)** — Parent Location Dest 🔒 readonly → `stock.location`
- `product_stock_quant_ids` **(one2many)** — Product Stock Quant 🔒 readonly → `stock.quant`
- `packaging_uom_id` **(many2one)** — Packaging Unit of Measure 🔒 readonly → `uom.uom`
  > Packaging unit from sale or purchase orders
- `outermost_result_package_id` **(many2one)** — Outermost Result Package → `stock.package`
- `check_ids` **(one2many)** — Checks → `quality.check`
- `carrier_id` **(many2one)** — Carrier 🔒 readonly → `delivery.carrier`

## Campos Calculados (readonly)

- `product_category_name` **(char)** — Product Category 🔒 readonly
- `result_package_dest_name` **(char)** — Destination Package Name 🔒 readonly
- `scheduled_date` **(datetime)** — Scheduled Date 🔒 readonly
  > Scheduled date until move is done, then date of actual move processing
- `location_usage` **(selection)** — Source Location Type 🔒 readonly
  > * Vendor: Virtual location representing the source location for products coming from your vendors * Virtual: Virtual location used to create a hierarchical structure for your warehouse by aggregating its child locations. Can't directly contain products * Internal: Physical locations inside your warehouses, * Customer: Virtual location representing the destination location for products sent to your customers * Inventory Loss: Virtual location serving as the counterpart for inventory operations done to correct stock levels (Physical inventories) * Production: Virtual counterpart location for production operations. I.e. This location consumes components and produces finished products * Transit: Counterpart location that should be used for inter-company or inter-warehouses operations
  > Opções: `supplier` (Vendor), `view` (Virtual), `internal` (Internal), `customer` (Customer), `inventory` (Inventory Loss), `production` (Production), `transit` (Transit)
- `location_dest_usage` **(selection)** — Destination Location Type 🔒 readonly
  > * Vendor: Virtual location representing the source location for products coming from your vendors * Virtual: Virtual location used to create a hierarchical structure for your warehouse by aggregating its child locations. Can't directly contain products * Internal: Physical locations inside your warehouses, * Customer: Virtual location representing the destination location for products sent to your customers * Inventory Loss: Virtual location serving as the counterpart for inventory operations done to correct stock levels (Physical inventories) * Production: Virtual counterpart location for production operations. I.e. This location consumes components and produces finished products * Transit: Counterpart location that should be used for inter-company or inter-warehouses operations
  > Opções: `supplier` (Vendor), `view` (Virtual), `internal` (Internal), `customer` (Customer), `inventory` (Inventory Loss), `production` (Production), `transit` (Transit)
- `lots_visible` **(boolean)** — Lots Visible 🔒 readonly
- `picking_code` **(selection)** — Type of Operation 🔒 readonly
  > Opções: `incoming` (Receipt), `outgoing` (Delivery), `internal` (Internal Transfer), `mrp_operation` (Manufacturing)
- `picking_type_use_create_lots` **(boolean)** — Create New Lots/Serial Numbers 🔒 readonly
  > If this is checked only, it will suppose you want to create new Lots/Serial Numbers, so you can provide them in a text field. 
- `picking_type_use_existing_lots` **(boolean)** — Use Existing Lots/Serial Numbers 🔒 readonly
  > If this is checked, you will be able to choose the Lots/Serial Numbers. You can also decide to not put lots in this operation type.  This means it will create stock with no lot or not put a restriction on the lot taken. 
- `is_inventory` **(boolean)** — Inventory 🔒 readonly
- `is_locked` **(boolean)** — Is Locked 🔒 readonly
- `reference` **(char)** — Reference 🔒 readonly
- `tracking` **(selection)** — Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `origin` **(char)** — Source 🔒 readonly
- `description_picking` **(text)** — Description Of Picking 🔒 readonly
- `product_barcode` **(char)** — Barcode 🔒 readonly
  > International Article Number used for product identification.
- `formatted_product_barcode` **(char)** — Formatted Product Barcode 🔒 readonly
- `lot_properties` **(properties)** — Properties 🔒 readonly
- `hide_lot_name` **(boolean)** — Hide Lot Name 🔒 readonly
- `hide_lot` **(boolean)** — Hide Lot 🔒 readonly
- `image_1920` **(binary)** — Image 🔒 readonly
- `product_reference_code` **(char)** — Product Reference Code 🔒 readonly
- `electronic_product_code` **(char)** — Electronic Product Code 🔒 readonly
- `packaging_uom_qty` **(float)** — Packaging Quantity 🔒 readonly
  > Quantity in the packaging unit
- `check_state` **(selection)** — Check State 🔒 readonly
  > Opções: `no_checks` (No checks), `in_progress` (Some checks to be done), `pass` (All checks passed), `fail` (Some checks failed)
- `manual_consumption` **(boolean)** — Manual Consumption 🔒 readonly
  > When activated, then the registration of consumption for that component is recorded manually exclusively. If not activated, and any of the components consumption is edited manually on the manufacturing order, Odoo assumes manual consumption also.
- `pick_type_create_components_lots` **(boolean)** — Create New Lots/Serial Numbers for Components 🔒 readonly
  > Allow to create new lot/serial numbers for the components
- `is_subcontract_stock_barcode` **(boolean)** — Is Subcontract Stock Barcode 🔒 readonly
- `sale_price` **(float)** — Sale Price 🔒 readonly
- `destination_country_code` **(char)** — Destination Country 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
