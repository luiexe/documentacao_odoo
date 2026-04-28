# Authentication Device — `auth_totp.device`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Description ⚠️ obrigatório 🔒 readonly
- `user_id` **(many2one)** — User ⚠️ obrigatório 🔒 readonly → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `scope` **(char)** — Scope 🔒 readonly
- `create_date` **(datetime)** — Creation Date 🔒 readonly
- `expiration_date` **(datetime)** — Expiration Date 🔒 readonly
