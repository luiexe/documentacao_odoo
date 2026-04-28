# Work Center Usage — `mrp.routing.workcenter`

**Ordenação padrão:** `bom_id, sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Operation ⚠️ obrigatório
- `workcenter_id` **(many2one)** — Work Center ⚠️ obrigatório → `mrp.workcenter`
- `bom_id` **(many2one)** — Bill of Material ⚠️ obrigatório → `mrp.bom`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
  > Gives the sequence order when displaying a list of routing Work Centers.
- `time_mode` **(selection)** — Duration Computation
  > Opções: `manual` (Fixed), `auto` (Computed)
- `time_mode_batch` **(integer)** — Based on
- `time_cycle_manual` **(float)** — Manual Duration
  > Time in minutes:- In fixed mode, time used- In computed mode, supposed first time when there aren't any work orders yet
- `cost_mode` **(selection)** — Cost based on
  > Determines the way Odoo calculates the cost of the operation: - Based on Actual time: the cost will be calculated based on tracked time and real employee costs. - Based on Estimated time: the cost will be calculated based on estimated time and costs.
  > Opções: `actual` (Actual time), `estimated` (Theorical time)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `employee_ratio` **(float)** — Employee Capacity
  > Number of employees needed to complete operation.

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `workorder_ids` **(one2many)** — Work Orders → `mrp.workorder`
- `possible_bom_product_template_attribute_value_ids` **(many2many)** — Possible Product Template Attribute Value 🔒 readonly → `product.template.attribute.value`
- `bom_product_template_attribute_value_ids` **(many2many)** — Apply on Variants → `product.template.attribute.value`
  > BOM Product Variants needed to apply this line.
- `blocked_by_operation_ids` **(many2many)** — Blocked By → `mrp.routing.workcenter`
  > Operations that need to be completed before this operation can start.
- `needed_by_operation_ids` **(many2many)** — Blocks → `mrp.routing.workcenter`
  > Operations that cannot start before this operation is completed.
- `quality_point_ids` **(one2many)** — Quality Point → `quality.point`
- `default_picking_type_ids` **(one2many)** — Default Picking Type 🔒 readonly → `stock.picking.type`

## Campos Calculados (readonly)

- `time_computed_on` **(char)** — Computed on last 🔒 readonly
- `time_cycle` **(float)** — Cycles 🔒 readonly
- `workorder_count` **(integer)** — # Work Orders 🔒 readonly
- `allow_operation_dependencies` **(boolean)** — Operation Dependencies 🔒 readonly
  > Create operation level dependencies that will influence both planning and the status of work orders upon MO confirmation. If this feature is ticked, and nothing is specified, Odoo will assume that all operations can be started simultaneously.
- `cycle_number` **(integer)** — Repetitions 🔒 readonly
- `time_total` **(float)** — Total Duration 🔒 readonly
- `show_time_total` **(boolean)** — Show Total Duration? 🔒 readonly
- `cost` **(float)** — Cost 🔒 readonly
- `quality_point_count` **(integer)** — Instructions 🔒 readonly
