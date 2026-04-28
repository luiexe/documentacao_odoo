# Module Activation Request — `base.module.install.request`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `module_id` **(many2one)** — Module ⚠️ obrigatório 🔒 readonly → `ir.module.module`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `body_html` **(html)** — Body
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_ids` **(many2many)** — Send to: 🔒 readonly → `res.users`
