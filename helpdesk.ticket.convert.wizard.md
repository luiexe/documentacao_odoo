# Convert Helpdesk Tickets to Tasks — `helpdesk.ticket.convert.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `stage_id` **(many2one)** — Stage ⚠️ obrigatório → `project.task.type`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `project_id` **(many2one)** — Project → `project.project`
