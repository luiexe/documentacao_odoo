# Choose the sheet layout to print the labels — `product.label.layout`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `print_format` **(selection)** — Format ⚠️ obrigatório
  > Opções: `dymo` (Dymo), `2x7xprice` (2 x 7 with price), `4x7xprice` (4 x 7 with price), `4x12` (4 x 12), `4x12xprice` (4 x 12 with price), `zpl` (ZPL Labels), `zplxprice` (ZPL Labels with price)
- `custom_quantity` **(integer)** — Copies ⚠️ obrigatório
- `move_quantity` **(selection)** — Quantity to print ⚠️ obrigatório
  > Opções: `move` (Operation Quantities), `custom` (Custom)
- `zpl_template` **(selection)** — ZPL Template ⚠️ obrigatório
  > Opções: `normal` (Normal (2.25" x 1.25")), `small` (Small (1.25" x 1.00")), `alternative` (Alternative (2.00" x 1.00")), `jewelry` (Jewelry (2.20" x 0.50"))

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `extra_html` **(html)** — Extra Content
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `zpl_preview` **(binary)** — ZPL Preview 🔒 readonly

## Relacionamentos

- `product_ids` **(many2many)** — Product → `product.product`
- `product_tmpl_ids` **(many2many)** — Product Tmpl → `product.template`
- `pricelist_id` **(many2one)** — Pricelist → `product.pricelist`
- `move_ids` **(many2many)** — Move → `stock.move`

## Campos Calculados (readonly)

- `rows` **(integer)** — Rows 🔒 readonly
- `columns` **(integer)** — Columns 🔒 readonly
