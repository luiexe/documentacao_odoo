# Product Combo Item — `product.combo.item`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `combo_id` **(many2one)** — Combo ⚠️ obrigatório → `product.combo`
- `product_id` **(many2one)** — Options ⚠️ obrigatório → `product.product`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `extra_price` **(float)** — Extra Price
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `lst_price` **(float)** — Original Price 🔒 readonly
  > The sale price is managed from the product template. Click on the 'Configure Variants' button to set the extra attribute prices.
