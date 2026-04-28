# Product Tag — `product.tag`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `color` **(char)** — Color
- `visible_to_customers` **(boolean)** — Visible to customers
  > Whether the tag is displayed to customers.
- `image` **(binary)** — Image
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_template_ids` **(many2many)** — Product Templates → `product.template`
- `product_product_ids` **(many2many)** — Product Variants → `product.product`
- `product_ids` **(many2many)** — All Product Variants using this Tag 🔒 readonly → `product.product`
- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
