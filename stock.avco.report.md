# Stock AVCO Justifier — `stock.avco.report`

**Ordenação padrão:** `date desc, id desc`

---

## Campos Obrigatórios

- `date` **(date)** — Date ⚠️ obrigatório
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `reference` **(char)** — Reference ⚠️ obrigatório
- `description` **(text)** — Description ⚠️ obrigatório
- `res_model_name` **(selection)** — Resource Model Name ⚠️ obrigatório
  > Opções: `stock.move` (Stock Move), `product.value` (Product Value)
- `quantity` **(float)** — Added Quantity ⚠️ obrigatório
- `value` **(float)** — Value ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `added_value` **(float)** — Added Value 🔒 readonly
- `total_quantity` **(float)** — Total Quantity 🔒 readonly
- `total_value` **(float)** — Total Value 🔒 readonly
- `avco_value` **(float)** — AVCO Value 🔒 readonly
- `justification` **(text)** — Justification 🔒 readonly
