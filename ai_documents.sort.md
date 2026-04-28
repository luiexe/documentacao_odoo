# Ai Documents Sort — `ai_documents.sort`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `folder_id` **(many2one)** — Folder ⚠️ obrigatório → `documents.document`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `ai_sort_prompt` **(html)** — AI Folder Sort Prompt
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `ai_tool_ids` **(many2many)** — Additional Tools → `ir.actions.server`
- `allowed_tools_ids` **(many2many)** — Allowed Tools 🔒 readonly → `ir.actions.server`

## Campos Calculados (readonly)

- `model` **(char)** — Model 🔒 readonly
- `relation` **(char)** — Relation 🔒 readonly
- `is_ai_sort_prompt_set` **(boolean)** — Is Prompt Set 🔒 readonly
