# Picking Type — `stock.picking.type`

**Ordenação padrão:** `is_favorite desc, sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Operation Type ⚠️ obrigatório
- `sequence_code` **(char)** — Sequence Prefix ⚠️ obrigatório
- `default_location_src_id` **(many2one)** — Source Location ⚠️ obrigatório → `stock.location`
  > This is the default source location when this operation is manually created. However, it is possible to change it afterwards or that the routes use another one by default.
- `default_location_dest_id` **(many2one)** — Destination Location ⚠️ obrigatório → `stock.location`
  > This is the default destination location when this operation is manually created. However, it is possible to change it afterwards or that the routes use another one by default.
- `code` **(selection)** — Type of Operation ⚠️ obrigatório
  > Opções: `incoming` (Receipt), `outgoing` (Delivery), `internal` (Internal Transfer), `mrp_operation` (Manufacturing)
- `reservation_method` **(selection)** — Reservation Method ⚠️ obrigatório
  > How products in transfers of this operation type should be reserved.
  > Opções: `at_confirm` (At Confirmation), `manual` (Manually), `by_date` (Before scheduled date)
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `create_backorder` **(selection)** — Create Backorder ⚠️ obrigatório
  > When validating a transfer:  * Ask: users are asked to choose if they want to make a backorder for remaining products  * Always: a backorder is automatically created for the remaining products  * Never: remaining products are cancelled
  > Opções: `ask` (Ask), `always` (Always), `never` (Never)
- `move_type` **(selection)** — Shipping Policy ⚠️ obrigatório
  > It specifies goods to be transferred partially or all at once
  > Opções: `direct` (As soon as possible), `one` (When all products are ready)
- `restrict_put_in_pack` **(selection)** — Force put in pack? ⚠️ obrigatório
  > Does the picker have to put the scanned products in a package? If yes, when?
  > Opções: `mandatory` (After each product), `optional` (After group of products), `no` (No)
- `restrict_scan_tracking_number` **(selection)** — Force Lot/Serial scan? ⚠️ obrigatório
  > Opções: `mandatory` (Mandatory Scan), `optional` (Optional Scan)
- `restrict_scan_source_location` **(selection)** — Force Source Location scan? ⚠️ obrigatório
  > Opções: `no` (No Scan), `mandatory` (Mandatory Scan)
- `restrict_scan_dest_location` **(selection)** — Force Destination Location scan? ⚠️ obrigatório
  > Does the picker have to scan the destination? If yes, when?
  > Opções: `mandatory` (After each product), `optional` (After group of products), `no` (No)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color
- `sequence` **(integer)** — Sequence
  > Used to order the 'All Operations' kanban view
- `show_entire_packs` **(boolean)** — Move Entire Packages
  > If ticked, packages to move will be directly displayed in Barcode instead of the products they contain
- `set_package_type` **(boolean)** — Set Package Type
  > If ticked, you will be able to select which package or package type to use in a put in pack
- `active` **(boolean)** — Active
- `use_create_lots` **(boolean)** — Create New Lots/Serial Numbers
  > If this is checked only, it will suppose you want to create new Lots/Serial Numbers, so you can provide them in a text field. 
- `use_existing_lots` **(boolean)** — Use Existing Lots/Serial Numbers
  > If this is checked, you will be able to choose the Lots/Serial Numbers. You can also decide to not put lots in this operation type.  This means it will create stock with no lot or not put a restriction on the lot taken. 
- `print_label` **(boolean)** — Generate Shipping Labels
  > Check this box if you want to generate shipping label in this operation.
- `show_operations` **(boolean)** — Show Detailed Operations
  > If this checkbox is ticked, the pickings lines will represent detailed stock operations. If not, the picking lines will represent an aggregate of detailed stock operations.
- `reservation_days_before` **(integer)** — Days
  > Maximum number of days before scheduled date that products should be reserved.
- `reservation_days_before_priority` **(integer)** — Days when starred
  > Maximum number of days before scheduled date that priority picking products should be reserved.
- `auto_show_reception_report` **(boolean)** — Show Reception Report at Validation
  > If this checkbox is ticked, Odoo will automatically show the reception report (if there are moves to allocate to) when validating.
- `auto_print_delivery_slip` **(boolean)** — Auto Print Delivery Slip
  > If this checkbox is ticked, Odoo will automatically print the delivery slip of a picking when it is validated.
- `auto_print_return_slip` **(boolean)** — Auto Print Return Slip
  > If this checkbox is ticked, Odoo will automatically print the return slip of a picking when it is validated.
- `auto_print_product_labels` **(boolean)** — Auto Print Product Labels
  > If this checkbox is ticked, Odoo will automatically print the product labels of a picking when it is validated.
- `product_label_format` **(selection)** — Product Label Format to auto-print
  > Opções: `dymo` (Dymo), `2x7xprice` (2 x 7 with price), `4x7xprice` (4 x 7 with price), `4x12` (4 x 12), `4x12xprice` (4 x 12 with price), `zpl` (ZPL Labels), `zplxprice` (ZPL Labels with price)
- `auto_print_lot_labels` **(boolean)** — Auto Print Lot/SN Labels
  > If this checkbox is ticked, Odoo will automatically print the lot/SN labels of a picking when it is validated.
- `lot_label_format` **(selection)** — Lot Label Format to auto-print
  > Opções: `4x12_lots` (4 x 12 - One per lot/SN), `4x12_units` (4 x 12 - One per unit), `zpl_lots` (ZPL Labels - One per lot/SN), `zpl_units` (ZPL Labels - One per unit)
- `auto_print_reception_report` **(boolean)** — Auto Print Reception Report
  > If this checkbox is ticked, Odoo will automatically print the reception report of a picking when it is validated and has assigned moves.
- `auto_print_reception_report_labels` **(boolean)** — Auto Print Reception Report Labels
  > If this checkbox is ticked, Odoo will automatically print the reception report labels of a picking when it is validated.
- `auto_print_packages` **(boolean)** — Auto Print Packages
  > If this checkbox is ticked, Odoo will automatically print the packages and their contents of a picking when it is validated.
- `auto_print_package_label` **(boolean)** — Auto Print Package Label
  > If this checkbox is ticked, Odoo will automatically print the package label when "Put in Pack" button is used.
- `package_label_to_print` **(selection)** — Package Label to Print
  > Opções: `pdf` (PDF), `zpl` (ZPL)
- `barcode` **(char)** — Barcode
- `picking_properties_definition` **(properties_definition)** — Picking Properties
- `is_favorite` **(boolean)** — Show Operation in Overview
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `use_create_components_lots` **(boolean)** — Create New Lots/Serial Numbers for Components
  > Allow to create new lot/serial numbers for the components
- `auto_print_done_production_order` **(boolean)** — Auto Print Done Production Order
  > If this checkbox is ticked, Odoo will automatically print the production order of a MO when it is done.
- `auto_print_done_mrp_product_labels` **(boolean)** — Auto Print Produced Product Labels
  > If this checkbox is ticked, Odoo will automatically print the product labels of a MO when it is done.
- `mrp_product_label_to_print` **(selection)** — Product Label to Print
  > Opções: `pdf` (PDF), `zpl` (ZPL)
- `auto_print_done_mrp_lot` **(boolean)** — Auto Print Produced Lot Label
  > If this checkbox is ticked, Odoo will automatically print the lot/SN label of a MO when it is done.
- `done_mrp_lot_label_to_print` **(selection)** — Lot/SN Label to Print
  > Opções: `pdf` (PDF), `zpl` (ZPL)
- `auto_print_mrp_reception_report` **(boolean)** — Auto Print Allocation Report
  > If this checkbox is ticked, Odoo will automatically print the allocation report of a MO when it is done and has assigned moves.
- `auto_print_mrp_reception_report_labels` **(boolean)** — Auto Print Allocation Report Labels
  > If this checkbox is ticked, Odoo will automatically print the allocation report labels of a MO when it is done.
- `auto_print_generated_mrp_lot` **(boolean)** — Auto Print Generated Lot/SN Label
  > Automatically print the lot/SN label when the "Create a new serial/lot number" button is used.
- `generated_mrp_lot_label_to_print` **(selection)** — Generated Lot/SN Label to Print
  > Opções: `pdf` (PDF), `zpl` (ZPL)
- `barcode_allow_extra_product` **(boolean)** — Allow extra products
  > For planned transfers, allow adding non-reserved products
- `barcode_validation_after_dest_location` **(boolean)** — Force a destination for all products
- `barcode_validation_all_product_packed` **(boolean)** — Force all products to be packed
- `barcode_validation_full` **(boolean)** — Allow full picking validation
  > Allow validating a picking even if nothing has been scanned yet, i.e. do an immediate transfer
- `restrict_scan_product` **(boolean)** — Force Product scan?
  > A line's product must be scanned before the line can be edited
- `show_reserved_sns` **(boolean)** — Show reserved lots/SN
  > Display reserved lots/serial numbers. When not active, the picker can pick lots/serials as they want.
- `prefill_shop_floor_lots` **(boolean)** — Pre fill lot/serial numbers in shop floor moves 
  > When enabled, reserved lots for component moves will be displayed in the shop floor. When disabled, lots will always need to be selected manually when processing components in the shop floor.
- `auto_close_production` **(boolean)** — Close Manufacturing Orders
  > Allow users to close MO in last work order operation or from the overview tab.
- `analytic_costs` **(boolean)** — Analytic Costs
  > Validating stock pickings will generate analytic entries for the selected project. Products set for re-invoicing will also be billed to the customer.

## Relacionamentos

- `sequence_id` **(many2one)** — Reference Sequence → `ir.sequence`
- `return_picking_type_id` **(many2one)** — Operation Type for Returns → `stock.picking.type`
- `warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`
- `favorite_user_ids` **(many2many)** — Favorite User → `res.users`

## Campos Calculados (readonly)

- `count_picking_draft` **(integer)** — Count Picking Draft 🔒 readonly
- `count_picking_ready` **(integer)** — Count Picking Ready 🔒 readonly
- `count_picking` **(integer)** — Count Picking 🔒 readonly
- `count_picking_waiting` **(integer)** — Count Picking Waiting 🔒 readonly
- `count_picking_late` **(integer)** — Count Picking Late 🔒 readonly
- `count_picking_backorders` **(integer)** — Count Picking Backorders 🔒 readonly
- `count_move_ready` **(integer)** — Count Move Ready 🔒 readonly
- `hide_reservation_method` **(boolean)** — Hide Reservation Method 🔒 readonly
- `show_picking_type` **(boolean)** — Show Picking Type 🔒 readonly
- `kanban_dashboard_graph` **(text)** — Kanban Dashboard Graph 🔒 readonly
- `count_mo_todo` **(integer)** — Number of Manufacturing Orders to Process 🔒 readonly
- `count_mo_waiting` **(integer)** — Number of Manufacturing Orders Waiting 🔒 readonly
- `count_mo_late` **(integer)** — Number of Manufacturing Orders Late 🔒 readonly
- `count_mo_in_progress` **(integer)** — Number of Manufacturing Orders In Progress 🔒 readonly
- `count_mo_to_close` **(integer)** — Number of Manufacturing Orders To Close 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `show_barcode_validation` **(boolean)** — Show Barcode Validation 🔒 readonly
  > Technical field used to compute whether the "Final Validation" group should be displayed, to support combined groups/invisible complexity.
- `is_barcode_picking_type` **(boolean)** — Is Barcode Picking Type 🔒 readonly
  > Technical field indicating if type should be used in barcode app and used to control visibility in the related UI.
- `count_mo_confirmed` **(integer)** — Count Mo Confirmed 🔒 readonly
