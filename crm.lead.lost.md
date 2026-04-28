# Get Lost Reason — `crm.lead.lost`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lost_feedback` **(html)** — Closing Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `lead_ids` **(many2many)** — Leads → `crm.lead`
- `lost_reason_id` **(many2one)** — Lost Reason → `crm.lost.reason`
