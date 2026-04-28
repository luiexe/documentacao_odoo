# Sale Loyalty - Reward Selection Wizard — `sale.loyalty.reward.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `order_id` **(many2one)** — Order ⚠️ obrigatório → `sale.order`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `reward_ids` **(many2many)** — Reward 🔒 readonly → `loyalty.reward`
- `selected_reward_id` **(many2one)** — Selected Reward → `loyalty.reward`
- `reward_product_ids` **(many2many)** — Reward Products 🔒 readonly → `product.product`
  > These are the products that can be claimed with this rule.
- `selected_product_id` **(many2one)** — Selected Product → `product.product`

## Campos Calculados (readonly)

- `multi_product_reward` **(boolean)** — Multi Product 🔒 readonly
