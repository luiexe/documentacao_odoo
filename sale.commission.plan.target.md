# Commission Plan Target — `sale.commission.plan.target`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Period ⚠️ obrigatório 🔒 readonly
- `date_from` **(date)** — From ⚠️ obrigatório 🔒 readonly
- `date_to` **(date)** — To ⚠️ obrigatório 🔒 readonly
- `amount` **(monetary)** — Target ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `payment_date` **(date)** — Payment Date
- `payment_amount` **(monetary)** — Payment Amount 🔒 readonly
  > Sum of amounts paid on the same payment date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `plan_id` **(many2one)** — Plan → `sale.commission.plan`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
