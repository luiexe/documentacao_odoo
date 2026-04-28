# Transfer — `stock.picking`

**Ordenação padrão:** `priority desc, scheduled_date asc, id desc`

---

## Campos Obrigatórios

- `move_type` **(selection)** — Shipping Policy ⚠️ obrigatório
  > It specifies goods to be deliver partially or all at once
  > Opções: `direct` (As soon as possible), `one` (When all products are ready)
- `location_id` **(many2one)** — Source Location ⚠️ obrigatório → `stock.location`
- `location_dest_id` **(many2one)** — Destination Location ⚠️ obrigatório → `stock.location`
- `picking_type_id` **(many2one)** — Operation Type ⚠️ obrigatório → `stock.picking.type`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Reference 🔒 readonly
- `origin` **(char)** — Source Document
  > Reference of the document
- `note` **(html)** — Notes
- `state` **(selection)** — Status 🔒 readonly
  >  * Draft: The transfer is not confirmed yet. Reservation doesn't apply.  * Waiting another operation: This transfer is waiting for another operation before being ready.  * Waiting: The transfer is waiting for the availability of some products. (a) The shipping policy is "As soon as possible": no product could be reserved. (b) The shipping policy is "When all products are ready": not all the products could be reserved.  * Ready: The transfer is ready to be processed. (a) The shipping policy is "As soon as possible": at least one product has been reserved. (b) The shipping policy is "When all products are ready": all product have been reserved.  * Done: The transfer has been processed.  * Cancelled: The transfer has been cancelled.
  > Opções: `draft` (Draft), `waiting` (Waiting Another Operation), `confirmed` (Waiting), `assigned` (Ready), `done` (Done), `cancel` (Cancelled)
- `priority` **(selection)** — Priority
  > Products will be reserved first for the transfers with the highest priorities.
  > Opções: `0` (Normal), `1` (Urgent)
- `scheduled_date` **(datetime)** — Scheduled Date
  > Scheduled time for the first part of the shipment to be processed. Setting manually a value here would set it as expected date for all the stock moves.
- `date_deadline` **(datetime)** — Deadline 🔒 readonly
  > In case of outgoing flow, validate the transfer before this date to allow to deliver at promised date to the customer.         In case of incoming flow, validate the transfer before this date in order to have these products in stock at the date promised by the supplier
- `has_deadline_issue` **(boolean)** — Is late 🔒 readonly
  > Is late or will be late depending on the deadline and scheduled date
- `date_done` **(datetime)** — Date of Transfer
  > Date at which the transfer has been processed or cancelled.
- `printed` **(boolean)** — Printed
- `signature` **(binary)** — Signature
  > Signature
- `is_locked` **(boolean)** — Is Locked
  > When the picking is not done this allows changing the initial demand. When the picking is done this allows changing the done quantities.
- `shipping_weight` **(float)** — Weight for Shipping
  > Total weight of packages and products not in a package. Packages with no shipping weight specified will default to their products' total weight. This is the weight used to compute the cost of the shipping.
- `picking_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `carrier_price` **(float)** — Shipping Cost
- `weight` **(float)** — Weight 🔒 readonly
  > Total weight of the products in the picking.
- `carrier_tracking_ref` **(char)** — Tracking Reference

## Relacionamentos

- `backorder_id` **(many2one)** — Back Order of 🔒 readonly → `stock.picking`
  > If this shipment was split, then this field links to the shipment which contains the already processed part.
- `backorder_ids` **(one2many)** — Back Orders → `stock.picking`
- `return_id` **(many2one)** — Return of 🔒 readonly → `stock.picking`
  > If this picking was created as a return of another picking, this field links to the original picking.
- `return_ids` **(one2many)** — Returns → `stock.picking`
- `reference_ids` **(many2many)** — References 🔒 readonly → `stock.reference`
- `move_ids` **(one2many)** — Stock Moves → `stock.move`
- `warehouse_address_id` **(many2one)** — Address 🔒 readonly → `res.partner`
- `partner_id` **(many2one)** — Contact → `res.partner`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `user_id` **(many2one)** — Responsible → `res.users`
- `move_line_ids` **(one2many)** — Operations → `stock.move.line`
- `package_history_ids` **(many2many)** — Transfered Packages → `stock.package.history`
- `owner_id` **(many2one)** — Assign Owner → `res.partner`
  > When validating the transfer, the products will be assigned to this owner.
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `lot_id` **(many2one)** — Lot/Serial Number 🔒 readonly → `stock.lot`
- `partner_country_id` **(many2one)** — Country 🔒 readonly → `res.country`
- `production_ids` **(one2many)** — Manufacturing Orders 🔒 readonly → `mrp.production`
- `production_group_id` **(many2one)** — Production Group 🔒 readonly → `mrp.production.group`
- `project_id` **(many2one)** — Project → `project.project`
- `purchase_id` **(many2one)** — Purchase Orders 🔒 readonly → `purchase.order`
- `check_ids` **(one2many)** — Checks → `quality.check`
- `quality_alert_ids` **(one2many)** — Alerts → `quality.alert`
- `sale_id` **(many2one)** — Sales Order → `sale.order`
- `allowed_carrier_ids` **(many2many)** — Allowed Carrier 🔒 readonly → `delivery.carrier`
- `carrier_id` **(many2one)** — Carrier → `delivery.carrier`
- `return_label_ids` **(one2many)** — Return Label 🔒 readonly → `ir.attachment`
- `website_id` **(many2one)** — Website 🔒 readonly → `website`
  > Website where this order has been placed, for eCommerce orders.

## Campos Calculados (readonly)

- `return_count` **(integer)** — # Returns 🔒 readonly
- `delay_alert_date` **(datetime)** — Delay Alert Date 🔒 readonly
- `json_popover` **(char)** — JSON data for the popover widget 🔒 readonly
- `has_scrap_move` **(boolean)** — Has Scrap Moves 🔒 readonly
- `picking_type_code` **(selection)** — Type of Operation 🔒 readonly
  > Opções: `incoming` (Receipt), `outgoing` (Delivery), `internal` (Internal Transfer), `mrp_operation` (Manufacturing)
- `picking_type_entire_packs` **(boolean)** — Move Entire Packages 🔒 readonly
  > If ticked, packages to move will be directly displayed in Barcode instead of the products they contain
- `use_create_lots` **(boolean)** — Create New Lots/Serial Numbers 🔒 readonly
  > If this is checked only, it will suppose you want to create new Lots/Serial Numbers, so you can provide them in a text field. 
- `use_existing_lots` **(boolean)** — Use Existing Lots/Serial Numbers 🔒 readonly
  > If this is checked, you will be able to choose the Lots/Serial Numbers. You can also decide to not put lots in this operation type.  This means it will create stock with no lot or not put a restriction on the lot taken. 
- `packages_count` **(integer)** — Packages Count 🔒 readonly
- `show_check_availability` **(boolean)** — Show Check Availability 🔒 readonly
  > Technical field used to compute whether the button "Check Availability" should be displayed.
- `show_allocation` **(boolean)** — Show Allocation 🔒 readonly
  > Technical Field used to decide whether the button "Allocation" should be displayed.
- `is_signed` **(boolean)** — Is Signed 🔒 readonly
- `is_date_editable` **(boolean)** — Is Scheduled Date Editable 🔒 readonly
- `weight_bulk` **(float)** — Bulk Weight 🔒 readonly
  > Total weight of products which are not in a package.
- `shipping_volume` **(float)** — Volume for Shipping 🔒 readonly
- `show_operations` **(boolean)** — Show Detailed Operations 🔒 readonly
  > If this checkbox is ticked, the pickings lines will represent detailed stock operations. If not, the picking lines will represent an aggregate of detailed stock operations.
- `show_lots_text` **(boolean)** — Show Lots Text 🔒 readonly
- `has_tracking` **(boolean)** — Has Tracking 🔒 readonly
- `products_availability` **(char)** — Product Availability 🔒 readonly
  > Latest product availability status of the picking
- `products_availability_state` **(selection)** — Products Availability State 🔒 readonly
  > Opções: `available` (Available), `expected` (Expected), `late` (Late)
- `show_next_pickings` **(boolean)** — Show Next Pickings 🔒 readonly
- `search_date_category` **(selection)** — Date Category 🔒 readonly
  > Opções: `before` (Before), `yesterday` (Yesterday), `today` (Today), `day_1` (Tomorrow), `day_2` (The day after tomorrow), `after` (After)
- `picking_warning_text` **(text)** — Picking Instructions 🔒 readonly
  > Internal instructions for the partner or its parent company as set by the user.
- `has_kits` **(boolean)** — Has Kits 🔒 readonly
- `production_count` **(integer)** — Count of MO generated 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `show_subcontracting_details_visible` **(boolean)** — Show Subcontracting Details Visible 🔒 readonly
- `days_to_arrive` **(datetime)** — Days To Arrive 🔒 readonly
- `delay_pass` **(datetime)** — Delay Pass 🔒 readonly
- `quality_check_todo` **(boolean)** — Pending checks 🔒 readonly
- `quality_check_fail` **(boolean)** — Quality Check Fail 🔒 readonly
- `quality_alert_count` **(integer)** — Quality Alert Count 🔒 readonly
- `subcontracting_source_purchase_count` **(integer)** — Number of subcontracting PO Source 🔒 readonly
  > Number of subcontracting Purchase Order Source
- `delivery_type` **(selection)** — Provider 🔒 readonly
  > Opções: `base_on_rule` (Based on Rules), `fixed` (Fixed Price), `envia` (Envia), `in_store` (Pick up in store)
- `carrier_tracking_url` **(char)** — Tracking URL 🔒 readonly
- `weight_uom_name` **(char)** — Weight unit of measure label 🔒 readonly
- `is_return_picking` **(boolean)** — Is Return Picking 🔒 readonly
- `destination_country_code` **(char)** — Destination Country 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `integration_level` **(selection)** — Integration Level 🔒 readonly
  > Action while validating Delivery Orders
  > Opções: `rate` (Get Rate), `rate_and_ship` (Get Rate and Create Shipment)
