# Quotation Template Line — `sale.order.template.line`

**Ordenação padrão:** `sale_order_template_id, sequence, id`

---

## Campos Obrigatórios

- `sale_order_template_id` **(many2one)** — Quotation Template Reference ⚠️ obrigatório → `sale.order.template`
- `product_uom_qty` **(float)** — Quantity ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > Gives the sequence order when displaying a list of sale quote lines.
- `name` **(text)** — Description
- `display_type` **(selection)** — Display Type
  > Opções: `line_section` (Section), `line_subsection` (Subsection), `line_note` (Note)
- `is_optional` **(boolean)** — Optional Line
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `product_id` **(many2one)** — Product → `product.product`
- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `product_uom_id` **(many2one)** — Unit → `uom.uom`
- `parent_id` **(many2one)** — Parent Section Line 🔒 readonly → `sale.order.template.line`
