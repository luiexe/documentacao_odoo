# 2-Factor Setup Wizard — `auth_totp.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório 🔒 readonly → `res.users`
- `secret` **(char)** — Secret ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `url` **(char)** — Url 🔒 readonly
- `qrcode` **(binary)** — Qrcode 🔒 readonly
- `code` **(char)** — Verification Code
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
