# CRM Activity Analysis — `crm.activity.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(datetime)** — Completion Date 🔒 readonly
- `lead_create_date` **(datetime)** — Creation Date 🔒 readonly
- `date_conversion` **(datetime)** — Conversion Date 🔒 readonly
- `date_deadline` **(date)** — Expected Closing 🔒 readonly
- `date_closed` **(datetime)** — Closed Date 🔒 readonly
- `body` **(html)** — Activity Description 🔒 readonly
- `lead_type` **(selection)** — Type
  > Type is used to separate Leads and Opportunities
  > Opções: `lead` (Lead), `opportunity` (Opportunity)
- `active` **(boolean)** — Active 🔒 readonly
- `won_status` **(selection)** — Is Won 🔒 readonly
  > Opções: `won` (Won), `lost` (Lost), `pending` (Pending)

## Relacionamentos

- `author_id` **(many2one)** — Assigned To 🔒 readonly → `res.partner`
- `user_id` **(many2one)** — Salesperson 🔒 readonly → `res.users`
- `team_id` **(many2one)** — Sales Team 🔒 readonly → `crm.team`
- `lead_id` **(many2one)** — Opportunity 🔒 readonly → `crm.lead`
- `subtype_id` **(many2one)** — Subtype 🔒 readonly → `mail.message.subtype`
- `mail_activity_type_id` **(many2one)** — Activity Type 🔒 readonly → `mail.activity.type`
- `country_id` **(many2one)** — Country 🔒 readonly → `res.country`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `stage_id` **(many2one)** — Stage 🔒 readonly → `crm.stage`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `tag_ids` **(many2many)** — Tags 🔒 readonly → `crm.tag`
  > Classify and analyze your lead/opportunity categories like: Training, Service
