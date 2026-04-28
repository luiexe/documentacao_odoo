# Workcenter Productivity Losses — `mrp.workcenter.productivity.loss`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Blocking Reason ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `manual` **(boolean)** — Is a Blocking Reason
- `loss_type` **(selection)** — Effectiveness Category
  > Opções: `availability` (Availability), `performance` (Performance), `quality` (Quality), `productive` (Productive)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `loss_id` **(many2one)** — Category → `mrp.workcenter.productivity.loss.type`
