# Lead convert to Ticket — `crm.lead.convert2ticket`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `team_id` **(many2one)** — Team ⚠️ obrigatório → `helpdesk.team`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `lead_id` **(many2one)** — Lead → `crm.lead`
- `partner_id` **(many2one)** — Customer → `res.partner`
