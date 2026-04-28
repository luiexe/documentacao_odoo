# Default Values — `ir.default`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `field_id` **(many2one)** — Field ⚠️ obrigatório → `ir.model.fields`
- `json_value` **(char)** — Default Value (JSON format) ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `condition` **(char)** — Condition
  > If set, applies the default upon condition.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — User → `res.users`
  > If set, action binding only applies for this user.
- `company_id` **(many2one)** — Company → `res.company`
  > If set, action binding only applies for this company
