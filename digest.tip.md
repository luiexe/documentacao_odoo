# Digest Tips — `digest.tip`

**Ordenação padrão:** `sequence`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > Used to display digest tip in email template base on order
- `name` **(char)** — Name
- `tip_description` **(html)** — Tip description
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_ids` **(many2many)** — Recipients → `res.users`
  > Users having already received this tip
- `group_id` **(many2one)** — Authorized Group → `res.groups`
