# Accounting Return Type — `account.return.type`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `category` **(selection)** — Type ⚠️ obrigatório
  > Opções: `account_return` (Tax Return), `audit` (Audit)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `auto_generate` **(boolean)** — Auto Generated
- `states_workflow` **(selection)** — States
  > Determines the workflow of the return.
  > Opções: `generic_state_review` (Review), `generic_state_review_submit` (Review, Submit), `generic_state_tax_report` (Review, Submit, Pay), `generic_state_only_pay` (Pay)
- `deadline_periodicity` **(selection)** — Periodicity
  > Opções: `monthly` (Monthly), `2_months` (Every 2 months), `trimester` (Quarterly), `4_months` (Every 4 months), `semester` (Semi-annually), `year` (Annually), `fiscalyear` (Fiscal Year)
- `default_deadline_periodicity` **(selection)** — Default Periodicity
  > Opções: `monthly` (Monthly), `2_months` (Every 2 months), `trimester` (Quarterly), `4_months` (Every 4 months), `semester` (Semi-annually), `year` (Annually), `fiscalyear` (Fiscal Year)
- `deadline_start_date` **(date)** — Start Date
  > Used to compute covered period based on the selected periodicity.
- `default_deadline_start_date` **(date)** — Default Start Date
- `deadline_days_delay` **(integer)** — Deadline
  > By default, Odoo applies its own deadline for returns (shown as 0). Entering a value here will override it and be used as the new deadline.
- `default_deadline_days_delay` **(integer)** — Default Deadline
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `report_id` **(many2one)** — Report → `account.report`
- `country_id` **(many2one)** — Country → `res.country`
- `payment_partner_bank_id` **(many2one)** — Payment Partner Bank → `res.partner.bank`
- `payment_partner_id` **(many2one)** — Payment Partner 🔒 readonly → `res.partner`

## Campos Calculados (readonly)

- `is_tax_return_type` **(boolean)** — Is a Tax Return Return Type 🔒 readonly
- `is_ec_sales_list_return_type` **(boolean)** — Is an EC Sales List Return Type 🔒 readonly
