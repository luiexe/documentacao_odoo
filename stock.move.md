# Stock Move — `stock.move`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `date` **(datetime)** — Date Scheduled ⚠️ obrigatório
  > Scheduled date until move is done, then date of actual move processing
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `product_uom_qty` **(float)** — Demand ⚠️ obrigatório
  > This is the quantity of product that is planned to be moved.Lowering this quantity does not generate a backorder.Changing this quantity on assigned moves affects the product reservation, and should be done with care.
- `product_uom` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
- `location_id` **(many2one)** — Source Location ⚠️ obrigatório → `stock.location`
  > The operation takes and suggests products from this location.
- `location_dest_id` **(many2one)** — Intermediate Location ⚠️ obrigatório → `stock.location`
  > The operations brings product to this location
- `procure_method` **(selection)** — Supply Method ⚠️ obrigatório
  > By default, the system will take from the stock in the source location and passively wait for availability. The other possibility allows you to directly create a procurement on the source location (and thus ignore its current stock) to gather products. If we want to chain moves and have this one to wait for the previous, this second option should be chosen.
  > Opções: `make_to_stock` (Default: Take From Stock), `make_to_order` (Advanced: Apply Procurement Rules)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `priority` **(selection)** — Priority 🔒 readonly
  > Opções: `0` (Normal), `1` (Urgent)
- `date_deadline` **(datetime)** — Deadline 🔒 readonly
  > In case of outgoing flow, validate the transfer before this date to allow to deliver at promised date to the customer.         In case of incoming flow, validate the transfer before this date in order to have these products in stock at the date promised by the supplier
- `description_picking` **(text)** — Description Of Picking
- `description_picking_manual` **(text)** — Description Picking Manual 🔒 readonly
- `product_qty` **(float)** — Real Quantity
  > Quantity in the default UoM of the product
- `state` **(selection)** — Status 🔒 readonly
  > * New: The stock move is created but not confirmed. * Waiting Another Move: A linked stock move should be done before this one. * Waiting: The stock move is confirmed but the product can't be reserved. * Available: The product of the stock move is reserved. * Done: The product has been transferred and the transfer has been confirmed.
  > Opções: `draft` (New), `waiting` (Waiting Another Move), `confirmed` (Waiting), `partially_available` (Partially Available), `assigned` (Available), `done` (Done), `cancel` (Cancelled)
- `picked` **(boolean)** — Picked
  > This checkbox is just indicative, it doesn't validate or generate any product moves.
- `price_unit` **(float)** — Price Unit
- `origin` **(char)** — Source Document
- `procurement_values` **(json)** — Procurement Values
  > Dummy field to store procurement values to propagate them to later steps
- `propagate_cancel` **(boolean)** — Propagate cancel and split
  > If checked, when this move is cancelled, cancel the linked move too
- `delay_alert_date` **(datetime)** — Delay Alert Date 🔒 readonly
  > Process at this date to be on time
- `is_inventory` **(boolean)** — Inventory
- `inventory_name` **(char)** — Inventory Name 🔒 readonly
- `quantity` **(float)** — Quantity
- `additional` **(boolean)** — Whether the move was added after the picking's confirmation
- `reference` **(char)** — Reference 🔒 readonly
- `next_serial` **(char)** — First SN/Lot
- `next_serial_count` **(integer)** — Number of SN/Lots
- `reservation_date` **(date)** — Date to Reserve 🔒 readonly
  > Computes when a move should be reserved
- `packaging_uom_qty` **(float)** — Packaging Quantity 🔒 readonly
  > Quantity in the packaging unit
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `unit_factor` **(float)** — Unit Factor 🔒 readonly
- `cost_share` **(float)** — Cost Share (%)
  > The percentage of the final production cost for this by-product. The total of all by-products' cost share must be smaller or equal to 100.
- `manual_consumption` **(boolean)** — Manual Consumption
  > When activated, then the registration of consumption for that component is recorded manually exclusively. If not activated, and any of the components consumption is edited manually on the manufacturing order, Odoo assumes manual consumption also.
- `to_refund` **(boolean)** — Update quantities on SO/PO
  > Trigger a decrease of the delivered/received quantity in the associated Sale Order/Purchase Order
- `value` **(monetary)** — Value
  > The current value of the move. It's zero if the move is not valued.
- `value_manual` **(monetary)** — Manual Value
- `is_in` **(boolean)** — Is Incoming (valued) 🔒 readonly
- `is_out` **(boolean)** — Is Outgoing (valued) 🔒 readonly
- `is_dropship` **(boolean)** — Is Dropship 🔒 readonly
- `is_subcontract` **(boolean)** — The move is a subcontract receipt
- `weight` **(float)** — Weight 🔒 readonly

## Relacionamentos

- `product_category_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `never_product_template_attribute_value_ids` **(many2many)** — Never attribute Values → `product.template.attribute.value`
- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `product_tmpl_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `location_final_id` **(many2one)** — Final Location → `stock.location`
  > The operation brings the products to the intermediate location.But this operation is part of a chain of operations targeting the final location.
- `partner_id` **(many2one)** — Destination Address  → `res.partner`
  > Optional address where goods are to be delivered, specifically used for allotment
- `move_dest_ids` **(many2many)** — Destination Moves → `stock.move`
  > Optional: next stock move when chaining them
- `move_orig_ids` **(many2many)** — Original Move → `stock.move`
  > Optional: previous stock move when chaining them
- `picking_id` **(many2one)** — Transfer → `stock.picking`
- `scrap_id` **(many2one)** — Scrap operation 🔒 readonly → `stock.scrap`
- `reference_ids` **(many2many)** — References → `stock.reference`
- `rule_id` **(many2one)** — Stock Rule → `stock.rule`
  > The stock rule that created this stock move
- `picking_type_id` **(many2one)** — Operation Type → `stock.picking.type`
- `move_line_ids` **(one2many)** — Move Line → `stock.move.line`
- `package_ids` **(one2many)** — Packages 🔒 readonly → `stock.package`
- `origin_returned_move_id` **(many2one)** — Origin return move → `stock.move`
  > Move that created the return move
- `returned_move_ids` **(one2many)** — All returned moves → `stock.move`
  > Optional: all returned moves created from this move
- `restrict_partner_id` **(many2one)** — Owner  → `res.partner`
- `route_ids` **(many2many)** — Destination route → `stock.route`
  > Preferred route
- `warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`
  > the warehouse to consider for the route selection on the next procurement (if any).
- `orderpoint_id` **(many2one)** — Original Reordering Rule → `stock.warehouse.orderpoint`
- `lot_ids` **(many2many)** — Serial Numbers → `stock.lot`
- `packaging_uom_id` **(many2one)** — Packaging 🔒 readonly → `uom.uom`
  > Packaging unit from sale or purchase orders
- `created_production_id` **(many2one)** — Created Production Order → `mrp.production`
- `production_id` **(many2one)** — Production Order for finished products → `mrp.production`
- `raw_material_production_id` **(many2one)** — Production Order for components → `mrp.production`
- `production_group_id` **(many2one)** — Used for Productions → `mrp.production.group`
- `unbuild_id` **(many2one)** — Disassembly Order → `mrp.unbuild`
- `consume_unbuild_id` **(many2one)** — Consumed Disassembly Order → `mrp.unbuild`
- `allowed_operation_ids` **(one2many)** — Operations 🔒 readonly → `mrp.routing.workcenter`
- `operation_id` **(many2one)** — Operation To Consume → `mrp.routing.workcenter`
- `workorder_id` **(many2one)** — Work Order To Consume → `mrp.workorder`
- `bom_line_id` **(many2one)** — BoM Line → `mrp.bom.line`
- `byproduct_id` **(many2one)** — By-products → `mrp.bom.byproduct`
  > By-product line that generated the move in a manufacturing order
- `order_finished_lot_ids` **(many2many)** — Finished Lot/Serial Number 🔒 readonly → `stock.lot`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `analytic_account_line_ids` **(many2many)** — Analytic Account Line → `account.analytic.line`
- `account_move_id` **(many2one)** — stock_move_id → `account.move`
- `check_id` **(one2many)** — Check → `quality.check`
- `move_line_ids_picked` **(one2many)** — Move Line Ids Picked → `stock.move.line`
- `purchase_line_id` **(many2one)** — Purchase Order Line 🔒 readonly → `purchase.order.line`
- `created_purchase_line_ids` **(many2many)** — Created Purchase Order Lines → `purchase.order.line`
- `sale_line_id` **(many2one)** — Sale Line → `sale.order.line`

## Campos Calculados (readonly)

- `location_usage` **(selection)** — Source Location Type 🔒 readonly
  > * Vendor: Virtual location representing the source location for products coming from your vendors * Virtual: Virtual location used to create a hierarchical structure for your warehouse by aggregating its child locations. Can't directly contain products * Internal: Physical locations inside your warehouses, * Customer: Virtual location representing the destination location for products sent to your customers * Inventory Loss: Virtual location serving as the counterpart for inventory operations done to correct stock levels (Physical inventories) * Production: Virtual counterpart location for production operations. I.e. This location consumes components and produces finished products * Transit: Counterpart location that should be used for inter-company or inter-warehouses operations
  > Opções: `supplier` (Vendor), `view` (Virtual), `internal` (Internal), `customer` (Customer), `inventory` (Inventory Loss), `production` (Production), `transit` (Transit)
- `location_dest_usage` **(selection)** — Destination Location Type 🔒 readonly
  > * Vendor: Virtual location representing the source location for products coming from your vendors * Virtual: Virtual location used to create a hierarchical structure for your warehouse by aggregating its child locations. Can't directly contain products * Internal: Physical locations inside your warehouses, * Customer: Virtual location representing the destination location for products sent to your customers * Inventory Loss: Virtual location serving as the counterpart for inventory operations done to correct stock levels (Physical inventories) * Production: Virtual counterpart location for production operations. I.e. This location consumes components and produces finished products * Transit: Counterpart location that should be used for inter-company or inter-warehouses operations
  > Opções: `supplier` (Vendor), `view` (Virtual), `internal` (Internal), `customer` (Customer), `inventory` (Inventory Loss), `production` (Production), `transit` (Transit)
- `availability` **(float)** — Forecasted Quantity 🔒 readonly
  > Quantity in stock that can still be reserved for this move
- `has_tracking` **(selection)** — Product with Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `has_lines_without_result_package` **(boolean)** — Has Lines Without Result Package 🔒 readonly
- `show_operations` **(boolean)** — Show Detailed Operations 🔒 readonly
  > If this checkbox is ticked, the pickings lines will represent detailed stock operations. If not, the picking lines will represent an aggregate of detailed stock operations.
- `picking_code` **(selection)** — Type of Operation 🔒 readonly
  > Opções: `incoming` (Receipt), `outgoing` (Delivery), `internal` (Internal Transfer), `mrp_operation` (Manufacturing)
- `show_details_visible` **(boolean)** — Details Visible 🔒 readonly
- `is_storable` **(boolean)** — Track Inventory 🔒 readonly
  > A storable product is a product for which you manage stock.
- `is_locked` **(boolean)** — Is Locked 🔒 readonly
- `is_initial_demand_editable` **(boolean)** — Is initial demand editable 🔒 readonly
- `is_date_editable` **(boolean)** — Is Date Editable 🔒 readonly
- `is_quantity_done_editable` **(boolean)** — Is quantity done editable 🔒 readonly
- `move_lines_count` **(integer)** — Move Lines Count 🔒 readonly
- `display_assign_serial` **(boolean)** — Display Assign Serial 🔒 readonly
- `display_import_lot` **(boolean)** — Display Import Lot 🔒 readonly
- `forecast_availability` **(float)** — Forecast Availability 🔒 readonly
- `forecast_expected_date` **(datetime)** — Forecasted Expected date 🔒 readonly
- `show_quant` **(boolean)** — Show Quant 🔒 readonly
- `show_lots_m2o` **(boolean)** — Show lot_id 🔒 readonly
- `show_lots_text` **(boolean)** — Show lot_name 🔒 readonly
- `should_consume_qty` **(float)** — Quantity To Consume 🔒 readonly
- `product_qty_available` **(float)** — Product On Hand Quantity 🔒 readonly
  > Current quantity of products. In a context with a single Stock Location, this includes goods stored at this Location, or any of its children. In a context with a single Warehouse, this includes goods stored in the Stock Location of this Warehouse, or any of its children. stored in the Stock Location of the Warehouse of this Shop, or any of its children. Otherwise, this includes goods stored in any Stock Location with 'internal' type.
- `product_virtual_available` **(float)** — Product Forecasted Quantity 🔒 readonly
  > Forecast quantity (computed as Quantity On Hand - Outgoing + Incoming) In a context with a single Stock Location, this includes goods stored in this location, or any of its children. In a context with a single Warehouse, this includes goods stored in the Stock Location of this Warehouse, or any of its children. Otherwise, this includes goods stored in any Stock Location with 'internal' type.
- `value_justification` **(text)** — Value Description 🔒 readonly
- `value_computed_justification` **(text)** — Computed Value Description 🔒 readonly
- `standard_price` **(float)** — Standard Price 🔒 readonly
- `is_valued` **(boolean)** — Is Valued 🔒 readonly
- `remaining_qty` **(float)** — Remaining Quantity 🔒 readonly
- `remaining_value` **(monetary)** — Remaining Value 🔒 readonly
- `show_subcontracting_details_visible` **(boolean)** — Show Subcontracting Details Visible 🔒 readonly
- `note` **(html)** — Note 🔒 readonly
- `worksheet_document` **(binary)** — Worksheet Image/PDF 🔒 readonly
- `product_barcode` **(char)** — Barcode 🔒 readonly
  > International Article Number used for product identification.
- `picking_type_prefill_shop_floor_lots` **(boolean)** — Pre fill lot/serial numbers in shop floor moves  🔒 readonly
  > When enabled, reserved lots for component moves will be displayed in the shop floor. When disabled, lots will always need to be selected manually when processing components in the shop floor.
