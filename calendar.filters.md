# Calendar Filters — `calendar.filters`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — Me ⚠️ obrigatório → `res.users`
- `partner_id` **(many2one)** — Employee ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `partner_checked` **(boolean)** — Checked
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
