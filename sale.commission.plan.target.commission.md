# Commission Plan Target Commission — `sale.commission.plan.target.commission`

**Ordenação padrão:** `amount, id`

---

## Campos Obrigatórios

- `target_rate` **(float)** — Target completion (%) ⚠️ obrigatório
- `amount` **(monetary)** — Commission ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount_rate` **(float)** — OTC %
  > On Target Commission rate
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `plan_id` **(many2one)** — Plan → `sale.commission.plan`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
