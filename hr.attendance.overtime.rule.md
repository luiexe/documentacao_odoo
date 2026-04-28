# Overtime Rule — `hr.attendance.overtime.rule`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `base_off` **(selection)** — Based Off ⚠️ obrigatório
  > Base for overtime calculation. Use 'Quantity' when overtime hours are those in excess of a certain amount per day/week. Use 'Timing' when overtime hours happen on specific days or at specific times
  > Opções: `quantity` (Quantity), `timing` (Timing)
- `ruleset_id` **(many2one)** — Ruleset ⚠️ obrigatório → `hr.attendance.overtime.ruleset`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(html)** — Description
- `timing_type` **(selection)** — Timing Type
  > Opções: `work_days` (On any working day), `non_work_days` (On any non-working day), `leave` (When employee is off), `schedule` (Outside of a specific schedule)
- `timing_start` **(float)** — From
- `timing_stop` **(float)** — To
- `expected_hours_from_contract` **(boolean)** — Hours from employee schedule
  > The attendance can go into negative extra hours to represent the missing hours compared to what is expected if the Absence Management setting is enabled.
- `expected_hours` **(float)** — Usual work hours
- `quantity_period` **(selection)** — Quantity Period
  > Opções: `day` (Day), `week` (Week)
- `sequence` **(integer)** — Sequence
- `paid` **(boolean)** — Pay Extra Hours
- `amount_rate` **(float)** — Rate
- `employee_tolerance` **(float)** — Employee Tolerance
- `employer_tolerance` **(float)** — Employer Tolerance
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `resource_calendar_id` **(many2one)** — Schedule → `resource.calendar`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `information_display` **(char)** — Information 🔒 readonly
