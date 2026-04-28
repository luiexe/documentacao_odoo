# Add or remove leaves from appointments — `appointment.manage.leaves`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `appointment_resource_ids` **(many2many)** — Resources ⚠️ obrigatório → `appointment.resource`
- `leave_start_dt` **(datetime)** — Start Date ⚠️ obrigatório
- `leave_end_dt` **(datetime)** — End Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `reason` **(char)** — Reason
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
