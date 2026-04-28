# Quality Control Point — `quality.point`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Reference ⚠️ obrigatório
- `team_id` **(many2one)** — Team ⚠️ obrigatório → `quality.alert.team`
- `picking_type_ids` **(many2many)** — Operation Types ⚠️ obrigatório → `stock.picking.type`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `test_type_id` **(many2one)** — Test Type ⚠️ obrigatório → `quality.point.test_type`
  > Defines the type of the quality control point.
- `test_report_type` **(selection)** — Report Type ⚠️ obrigatório
  > Opções: `pdf` (PDF), `zpl` (ZPL)
- `measure_on` **(selection)** — Control per ⚠️ obrigatório
  > Operation = One quality check is requested at the operation level.                   Product = A quality check is requested per product.                  Quantity = A quality check is requested for each new product quantity registered, with partial quantity checks also possible.
  > Opções: `operation` (Operation), `product` (Product), `move_line` (Quantity)
- `measure_frequency_type` **(selection)** — Control Frequency ⚠️ obrigatório
  > Opções: `all` (All), `random` (Randomly), `periodical` (Periodically), `on_demand` (On-demand)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `title` **(char)** — Title
- `active` **(boolean)** — Active
- `note` **(html)** — Note
- `reason` **(html)** — Cause
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `worksheet_document` **(binary)** — Image/PDF
- `failure_message` **(html)** — Failure Message
- `measure_frequency_value` **(float)** — Percentage
  > The probability of each quality check being generated
- `measure_frequency_unit_value` **(integer)** — Frequency Unit Value
- `measure_frequency_unit` **(selection)** — Measure Frequency Unit
  > Opções: `day` (Days), `week` (Weeks), `month` (Months)
- `testing_percentage_within_lot` **(float)** — Testing Percentage Within Lot
  > Defines the percentage within a lot that should be tested
- `norm` **(float)** — Norm
- `tolerance_min` **(float)** — Min Tolerance
- `tolerance_max` **(float)** — Max Tolerance
- `norm_unit` **(char)** — Norm Unit
- `spreadsheet_check_cell` **(char)** — Success cell
  > The check is successful if the success cell value is TRUE. If there are several sheets, specify which one you want to use (e.g. Sheet2!C4). If not specified, the first sheet is selected by default.

## Relacionamentos

- `product_ids` **(many2many)** — Products → `product.product`
  > Quality Point will apply to every selected Products.
- `product_category_ids` **(many2many)** — Product Categories → `product.category`
  > Quality Point will apply to every Products in the selected Product Categories.
- `user_id` **(many2one)** — Responsible → `res.users`
- `check_ids` **(one2many)** — Check → `quality.check`
- `failure_location_ids` **(many2many)** — Failure Locations → `stock.location`
  > If quality check fails, a destination location is chosen from this list for - each failed specific product quantity if control is per quantity  /- all quantities of a product if control is per product  /- all quantities of products in the operation if control is per operation
- `operation_id` **(many2one)** — Step → `mrp.routing.workcenter`
- `bom_id` **(many2one)** — Bill of Material 🔒 readonly → `mrp.bom`
- `component_ids` **(one2many)** — Component 🔒 readonly → `product.product`
- `bom_product_ids` **(one2many)** — Bom Product 🔒 readonly → `product.product`
- `component_id` **(many2one)** — Product To Register → `product.product`
- `spreadsheet_template_id` **(many2one)** — Spreadsheet Template → `quality.spreadsheet.template`

## Campos Calculados (readonly)

- `check_count` **(integer)** — Check Count 🔒 readonly
- `test_type` **(char)** — Technical name 🔒 readonly
- `show_failure_location` **(boolean)** — Show Failure Location 🔒 readonly
- `is_workorder_step` **(boolean)** — Is Workorder Step 🔒 readonly
- `bom_active` **(boolean)** — Related Bill of Material Active 🔒 readonly
- `is_lot_tested_fractionally` **(boolean)** — Lot Tested Fractionally 🔒 readonly
  > Determines if only a fraction of the lot should be tested
- `average` **(float)** — Average 🔒 readonly
- `standard_deviation` **(float)** — Standard Deviation 🔒 readonly
