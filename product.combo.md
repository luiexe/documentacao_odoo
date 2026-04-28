# Product Combo — `product.combo`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `combo_item_ids` **(one2many)** — Combo Item → `product.combo.item`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `combo_item_count` **(integer)** — Product Count 🔒 readonly
- `base_price` **(float)** — Combo Price 🔒 readonly
  > The minimum price among the products in this combo. This value will be used to prorate the price of this combo with respect to the other combos in a combo product. This heuristic ensures that whatever product the user chooses in a combo, it will always be the same price.
