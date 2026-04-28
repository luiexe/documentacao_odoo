# Create activity and todo at the same time — `mail.activity.todo.create`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `date_deadline` **(date)** — Due Date ⚠️ obrigatório
- `user_id` **(many2one)** — Assigned to ⚠️ obrigatório 🔒 readonly → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `summary` **(char)** — Summary
- `note` **(html)** — Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
