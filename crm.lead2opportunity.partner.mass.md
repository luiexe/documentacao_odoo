# Convert Lead to Opportunity (in mass) — `crm.lead2opportunity.partner.mass`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `action` **(selection)** — Related Customer ⚠️ obrigatório
  > Opções: `create` (Create a new customer), `exist` (Link to an existing customer), `each_exist_or_create` (Use existing partner or create)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(selection)** — Conversion Action
  > Opções: `convert` (Convert to opportunity), `merge` (Merge with existing opportunities)
- `force_assignment` **(boolean)** — Force assignment
  > If checked, forces salesman to be updated on updated opportunities even if already set.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `deduplicate` **(boolean)** — Apply deduplication
  > Merge with existing leads/opportunities of each partner

## Relacionamentos

- `lead_id` **(many2one)** — Associated Lead → `crm.lead`
- `duplicated_lead_ids` **(many2many)** — Opportunities → `crm.lead`
- `commercial_partner_id` **(many2one)** — Company → `res.partner`
- `partner_id` **(many2one)** — Customer → `res.partner`
- `user_id` **(many2one)** — Salesperson → `res.users`
- `team_id` **(many2one)** — Sales Team → `crm.team`
- `lead_tomerge_ids` **(many2many)** — Active Leads → `crm.lead`
- `user_ids` **(many2many)** — Salespersons → `res.users`

## Campos Calculados (readonly)

- `lead_partner_name` **(char)** — Company Name 🔒 readonly
- `lead_contact_name` **(char)** — Contact Name 🔒 readonly
