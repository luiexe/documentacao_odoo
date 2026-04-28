# Helpdesk Tag Assignment — `helpdesk.tag.assignment`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `tag_id` **(many2one)** — Ticket Tag ⚠️ obrigatório → `helpdesk.tag`
- `user_ids` **(many2many)** — Team Members ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `team_id` **(many2one)** — Team → `helpdesk.team`
