# Server Action History — `ir.actions.server.history`

**Ordenação padrão:** `create_date desc, id desc`

---

## Campos Obrigatórios

- `action_id` **(many2one)** — Action ⚠️ obrigatório → `ir.actions.server`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code` **(text)** — Code
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
