# Create a topic that leverages instructions and tools to direct Odoo AI in assisting the user with their tasks. — `ai.topic`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Title ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
- `instructions` **(text)** — Instructions
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `tool_ids` **(many2many)** — AI Tools → `ir.actions.server`
