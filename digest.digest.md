# Digest — `digest.digest`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `periodicity` **(selection)** — Periodicity ⚠️ obrigatório
  > Opções: `daily` (Daily), `weekly` (Weekly), `monthly` (Monthly), `quarterly` (Quarterly)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `next_run_date` **(date)** — Next Mailing Date
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `activated` (Activated), `deactivated` (Deactivated)
- `kpi_res_users_connected` **(boolean)** — Connected Users
- `kpi_mail_message_total` **(boolean)** — Messages Sent
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `kpi_account_total_revenue` **(boolean)** — Revenue
- `kpi_crm_lead_created` **(boolean)** — New Leads
- `kpi_crm_opportunities_won` **(boolean)** — Opportunities Won
- `kpi_helpdesk_tickets_closed` **(boolean)** — Tickets Closed
- `kpi_project_task_opened` **(boolean)** — Open Tasks
- `kpi_account_bank_cash` **(boolean)** — Bank & Cash Moves
- `kpi_hr_recruitment_new_colleagues` **(boolean)** — New Employees
- `kpi_all_sale_total` **(boolean)** — All Sales
- `kpi_website_sale_total` **(boolean)** — eCommerce Sales

## Relacionamentos

- `user_ids` **(many2many)** — Recipients → `res.users`
- `currency_id` **(many2one)** — Currency → `res.currency`
- `company_id` **(many2one)** — Company → `res.company`

## Campos Calculados (readonly)

- `available_fields` **(char)** — Available Fields 🔒 readonly
- `is_subscribed` **(boolean)** — Is user subscribed 🔒 readonly
- `kpi_res_users_connected_value` **(integer)** — Kpi Res Users Connected Value 🔒 readonly
- `kpi_mail_message_total_value` **(integer)** — Kpi Mail Message Total Value 🔒 readonly
- `kpi_account_total_revenue_value` **(monetary)** — Kpi Account Total Revenue Value 🔒 readonly
- `kpi_crm_lead_created_value` **(integer)** — Kpi Crm Lead Created Value 🔒 readonly
- `kpi_crm_opportunities_won_value` **(integer)** — Kpi Crm Opportunities Won Value 🔒 readonly
- `kpi_helpdesk_tickets_closed_value` **(integer)** — Kpi Helpdesk Tickets Closed Value 🔒 readonly
- `kpi_project_task_opened_value` **(integer)** — Kpi Project Task Opened Value 🔒 readonly
- `kpi_account_bank_cash_value` **(monetary)** — Kpi Account Bank Cash Value 🔒 readonly
- `kpi_hr_recruitment_new_colleagues_value` **(integer)** — Kpi Hr Recruitment New Colleagues Value 🔒 readonly
- `kpi_all_sale_total_value` **(monetary)** — Kpi All Sale Total Value 🔒 readonly
- `kpi_website_sale_total_value` **(monetary)** — Kpi Website Sale Total Value 🔒 readonly
