# Bill of Material — `mrp.bom`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `type` **(selection)** — BoM Type ⚠️ obrigatório
  > Opções: `normal` (Manufacture this product), `phantom` (Kit), `subcontract` (Subcontracting)
- `product_tmpl_id` **(many2one)** — Product ⚠️ obrigatório → `product.template`
- `product_qty` **(float)** — Quantity ⚠️ obrigatório
  > This should be the smallest quantity that this product can be produced in. If the BOM contains operations, make sure the work center capacity is accurate.
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
  > Unit of Measure (Unit of Measure) is the unit of measurement for the inventory control
- `ready_to_produce` **(selection)** — Manufacturing Readiness ⚠️ obrigatório
  > Opções: `all_available` ( When all components are available), `asap` (When components for 1st operation are available)
- `consumption` **(selection)** — Flexible Consumption ⚠️ obrigatório
  > Defines if you can consume more or less components than the quantity defined on the BoM:   * Allowed: allowed for all manufacturing users.   * Allowed with warning: allowed for all manufacturing users with summary of consumption differences when closing the manufacturing order.   Note that in the case of component Highlight Consumption, where consumption is registered manually exclusively, consumption warnings will still be issued when appropriate also.   * Blocked: only a manager can close a manufacturing order when the BoM consumption is not respected.
  > Opções: `flexible` (Allowed), `warning` (Allowed with warning), `strict` (Blocked)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code` **(char)** — Reference
- `active` **(boolean)** — Production Ready
- `sequence` **(integer)** — Sequence
- `allow_operation_dependencies` **(boolean)** — Operation Dependencies
  > Create operation level dependencies that will influence both planning and the status of work orders upon MO confirmation. If this feature is ticked, and nothing is specified, Odoo will assume that all operations can be started simultaneously.
- `produce_delay` **(integer)** — Manufacturing Lead Time
  > Average lead time in days to manufacture this product. In the case of multi-level BOM, the manufacturing lead times of the components will be added. In case the product is subcontracted, this can be used to determine the date at which components should be sent to the subcontractor.
- `days_to_prepare_mo` **(integer)** — Days to prepare Manufacturing Order
  > Create and confirm Manufacturing Orders this many days in advance, to have enough time to replenish components or manufacture semi-finished products.
- `batch_size` **(float)** — Batch Size
  > All automatically generated manufacturing orders for this product will be of this size.
- `enable_batch_size` **(boolean)** — Enable Batch Size
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `version` **(integer)** — Version
- `image_128` **(binary)** — Image 128

## Relacionamentos

- `product_id` **(many2one)** — Product Variant → `product.product`
  > If a product variant is defined the BOM is available only for this product.
- `bom_line_ids` **(one2many)** — BoM Lines → `mrp.bom.line`
- `byproduct_ids` **(one2many)** — By-products → `mrp.bom.byproduct`
- `operation_ids` **(one2many)** — Operations → `mrp.routing.workcenter`
- `picking_type_id` **(many2one)** — Operation Type → `stock.picking.type`
  > When a procurement has a ‘produce’ route with a operation type set, it will try to create a Manufacturing Order for that product using a BoM of the same operation type.If not,the operation type is not taken into account in the BoM search. That allows to define stock rules which trigger different manufacturing orders with different BoMs.
- `company_id` **(many2one)** — Company → `res.company`
- `possible_product_template_attribute_value_ids` **(many2many)** — Possible Product Template Attribute Value 🔒 readonly → `product.template.attribute.value`
- `previous_bom_id` **(many2one)** — Previous BoM → `mrp.bom`
- `eco_ids` **(one2many)** — ECO to be applied → `mrp.eco`
- `subcontractor_ids` **(many2many)** — Subcontractors → `res.partner`
- `project_id` **(many2one)** — Project → `project.project`

## Campos Calculados (readonly)

- `operation_count` **(integer)** — Operations Count 🔒 readonly
- `show_copy_operations_button` **(boolean)** — Show Copy Operations Button 🔒 readonly
  > Technical field used to control the visibility of the 'Copy Existing Operations' button.
- `show_set_bom_button` **(boolean)** — Show Set Bom Button 🔒 readonly
- `eco_count` **(integer)** — # ECOs 🔒 readonly
- `quality_point_count` **(integer)** — Instructions Count 🔒 readonly
