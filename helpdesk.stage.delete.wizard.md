# Helpdesk Stage Delete Wizard — `helpdesk.stage.delete.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `team_ids` **(many2many)** — Helpdesk Teams → `helpdesk.team`
- `stage_ids` **(many2many)** — Stages To Delete → `helpdesk.stage`

## Campos Calculados (readonly)

- `ticket_count` **(integer)** — Number of Tickets 🔒 readonly
- `stages_active` **(boolean)** — Stages Active 🔒 readonly
