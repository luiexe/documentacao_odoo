# Account Return Check Template — `account.return.check.template`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Title ⚠️ obrigatório
- `return_type` **(many2one)** — Tax Return/Audit ⚠️ obrigatório → `account.return.type`
- `cycle` **(selection)** — Cycle ⚠️ obrigatório
  > Opções: `regulatory_compliance` (Regulatory compliance), `treasury_financing` (Treasury and financing), `purchases` (Purchases), `operating_expenses` (Operating expenses), `sales` (Sales), `inventory` (Inventory), `fixed_assets` (Fixed assets), `payroll` (Payroll), `state` (Government), `equity` (Equity), `other` (Others)
- `type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `check` (Check), `file` (Upload Document)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code` **(char)** — Code
- `additional_action_domain` **(char)** — Additional Action Domain
- `additional_action_context` **(char)** — Additional Action Context
- `additional_action_params` **(char)** — Additional Action Params
- `description` **(text)** — Description
- `model` **(selection)** — Model
  > Opções: `account.move.line` (Journal Item), `account.move` (Journal Entry), `account.bank.statement.line` (Bank Statement Line), `account.payment` (Payments)
- `domain` **(char)** — Domain
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `country_ids` **(many2many)** — Applicable Countries → `res.country`
- `action_id` **(many2one)** — Action on Click → `ir.actions.actions`
  > Overrides the default action based on the model and domain.
- `activity_type` **(many2one)** — Activities → `mail.activity.type`
