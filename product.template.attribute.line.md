# Product Template Attribute Line — `product.template.attribute.line`

**Ordenação padrão:** `sequence, attribute_id, id`

---

## Campos Obrigatórios

- `product_tmpl_id` **(many2one)** — Product Template ⚠️ obrigatório → `product.template`
- `attribute_id` **(many2one)** — Attribute ⚠️ obrigatório → `product.attribute`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `value_count` **(integer)** — Value Count 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `value_ids` **(many2many)** — Values → `product.attribute.value`
- `product_template_value_ids` **(one2many)** — Product Attribute Values → `product.template.attribute.value`
