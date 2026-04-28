# Employee Location — `hr.employee.location`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `work_location_id` **(many2one)** — Location ⚠️ obrigatório → `hr.work.location`
- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `work_location_name` **(char)** — Location name 🔒 readonly
- `work_location_type` **(selection)** — Cover Image 🔒 readonly
  > Opções: `home` (Home), `office` (Office), `other` (Other)
- `employee_name` **(char)** — Employee Name 🔒 readonly
- `day_week_string` **(char)** — Day Week String 🔒 readonly
