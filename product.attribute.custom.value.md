# Product Attribute Custom Value — `product.attribute.custom.value`

**Ordenação padrão:** `custom_product_template_attribute_value_id, id`

---

## Campos Obrigatórios

- `custom_product_template_attribute_value_id` **(many2one)** — Attribute Value ⚠️ obrigatório → `product.template.attribute.value`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `custom_value` **(char)** — Custom Value
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `sale_order_line_id` **(many2one)** — Sales Order Line → `sale.order.line`

## Campos Calculados (readonly)

- `name` **(char)** — Name 🔒 readonly
