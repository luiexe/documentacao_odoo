# CRM Lead Mining Request — `crm.iap.lead.mining.request`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Request Number ⚠️ obrigatório 🔒 readonly
- `state` **(selection)** — Status ⚠️ obrigatório
  > Opções: `draft` (Draft), `error` (Error), `done` (Done)
- `lead_number` **(integer)** — Number of Leads ⚠️ obrigatório
- `search_type` **(selection)** — Target ⚠️ obrigatório
  > Opções: `companies` (Companies), `people` (Companies and their Contacts)
- `lead_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `lead` (Leads), `opportunity` (Opportunities)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `error_type` **(selection)** — Error Type 🔒 readonly
  > Opções: `credits` (Insufficient Credits), `no_result` (No Result)
- `filter_on_size` **(boolean)** — Filter on Size
- `company_size_min` **(integer)** — Size
- `company_size_max` **(integer)** — Company Size Max
- `contact_number` **(integer)** — Number of Contacts
- `contact_filter_type` **(selection)** — Filter on
  > Opções: `role` (Role), `seniority` (Seniority)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `team_id` **(many2one)** — Sales Team → `crm.team`
- `user_id` **(many2one)** — Salesperson → `res.users`
- `tag_ids` **(many2many)** — Tags → `crm.tag`
- `lead_ids` **(one2many)** — Generated Lead / Opportunity → `crm.lead`
- `country_ids` **(many2many)** — Countries → `res.country`
- `state_ids` **(many2many)** — States → `res.country.state`
- `available_state_ids` **(one2many)** — Available State 🔒 readonly → `res.country.state`
- `industry_ids` **(many2many)** — Industries → `crm.iap.lead.industry`
- `preferred_role_id` **(many2one)** — Preferred Role → `crm.iap.lead.role`
- `role_ids` **(many2many)** — Other Roles → `crm.iap.lead.role`
- `seniority_id` **(many2one)** — Seniority → `crm.iap.lead.seniority`

## Campos Calculados (readonly)

- `lead_count` **(integer)** — Number of Generated Leads 🔒 readonly
- `lead_credits` **(char)** — Lead Credits 🔒 readonly
- `lead_contacts_credits` **(char)** — Lead Contacts Credits 🔒 readonly
- `lead_total_credits` **(char)** — Lead Total Credits 🔒 readonly
