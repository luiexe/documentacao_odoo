# Work Detail — `resource.calendar.attendance`

**Ordenação padrão:** `sequence, week_type, dayofweek, hour_from`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `dayofweek` **(selection)** — Day of Week ⚠️ obrigatório
  > Opções: `0` (Monday), `1` (Tuesday), `2` (Wednesday), `3` (Thursday), `4` (Friday), `5` (Saturday), `6` (Sunday)
- `hour_from` **(float)** — Work from ⚠️ obrigatório
  > Start and End time of working. A specific value of 24:00 is interpreted as 23:59:59.999999.
- `hour_to` **(float)** — Work to ⚠️ obrigatório
- `calendar_id` **(many2one)** — Resource's Calendar ⚠️ obrigatório → `resource.calendar`
- `day_period` **(selection)** — Day Period ⚠️ obrigatório
  > Opções: `morning` (Morning), `lunch` (Break), `afternoon` (Afternoon), `full_day` (Full Day)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `duration_hours` **(float)** — Duration (hours)
- `duration_days` **(float)** — Duration (days)
- `week_type` **(selection)** — Week Number
  > Opções: `1` (Second), `0` (First)
- `display_type` **(selection)** — Display Type
  > Technical field for UX purpose.
  > Opções: `line_section` (Section)
- `sequence` **(integer)** — Sequence
  > Gives the sequence of this line when displaying the resource calendar.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `duration_based` **(boolean)** — Attendance based on duration 🔒 readonly
  > The hours will be centered around 12:00 to cover the duration for the day
- `two_weeks_calendar` **(boolean)** — Calendar in 2 weeks mode 🔒 readonly
