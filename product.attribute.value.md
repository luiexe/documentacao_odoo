# Attribute Value — `product.attribute.value`

**Ordenação padrão:** `attribute_id, sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Value ⚠️ obrigatório
- `attribute_id` **(many2one)** — Attribute ⚠️ obrigatório → `product.attribute`
  > The attribute cannot be changed once the value is used on at least one product.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > Determine the display order
- `default_extra_price` **(float)** — Default Extra Price
- `is_custom` **(boolean)** — Free text
  > Allow customers to set their own value
- `html_color` **(char)** — Color
  > Here you can set a specific HTML color index (e.g. #ff0000) to display the color if the attribute type is 'Color'.
- `color` **(integer)** — Color Index
- `image` **(binary)** — Image
  > You can upload an image that will be used as the color of the attribute value.
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `pav_attribute_line_ids` **(many2many)** — Lines → `product.template.attribute.line`

## Campos Calculados (readonly)

- `display_type` **(selection)** — Display Type 🔒 readonly
  > The display type used in the Product Configurator.
  > Opções: `radio` (Radio), `pills` (Pills), `select` (Select), `color` (Color), `multi` (Multi-checkbox), `image` (Image)
- `is_used_on_products` **(boolean)** — Used on Products 🔒 readonly
- `default_extra_price_changed` **(boolean)** — Default Extra Price Changed 🔒 readonly
