# Mail Activity Schedule Line — `mail.activity.schedule.line`

**Ordenação padrão:** `line_date_deadline asc, id asc`

---

## Campos Obrigatórios

- `activity_schedule_id` **(many2one)** — Activity Schedule ⚠️ obrigatório → `mail.activity.schedule`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `line_description` **(char)** — Line Description
- `line_date_deadline` **(date)** — Date Deadline
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `responsible_user_id` **(many2one)** — Responsible User → `res.users`
