# User, Change Password Wizard — `change.password.user`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `wizard_id` **(many2one)** — Wizard ⚠️ obrigatório → `change.password.wizard`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `user_login` **(char)** — User Login 🔒 readonly
- `new_passwd` **(char)** — New Password
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
