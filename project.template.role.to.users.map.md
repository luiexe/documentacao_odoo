# Project role to users mapping — `project.template.role.to.users.map`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `role_id` **(many2one)** — Project Role ⚠️ obrigatório → `project.role`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `wizard_id` **(many2one)** — Wizard → `project.template.create.wizard`
- `user_ids` **(many2many)** — Assignees → `res.users`
