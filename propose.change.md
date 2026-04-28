# Propose a change in the production — `propose.change`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `workorder_id` **(many2one)** — Workorder ⚠️ obrigatório → `mrp.workorder`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `title` **(char)** — Title
- `note` **(html)** — New Instruction
- `comment` **(char)** — Comment
- `picture` **(binary)** — Picture
- `change_type` **(selection)** — Type of Change
  > Opções: `update_step` (Update Current Step), `remove_step` (Remove Current Step), `set_picture` (Set Picture)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `step_id` **(many2one)** — Step to change → `quality.check`
