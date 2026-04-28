# Planning Recurrence — `planning.recurrency`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `repeat_interval` **(integer)** — Repeat Every ⚠️ obrigatório
- `repeat_unit` **(selection)** — Repeat Unit ⚠️ obrigatório
  > Opções: `day` (Days), `week` (Weeks), `month` (Months), `year` (Years)
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `repeat_type` **(selection)** — Weeks
  > Opções: `forever` (Forever), `until` (Until), `x_times` (Number of Repetitions)
- `repeat_until` **(datetime)** — Repeat Until
  > Up to which date should the plannings be repeated
- `repeat_number` **(integer)** — Repetitions
  > No Of Repetitions of the plannings
- `last_generated_end_datetime` **(datetime)** — Last Generated End Datetime 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `slot_ids` **(one2many)** — Related Planning Entries → `planning.slot`
