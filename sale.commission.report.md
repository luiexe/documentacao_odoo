# Sales Commission Report — `sale.commission.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `target_amount` **(monetary)** — Target Amount 🔒 readonly
- `achieved` **(monetary)** — Achieved 🔒 readonly
- `achieved_rate` **(float)** — Achieved Rate 🔒 readonly
- `commission` **(monetary)** — Commission 🔒 readonly
- `payment_date` **(date)** — Payment Date 🔒 readonly
- `forecast` **(monetary)** — Forecast 🔒 readonly

## Relacionamentos

- `target_id` **(many2one)** — Period 🔒 readonly → `sale.commission.plan.target`
- `plan_id` **(many2one)** — Commission Plan 🔒 readonly → `sale.commission.plan`
- `user_id` **(many2one)** — Sales Person 🔒 readonly → `res.users`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `forecast_id` **(many2one)** — fc → `sale.commission.plan.target.forecast`

## Campos Calculados (readonly)

- `date_from` **(date)** — From 🔒 readonly
- `date_to` **(date)** — To 🔒 readonly
- `notes` **(text)** — Notes 🔒 readonly
