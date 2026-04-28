# TOTP rate limit logs — `auth.totp.rate.limit.log`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório 🔒 readonly → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `ip` **(char)** — Ip 🔒 readonly
- `limit_type` **(selection)** — Limit Type 🔒 readonly
  > Opções: `send_email` (Send Email), `code_check` (Code Checking)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
