# Product Value — `product.value`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `value` **(monetary)** — Value ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `date` **(datetime)** — Date ⚠️ obrigatório
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(char)** — Description
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_id` **(many2one)** — Product → `product.product`
- `lot_id` **(many2one)** — Lot → `stock.lot`
- `move_id` **(many2one)** — Move → `stock.move`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `current_value` **(monetary)** — Current Value 🔒 readonly
  > The current value of the move. It's zero if the move is not valued.
- `current_value_details` **(char)** — Current Value Details 🔒 readonly
- `current_value_description` **(text)** — Current Value Description 🔒 readonly
- `computed_value_description` **(text)** — Computed Value Description 🔒 readonly
