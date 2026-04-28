# Shift Template — `planning.slot.template`

**Ordenação padrão:** `sequence`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `name` **(char)** — Hours 🔒 readonly
- `sequence` **(integer)** — Sequence
- `start_time` **(float)** — Planned Hours
- `end_time` **(float)** — End Hour
- `duration_days` **(integer)** — Duration Days
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `role_id` **(many2one)** — Role → `planning.role`
