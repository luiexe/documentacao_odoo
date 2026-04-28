# User Settings for Embedded Actions — `res.users.settings.embedded.action`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_setting_id` **(many2one)** — User Setting ⚠️ obrigatório → `res.users.settings`
- `action_id` **(many2one)** — Action ⚠️ obrigatório → `ir.actions.act_window`
- `res_model` **(char)** — Res Model ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_id` **(integer)** — Res
- `embedded_actions_order` **(char)** — List order of embedded action ids
- `embedded_actions_visibility` **(char)** — List visibility of embedded actions ids
- `embedded_visibility` **(boolean)** — Is top bar visible
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
