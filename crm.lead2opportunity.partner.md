# Convert Lead to Opportunity (not in mass) — `crm.lead2opportunity.partner`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `action` **(selection)** — Related Customer ⚠️ obrigatório
  > Opções: `create` (Create a new customer), `exist` (Link to an existing customer)
- `lead_id` **(many2one)** — Associated Lead ⚠️ obrigatório → `crm.lead`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(selection)** — Conversion Action
  > Opções: `convert` (Convert to opportunity), `merge` (Merge with existing opportunities)
- `force_assignment` **(boolean)** — Force assignment
  > If checked, forces salesman to be updated on updated opportunities even if already set.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `duplicated_lead_ids` **(many2many)** — Opportunities → `crm.lead`
- `commercial_partner_id` **(many2one)** — Company → `res.partner`
- `partner_id` **(many2one)** — Customer → `res.partner`
- `user_id` **(many2one)** — Salesperson → `res.users`
- `team_id` **(many2one)** — Sales Team → `crm.team`

## Campos Calculados (readonly)

- `lead_partner_name` **(char)** — Company Name 🔒 readonly
- `lead_contact_name` **(char)** — Contact Name 🔒 readonly
