# Quality Check — `quality.check`

**Ordenação padrão:** `point_id, id`

---

## Campos Obrigatórios

- `team_id` **(many2one)** — Team ⚠️ obrigatório → `quality.alert.team`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `test_type_id` **(many2one)** — Test Type ⚠️ obrigatório → `quality.point.test_type`
- `measure_on` **(selection)** — Control per ⚠️ obrigatório 🔒 readonly
  > Operation = One quality check is requested at the operation level.                   Product = A quality check is requested per product.                  Quantity = A quality check is requested for each new product quantity registered, with partial quantity checks also possible.
  > Opções: `operation` (Operation), `product` (Product), `move_line` (Quantity)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Reference
- `title` **(char)** — Title
- `quality_state` **(selection)** — Status
  > Opções: `none` (To do), `pass` (Passed), `fail` (Failed)
- `control_date` **(datetime)** — Control Date
- `note` **(html)** — Note
- `picture` **(binary)** — Picture
- `additional_note` **(text)** — Additional Note
  > Additional remarks concerning this check.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `is_deleted` **(boolean)** — Deleted in production
- `finished_product_sequence` **(float)** — Finished Product Sequence Number
- `worksheet_document` **(binary)** — Image/PDF
- `measure` **(float)** — Measure
- `measure_success` **(selection)** — Measure Success 🔒 readonly
  > Opções: `none` (No measure), `pass` (Pass), `fail` (Fail)
- `qty_tested` **(float)** — Quantity Tested
  > Quantity of product tested within the lot
- `qty_passed` **(float)** — Quantity Passed 🔒 readonly
  > Quantity of product that passed the quality check
- `qty_failed` **(float)** — Quantity Failed 🔒 readonly
  > Quantity of product that failed the quality check

## Relacionamentos

- `point_id` **(many2one)** — Control Point → `quality.point`
- `product_id` **(many2one)** — Product → `product.product`
- `picking_id` **(many2one)** — Picking → `stock.picking`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
- `lot_ids` **(many2many)** — Lot/Serial → `stock.lot`
- `user_id` **(many2one)** — Responsible → `res.users`
- `alert_ids` **(one2many)** — Alerts → `quality.alert`
- `failure_location_id` **(many2one)** — Failure Location → `stock.location`
- `workorder_id` **(many2one)** — Operation → `mrp.workorder`
- `workcenter_id` **(many2one)** — Work Center 🔒 readonly → `mrp.workcenter`
- `production_id` **(many2one)** — Production Order → `mrp.production`
- `next_check_id` **(many2one)** — Next Check → `quality.check`
- `previous_check_id` **(many2one)** — Previous Check → `quality.check`
- `move_id` **(many2one)** — Stock Move → `stock.move`
- `component_id` **(many2one)** — Component → `product.product`
- `component_uom_id` **(many2one)** — Component Unit 🔒 readonly → `uom.uom`
- `finished_lot_ids` **(many2many)** — Lot/Serial Number 🔒 readonly → `stock.lot`
- `employee_id` **(many2one)** — Employee → `hr.employee`
- `move_line_id` **(many2one)** — Stock Move Line → `stock.move.line`
  > In case of Quality Check by Quantity, Move Line on which the Quality Check applies
- `lot_line_id` **(many2one)** — Lot Line 🔒 readonly → `stock.lot`
- `uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.
- `spreadsheet_id` **(many2one)** — Spreadsheet → `quality.check.spreadsheet`
- `allowed_product_ids` **(many2many)** — Allowed Product 🔒 readonly → `product.product`
- `spreadsheet_template_id` **(many2one)** — Spreadsheet Template 🔒 readonly → `quality.spreadsheet.template`
- `operation_id` **(many2one)** — Step 🔒 readonly → `mrp.routing.workcenter`

## Campos Calculados (readonly)

- `alert_count` **(integer)** — # Quality Alerts 🔒 readonly
- `test_type` **(char)** — Technical name 🔒 readonly
- `product_tracking` **(selection)** — Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `component_barcode` **(char)** — Barcode 🔒 readonly
  > International Article Number used for product identification.
- `component_tracking` **(selection)** — Is Component Tracked 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `is_user_working` **(boolean)** — Is the Current User Working 🔒 readonly
- `consumption` **(selection)** — Consumption 🔒 readonly
  > Opções: `flexible` (Allowed), `warning` (Allowed with warning), `strict` (Blocked)
- `working_state` **(selection)** — Workcenter Status 🔒 readonly
  > Opções: `normal` (Normal), `blocked` (Blocked), `done` (In Progress)
- `result` **(char)** — Result 🔒 readonly
- `failure_message` **(html)** — Failure Message 🔒 readonly
- `tolerance_min` **(float)** — Min Tolerance 🔒 readonly
- `tolerance_max` **(float)** — Max Tolerance 🔒 readonly
- `warning_message` **(text)** — Warning Message 🔒 readonly
- `norm_unit` **(char)** — Norm Unit 🔒 readonly
- `qty_to_test` **(float)** — Quantity to Test 🔒 readonly
  > Quantity of product to test within the lot
- `lot_name` **(char)** — Lot/Serial Number Name 🔒 readonly
- `qty_line` **(float)** — Quantity 🔒 readonly
- `show_lot_text` **(boolean)** — Show Lot Text 🔒 readonly
- `is_lot_tested_fractionally` **(boolean)** — Lot Tested Fractionally 🔒 readonly
  > Determines if only a fraction of the lot should be tested
- `testing_percentage_within_lot` **(float)** — Testing Percentage Within Lot 🔒 readonly
  > Defines the percentage within a lot that should be tested
- `hide_picking_id` **(integer)** — Hide Picking 🔒 readonly
- `hide_production_id` **(integer)** — Hide Production 🔒 readonly
- `hide_repair_id` **(integer)** — Hide Repair 🔒 readonly
