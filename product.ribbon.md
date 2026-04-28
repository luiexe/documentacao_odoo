# Product ribbon — `product.ribbon`

**Ordenação padrão:** `sequence ASC, id`

---

## Campos Obrigatórios

- `name` **(char)** — Ribbon Name ⚠️ obrigatório
- `bg_color` **(char)** — Background Color ⚠️ obrigatório
- `text_color` **(char)** — Text Color ⚠️ obrigatório
- `position` **(selection)** — Position ⚠️ obrigatório
  > Opções: `left` (Left), `right` (Right)
- `style` **(selection)** — Style ⚠️ obrigatório
  > Defines the display style: - Ribbon: Shows a ribbon banner on the product image. - Badge: Shows a small badge label on the product image.
  > Opções: `ribbon` (Ribbon), `tag` (Badge)
- `assign` **(selection)** — Assign ⚠️ obrigatório
  > Defines how this ribbon is assigned to products: - Manually: You assign the ribbon manually to products. - Sale: Applied when the product is visibly on sale. - New: Applied based on the New period you will define. - Out Of Stock: Applied when the product is out of stock.
  > Opções: `manual` (Manually), `sale` (On Sale), `new` (When New), `out_of_stock` (when out of stock)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `new_period` **(integer)** — New Period
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
