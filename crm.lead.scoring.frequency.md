# Lead Scoring Frequency — `crm.lead.scoring.frequency`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `variable` **(char)** — Variable
- `value` **(char)** — Value
- `won_count` **(float)** — Won Count
- `lost_count` **(float)** — Lost Count
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `team_id` **(many2one)** — Sales Team → `crm.team`
