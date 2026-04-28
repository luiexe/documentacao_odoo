# Schedule — `planning.planning`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `start_datetime` **(datetime)** — Start Date ⚠️ obrigatório
- `end_datetime` **(datetime)** — Stop Date ⚠️ obrigatório
- `access_token` **(char)** — Security Token ⚠️ obrigatório 🔒 readonly
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
  > Company linked to the material resource. Leave empty for the resource to be available in every company.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `include_unassigned` **(boolean)** — Includes Open Shifts
- `is_planning_preview` **(boolean)** — Is Planning Preview
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `date_start` **(date)** — Date Start 🔒 readonly
- `date_end` **(date)** — Date End 🔒 readonly
- `allow_self_unassign` **(boolean)** — Let Employee Unassign Themselves 🔒 readonly
- `self_unassign_days_before` **(integer)** — Days before shift for unassignment 🔒 readonly
  > Deadline in days for shift unassignment
