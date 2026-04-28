# Byproduct — `mrp.bom.byproduct`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — By-product ⚠️ obrigatório → `product.product`
- `product_qty` **(float)** — Quantity ⚠️ obrigatório
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `cost_share` **(float)** — Cost Share (%)
  > The percentage of the final production cost for this by-product line (divided between the quantity produced).The total of all by-products' cost share must be less than or equal to 100.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `bom_id` **(many2one)** — BoM → `mrp.bom`
- `allowed_operation_ids` **(one2many)** — Operations 🔒 readonly → `mrp.routing.workcenter`
- `operation_id` **(many2one)** — Produced in Operation → `mrp.routing.workcenter`
- `possible_bom_product_template_attribute_value_ids` **(many2many)** — Possible Product Template Attribute Value 🔒 readonly → `product.template.attribute.value`
- `bom_product_template_attribute_value_ids` **(many2many)** — Apply on Variants → `product.template.attribute.value`
  > BOM Product Variants needed to apply this line.
