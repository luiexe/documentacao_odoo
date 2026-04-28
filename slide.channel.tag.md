# Channel/Course Tag — `slide.channel.tag`

**Ordenação padrão:** `group_sequence asc, sequence asc`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `sequence` **(integer)** — Sequence ⚠️ obrigatório
- `group_id` **(many2one)** — Group ⚠️ obrigatório → `slide.channel.tag.group`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `group_sequence` **(integer)** — Group sequence 🔒 readonly
- `color` **(integer)** — Color Index
  > Tag color used in both backend and website. No color means no display in kanban or front-end, to distinguish internal tags from public categorization tags
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `channel_ids` **(many2many)** — Channels → `slide.channel`
