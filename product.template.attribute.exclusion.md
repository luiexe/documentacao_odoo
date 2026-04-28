# Product Template Attribute Exclusion — `product.template.attribute.exclusion`

**Ordenação padrão:** `product_tmpl_id, id`

---

## Campos Obrigatórios

- `product_tmpl_id` **(many2one)** — Product Template ⚠️ obrigatório → `product.template`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_template_attribute_value_id` **(many2one)** — Attribute Value → `product.template.attribute.value`
- `value_ids` **(many2many)** — Attribute Values → `product.template.attribute.value`
