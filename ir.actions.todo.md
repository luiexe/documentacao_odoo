# Configuration Wizards — `ir.actions.todo`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `action_id` **(many2one)** — Action ⚠️ obrigatório → `ir.actions.actions`
- `state` **(selection)** — Status ⚠️ obrigatório
  > Opções: `open` (To Do), `done` (Done)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `name` **(char)** — Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
