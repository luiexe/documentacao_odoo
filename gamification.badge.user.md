# Gamification User Badge — `gamification.badge.user`

**Ordenação padrão:** `create_date desc`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `badge_id` **(many2one)** — Badge ⚠️ obrigatório → `gamification.badge`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `comment` **(text)** — Comment
- `badge_name` **(char)** — Badge Name
- `level` **(selection)** — Badge Level 🔒 readonly
  > Opções: `bronze` (Bronze), `silver` (Silver), `gold` (Gold)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_partner_id` **(many2one)** — Related Partner 🔒 readonly → `res.partner`
  > Partner-related data of the user
- `sender_id` **(many2one)** — Sender → `res.users`
- `challenge_id` **(many2one)** — Challenge → `gamification.challenge`
- `employee_id` **(many2one)** — Employee → `hr.employee`

## Campos Calculados (readonly)

- `has_edit_delete_access` **(boolean)** — Has Edit Delete Access 🔒 readonly
