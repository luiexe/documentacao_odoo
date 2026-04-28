# Sales Achievement Report — `sale.commission.achievement.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `achieved` **(monetary)** — Achieved 🔒 readonly
- `target_amount` **(monetary)** — Target Amount 🔒 readonly
- `commission_target_amount` **(monetary)** — Commission Target Amount 🔒 readonly
  > Sum of target amount per plan paid on the same date
- `target_rate` **(float)** — Achieved Rate 🔒 readonly
  > Achieved over the target of that period, meaningless in group by
- `commission_rate` **(float)** — Commission Rate 🔒 readonly
  > Achieved over the commission target amount
- `date` **(date)** — Date 🔒 readonly
- `related_res_model` **(char)** — Related Res Model 🔒 readonly
- `related_res_id` **(many2one_reference)** — Related 🔒 readonly

## Relacionamentos

- `target_id` **(many2one)** — Period 🔒 readonly → `sale.commission.plan.target`
- `plan_id` **(many2one)** — Commission Plan 🔒 readonly → `sale.commission.plan`
- `user_id` **(many2one)** — Sales Person 🔒 readonly → `res.users`
- `team_id` **(many2one)** — Sales Team 🔒 readonly → `crm.team`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
