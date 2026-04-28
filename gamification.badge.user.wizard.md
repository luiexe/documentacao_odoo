# Gamification User Badge Wizard — `gamification.badge.user.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `badge_id` **(many2one)** — Badge ⚠️ obrigatório → `gamification.badge`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `comment` **(text)** — Comment
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_id` **(many2one)** — Employee → `hr.employee`
