# Planning Preview — `planning.preview`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `slot_count` **(integer)** — Slot Count 🔒 readonly
