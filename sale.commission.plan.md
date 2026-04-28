# Commission Plan — `sale.commission.plan`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `name` **(char)** — Name ⚠️ obrigatório
- `date_from` **(date)** — From ⚠️ obrigatório
- `date_to` **(date)** — To ⚠️ obrigatório
- `periodicity` **(selection)** — Periodicity ⚠️ obrigatório
  > Opções: `month` (Monthly), `quarter` (Quarterly), `year` (Yearly)
- `type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `target` (Targets), `achieve` (Achievements)
- `user_type` **(selection)** — User Type ⚠️ obrigatório
  > Opções: `person` (Salesperson), `team` (Sales Team)
- `state` **(selection)** — State ⚠️ obrigatório
  > Opções: `draft` (Draft), `approved` (Approved), `done` (Done), `cancel` (Cancelled)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `commission_amount` **(monetary)** — On Target Commission
  > OTC
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `team_id` **(many2one)** — Sale team → `crm.team`
- `achievement_ids` **(one2many)** — Achievement → `sale.commission.plan.achievement`
- `target_ids` **(one2many)** — Target → `sale.commission.plan.target`
- `target_commission_ids` **(one2many)** — Target Commission → `sale.commission.plan.target.commission`
- `user_ids` **(one2many)** — User → `sale.commission.plan.user`

## Campos Calculados (readonly)

- `target_commission_graph` **(text)** — Target Commission Graph 🔒 readonly
