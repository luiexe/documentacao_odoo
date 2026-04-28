# Sales Team Member — `crm.team.member`

**Ordenação padrão:** `create_date ASC, id`

---

## Campos Obrigatórios

- `crm_team_id` **(many2one)** — Sales Team ⚠️ obrigatório → `crm.team`
- `user_id` **(many2one)** — Salesperson ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `name` **(char)** — Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `assignment_domain` **(char)** — Assignment Domain
- `assignment_domain_preferred` **(char)** — Preference assignment Domain
- `assignment_optout` **(boolean)** — Pause assignment
- `assignment_max` **(integer)** — Average Leads Capacity (on 30 days)

## Relacionamentos

- `user_in_teams_ids` **(many2many)** — User In Teams 🔒 readonly → `res.users`
  > UX: Give users not to add in the currently chosen team to avoid duplicates
- `user_company_ids` **(many2many)** — User Company 🔒 readonly → `res.company`
  > UX: Limit to team company or all if no company
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
  > The default company for this user.

## Campos Calculados (readonly)

- `is_membership_multi` **(boolean)** — Multiple Memberships Allowed 🔒 readonly
  > If True, users may belong to several sales teams. Otherwise membership is limited to a single sales team.
- `member_warning` **(text)** — Member Warning 🔒 readonly
- `image_1920` **(binary)** — Image 🔒 readonly
- `image_128` **(binary)** — Image (128) 🔒 readonly
- `email` **(char)** — Email 🔒 readonly
- `phone` **(char)** — Phone 🔒 readonly
- `assignment_enabled` **(boolean)** — Lead Assign 🔒 readonly
- `lead_day_count` **(integer)** — Leads (last 24h) 🔒 readonly
  > Number of leads assigned to this member in the last 24 hours (lost leads excluded)
- `lead_month_count` **(integer)** — Leads (30 days) 🔒 readonly
  > Number of leads assigned to this member in the last 30 days
