# Personal Task Stage — `project.task.stage.personal`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `task_id` **(many2one)** — Task ⚠️ obrigatório → `project.task`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `stage_id` **(many2one)** — Stage → `project.task.type`
