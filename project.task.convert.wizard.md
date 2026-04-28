# Convert Project Tasks to Tickets — `project.task.convert.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `stage_id` **(many2one)** — Stage ⚠️ obrigatório → `helpdesk.stage`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `team_id` **(many2one)** — Team → `helpdesk.team`
