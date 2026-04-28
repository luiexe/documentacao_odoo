# Product Attribute — `product.attribute`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Attribute ⚠️ obrigatório
- `create_variant` **(selection)** — Variant Creation ⚠️ obrigatório
  > - Instantly: All possible variants are created as soon as the attribute and its values are added to a product.         - Dynamically: Each variant is created only when its corresponding attributes and values are added to a sales order.         - Never: Variants are never created for the attribute.         Note: this cannot be changed once the attribute is used on a product.
  > Opções: `always` (Instantly), `dynamic` (Dynamically), `no_variant` (Never)
- `display_type` **(selection)** — Display Type ⚠️ obrigatório
  > The display type used in the Product Configurator.
  > Opções: `radio` (Radio), `pills` (Pills), `select` (Select), `color` (Color), `multi` (Multi-checkbox), `image` (Image)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If unchecked, it will allow you to hide the attribute without removing it.
- `sequence` **(integer)** — Sequence
  > Determine the display order
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `visibility` **(selection)** — Visibility
  > Opções: `visible` (Visible), `hidden` (Hidden)
- `preview_variants` **(selection)** — On Product Cards
  > Instantly created variants are available for selection from your /shop page.
  > Opções: `visible` (Visible), `hidden` (Hidden), `hover` (Hover)
- `is_thumbnail_visible` **(boolean)** — Show Thumbnails
  > Use product variant images instead of the attribute values displays.

## Relacionamentos

- `value_ids` **(one2many)** — Values → `product.attribute.value`
- `template_value_ids` **(one2many)** — Template Values → `product.template.attribute.value`
- `attribute_line_ids` **(one2many)** — Lines → `product.template.attribute.line`
- `product_tmpl_ids` **(many2many)** — Related Products 🔒 readonly → `product.template`
- `category_id` **(many2one)** — eCommerce Category → `product.attribute.category`
  > Set a category to regroup similar attributes under the same section in the Comparison page of eCommerce.

## Campos Calculados (readonly)

- `number_related_products` **(integer)** — Number Related Products 🔒 readonly
