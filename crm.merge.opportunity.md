# Merge Opportunities — `crm.merge.opportunity`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `opportunity_ids` **(many2many)** — Leads/Opportunities → `crm.lead`
- `user_id` **(many2one)** — Salesperson → `res.users`
- `team_id` **(many2one)** — Sales Team → `crm.team`
