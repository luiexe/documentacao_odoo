# Commission Plan Target Forecast — `sale.commission.plan.target.forecast`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `target_id` **(many2one)** — Period ⚠️ obrigatório → `sale.commission.plan.target`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount` **(monetary)** — Forecast
- `notes` **(text)** — Notes
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `plan_id` **(many2one)** — Plan → `sale.commission.plan`
- `team_id` **(many2one)** — User Sales Team 🔒 readonly → `crm.team`
  > Main user sales team. Used notably for pipeline, or to set sales team in invoicing or subscription.
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
