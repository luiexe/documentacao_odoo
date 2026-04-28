# Work Order — `mrp.workorder`

**Ordenação padrão:** `sequence, leave_id, date_start, id`

---

## Campos Obrigatórios

- `name` **(char)** — Work Order ⚠️ obrigatório
- `workcenter_id` **(many2one)** — Work Center ⚠️ obrigatório → `mrp.workcenter`
- `production_id` **(many2one)** — Manufacturing Order ⚠️ obrigatório 🔒 readonly → `mrp.production`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `_barcode_scanned` **(char)** — Barcode Scanned
  > Value of the last barcode scanned.
- `sequence` **(integer)** — Sequence
- `barcode` **(char)** — Barcode 🔒 readonly
- `production_availability` **(selection)** — Stock Availability 🔒 readonly
  > Manufacturing readiness for this MO, as per bill of material configuration:             * Ready: The material is available to start the production.             * Waiting: The material is not available to start the production. 
  > Opções: `confirmed` (Waiting), `assigned` (Ready), `waiting` (Waiting Another Operation)
- `qty_producing` **(float)** — Currently Produced Quantity
- `qty_produced` **(float)** — Quantity Done
  > The number of products already handled by this work order
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `blocked` (Blocked), `ready` (To Do), `progress` (In Progress), `done` (Finished), `cancel` (Cancelled)
- `date_start` **(datetime)** — Start
- `date_finished` **(datetime)** — End
- `duration_expected` **(float)** — Expected Duration
- `duration` **(float)** — Real Duration
- `duration_unit` **(float)** — Duration Per Unit 🔒 readonly
- `duration_percent` **(integer)** — Duration Deviation (%) 🔒 readonly
- `costs_hour` **(float)** — Cost per hour
- `cost_mode` **(selection)** — Cost Mode
  > Opções: `actual` (Actual), `estimated` (Estimated)
- `production_date` **(datetime)** — Production Date 🔒 readonly
- `qty_reported_from_previous_wo` **(float)** — Carried Quantity
  > The quantity already produced awaiting allocation in the backorders chain.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `allow_producing_quantity_change` **(boolean)** — Allow Changes to Producing Quantity
- `quality_state` **(selection)** — Quality State
  > Opções: `none` (To do), `pass` (Passed), `fail` (Failed)
- `worksheet_page` **(integer)** — Worksheet page
- `picture` **(binary)** — Picture
- `employee_costs_hour` **(float)** — Employee Cost per hour

## Relacionamentos

- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
- `product_variant_attributes` **(many2many)** — Attribute Values 🔒 readonly → `product.template.attribute.value`
- `production_bom_id` **(many2one)** — Bill of Material 🔒 readonly → `mrp.bom`
  > Bills of Materials, also called recipes, are used to autocomplete components and work order instructions.
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `leave_id` **(many2one)** — Leave → `resource.calendar.leaves`
  > Slot into workcenter calendar once planned
- `operation_id` **(many2one)** — Operation → `mrp.routing.workcenter`
- `move_raw_ids` **(one2many)** — Raw Moves → `stock.move`
- `move_finished_ids` **(one2many)** — Finished Moves → `stock.move`
- `move_line_ids` **(one2many)** — Moves to Track 🔒 readonly → `stock.move.line`
  > Inventory moves for which you must scan a lot number at this work order
- `finished_lot_ids` **(many2many)** — Lot/Serial Numbers → `stock.lot`
- `time_ids` **(one2many)** — Time → `mrp.workcenter.productivity`
- `working_user_ids` **(one2many)** — Working user on this work order. 🔒 readonly → `res.users`
- `last_working_user_id` **(many2one)** — Last user that worked on this work order. 🔒 readonly → `res.users`
- `scrap_ids` **(one2many)** — Scrap → `stock.scrap`
- `blocked_by_workorder_ids` **(many2many)** — Blocked By → `mrp.workorder`
- `needed_by_workorder_ids` **(many2many)** — Blocks → `mrp.workorder`
- `mo_analytic_account_line_ids` **(many2many)** — Mo Analytic Account Line → `account.analytic.line`
- `wc_analytic_account_line_ids` **(many2many)** — Wc Analytic Account Line → `account.analytic.line`
- `quality_point_ids` **(many2many)** — Quality Point 🔒 readonly → `quality.point`
- `check_ids` **(one2many)** — Check → `quality.check`
- `finished_product_check_ids` **(many2many)** — Finished Product Check 🔒 readonly → `quality.check`
- `done_check_ids` **(many2many)** — Done Check 🔒 readonly → `quality.check`
- `quality_alert_ids` **(one2many)** — Quality Alert → `quality.alert`
- `current_quality_check_id` **(many2one)** — Current Quality Check → `quality.check`
- `move_id` **(many2one)** — Stock Move → `stock.move`
- `test_type_id` **(many2one)** — Test Type 🔒 readonly → `quality.point.test_type`
- `user_id` **(many2one)** — Responsible → `res.users`
- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `employee_ids` **(many2many)** — Working employees → `hr.employee`
- `employee_assigned_ids` **(many2many)** — Assigned → `hr.employee`
- `connected_employee_ids` **(many2many)** — Connected Employee → `hr.employee`
- `allowed_employees` **(many2many)** — employees with access 🔒 readonly → `hr.employee`
  > if left empty, all employees can log in to the workcenter
- `employee_analytic_account_line_ids` **(many2many)** — Employee Analytic Account Line → `account.analytic.line`

## Campos Calculados (readonly)

- `working_state` **(selection)** — Workcenter Status 🔒 readonly
  > Opções: `normal` (Normal), `blocked` (Blocked), `done` (In Progress)
- `product_tracking` **(selection)** — Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `production_state` **(selection)** — Production State 🔒 readonly
  >  * Draft: The MO is not confirmed yet.  * Confirmed: The MO is confirmed, the stock rules and the reordering of the components are trigerred.  * In Progress: The production has started (on the MO or on the WO).  * To Close: The production is done, the MO has to be closed.  * Done: The MO is closed, the stock moves are posted.   * Cancelled: The MO has been cancelled, can't be confirmed anymore.
  > Opções: `draft` (Draft), `confirmed` (Confirmed), `progress` (In Progress), `to_close` (To Close), `done` (Done), `cancel` (Cancelled)
- `qty_production` **(float)** — Original Production Quantity 🔒 readonly
- `qty_remaining` **(float)** — Quantity To Be Produced 🔒 readonly
- `qty_ready` **(float)** — Quantity Ready 🔒 readonly
- `is_produced` **(boolean)** — Has Been Produced 🔒 readonly
- `progress` **(float)** — Progress Done (%) 🔒 readonly
- `is_user_working` **(boolean)** — Is the Current User Working 🔒 readonly
- `scrap_count` **(integer)** — Scrap Move 🔒 readonly
- `json_popover` **(char)** — Popover Data JSON 🔒 readonly
- `show_json_popover` **(boolean)** — Show Popover? 🔒 readonly
- `consumption` **(selection)** — Consumption 🔒 readonly
  > Opções: `flexible` (Allowed), `warning` (Allowed with warning), `strict` (Blocked)
- `is_planned` **(boolean)** — Its Operations are Planned 🔒 readonly
- `allow_workorder_dependencies` **(boolean)** — Allow Work Order Dependencies 🔒 readonly
- `quality_point_count` **(integer)** — Steps 🔒 readonly
- `quality_check_todo` **(boolean)** — Quality Check Todo 🔒 readonly
- `quality_check_fail` **(boolean)** — Quality Check Fail 🔒 readonly
- `quality_alert_count` **(integer)** — Quality Alert Count 🔒 readonly
- `is_last_lot` **(boolean)** — Is Last lot 🔒 readonly
- `is_first_started_wo` **(boolean)** — Is The first Work Order 🔒 readonly
- `is_last_unfinished_wo` **(boolean)** — Is Last Work Order To Process 🔒 readonly
- `test_type` **(char)** — Technical name 🔒 readonly
- `product_description_variants` **(char)** — Custom Description 🔒 readonly
- `employee_name` **(char)** — Employee Name 🔒 readonly
- `all_employees_allowed` **(boolean)** — All Employees Allowed 🔒 readonly
