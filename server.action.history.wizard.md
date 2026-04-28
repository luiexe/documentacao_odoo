# Server Action History Wizard — `server.action.history.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `revision` **(many2one)** — Revision ⚠️ obrigatório → `ir.actions.server.history`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `action_id` **(many2one)** — Action → `ir.actions.server`

## Campos Calculados (readonly)

- `code_diff` **(html)** — Code Diff 🔒 readonly
- `current_code` **(text)** — Python Code 🔒 readonly
  > Write Python code that the action will execute. Some variables are available for use; help about python expression is given in the help tab.
