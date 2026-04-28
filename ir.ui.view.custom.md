# Custom View — `ir.ui.view.custom`

**Ordenação padrão:** `create_date desc, id desc`

---

## Campos Obrigatórios

- `ref_id` **(many2one)** — Original View ⚠️ obrigatório → `ir.ui.view`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `arch` **(text)** — View Architecture ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
