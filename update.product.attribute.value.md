# Update product attribute value — `update.product.attribute.value`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `attribute_value_id` **(many2one)** — Attribute Value ⚠️ obrigatório → `product.attribute.value`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `mode` **(selection)** — Mode
  > Opções: `add` (Add to existing products), `update_extra_price` (Update the extra price on existing products)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `message` **(char)** — Message 🔒 readonly
- `product_count` **(integer)** — Product Count 🔒 readonly
