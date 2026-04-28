# Bill of Material Line — `mrp.bom.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Component ⚠️ obrigatório → `product.product`
- `product_qty` **(float)** — Quantity ⚠️ obrigatório
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
- `bom_id` **(many2one)** — Parent BoM ⚠️ obrigatório → `mrp.bom`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > Gives the sequence order when displaying.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `cost_share` **(float)** — Cost Share (%)
  > The percentage of the component repartition cost when purchasing a kit.The total of all components' cost have to be equal to 100.

## Relacionamentos

- `product_tmpl_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `parent_product_tmpl_id` **(many2one)** — Parent Product Template 🔒 readonly → `product.template`
- `possible_bom_product_template_attribute_value_ids` **(many2many)** — Possible Product Template Attribute Value 🔒 readonly → `product.template.attribute.value`
- `bom_product_template_attribute_value_ids` **(many2many)** — Apply on Variants → `product.template.attribute.value`
  > BOM Product Variants needed to apply this line.
- `allowed_operation_ids` **(one2many)** — Operations 🔒 readonly → `mrp.routing.workcenter`
- `operation_id` **(many2one)** — Consumed in Operation → `mrp.routing.workcenter`
  > The operation where the components are consumed, or the finished products created.
- `child_bom_id` **(many2one)** — Sub BoM 🔒 readonly → `mrp.bom`
- `child_line_ids` **(one2many)** — BOM lines of the referred bom 🔒 readonly → `mrp.bom.line`

## Campos Calculados (readonly)

- `attachments_count` **(integer)** — Attachments Count 🔒 readonly
- `tracking` **(selection)** — Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
