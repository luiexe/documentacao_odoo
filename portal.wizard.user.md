# Portal User Config — `portal.wizard.user`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `wizard_id` **(many2one)** — Wizard ⚠️ obrigatório → `portal.wizard`
- `partner_id` **(many2one)** — Contact ⚠️ obrigatório 🔒 readonly → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `email` **(char)** — Email
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — User 🔒 readonly → `res.users`

## Campos Calculados (readonly)

- `login_date` **(datetime)** — Latest Authentication 🔒 readonly
- `is_portal` **(boolean)** — Is Portal 🔒 readonly
- `is_internal` **(boolean)** — Is Internal 🔒 readonly
- `email_state` **(selection)** — Status 🔒 readonly
  > Opções: `ok` (Valid), `ko` (Invalid), `exist` (Already Registered)
