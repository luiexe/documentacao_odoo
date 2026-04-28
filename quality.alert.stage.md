# Quality Alert Stage — `quality.alert.stage`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `folded` **(boolean)** — Folded
- `done` **(boolean)** — Alert Processed
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `team_ids` **(many2many)** — Teams → `quality.alert.team`
