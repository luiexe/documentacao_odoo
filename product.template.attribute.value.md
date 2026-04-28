# Product Template Attribute Value — `product.template.attribute.value`

**Ordenação padrão:** `attribute_line_id, product_attribute_value_id, id`

---

## Campos Obrigatórios

- `product_attribute_value_id` **(many2one)** — Attribute Value ⚠️ obrigatório → `product.attribute.value`
- `attribute_line_id` **(many2one)** — Attribute Line ⚠️ obrigatório → `product.template.attribute.line`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `ptav_active` **(boolean)** — Active
- `price_extra` **(float)** — Extra Price
  > Extra price for the variant with this attribute value on sale price. eg. 200 price extra, 1000 + 200 = 1200.
- `color` **(integer)** — Color
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `exclude_for` **(one2many)** — Exclude for → `product.template.attribute.exclusion`
  > Make this attribute value not compatible with other values of the product or some attribute values of optional and accessory products.
- `product_tmpl_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `attribute_id` **(many2one)** — Attribute 🔒 readonly → `product.attribute`
- `ptav_product_variant_ids` **(many2many)** — Related Variants 🔒 readonly → `product.product`

## Campos Calculados (readonly)

- `name` **(char)** — Value 🔒 readonly
- `html_color` **(char)** — HTML Color Index 🔒 readonly
  > Here you can set a specific HTML color index (e.g. #ff0000) to display the color if the attribute type is 'Color'.
- `is_custom` **(boolean)** — Free text 🔒 readonly
  > Allow customers to set their own value
- `display_type` **(selection)** — Display Type 🔒 readonly
  > The display type used in the Product Configurator.
  > Opções: `radio` (Radio), `pills` (Pills), `select` (Select), `color` (Color), `multi` (Multi-checkbox), `image` (Image)
- `image` **(binary)** — Image 🔒 readonly
  > You can upload an image that will be used as the color of the attribute value.
