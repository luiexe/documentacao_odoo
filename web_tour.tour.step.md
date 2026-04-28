# Tour's step — `web_tour.tour.step`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `trigger` **(char)** — Trigger ⚠️ obrigatório
- `tour_id` **(many2one)** — Tour ⚠️ obrigatório → `web_tour.tour`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `content` **(char)** — Content
- `tooltip_position` **(selection)** — Tooltip Position
  > Opções: `bottom` (Bottom), `top` (Top), `right` (Right), `left` (left)
- `run` **(char)** — Run
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
