# Prompt that can be attached to AI UI rules for quick access by the user. — `ai.prompt.button`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — AI Prompt
  > The prompt sent to the AI when clicked on
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `composer_id` **(many2one)** — Composer → `ai.composer`
