# Appointment Questions — `appointment.question`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `name` **(char)** — Question ⚠️ obrigatório
- `question_type` **(selection)** — Answer Type ⚠️ obrigatório
  > Opções: `char` (Single line text), `text` (Multi-line text), `phone` (Phone Number), `select` (Dropdown (one answer)), `radio` (Radio (one answer)), `checkbox` (Checkboxes (multiple answers))

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `is_default` **(boolean)** — Default question
  > Include by default in new appointment types.
- `is_reusable` **(boolean)** — Is Reusable
  > Will appear in the list of available questions when adding one in any appointment. Always true for default questions.
- `placeholder` **(char)** — Placeholder
- `question_required` **(boolean)** — Mandatory Answer
- `extra_comment` **(html)** — Extra Comment
  > This will appear below the question in the appointment form.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `appointment_type_ids` **(many2many)** — Appointment Types → `appointment.type`
- `answer_ids` **(one2many)** — Available Answers → `appointment.answer`
- `answer_input_ids` **(one2many)** — Submitted Answers → `appointment.answer.input`

## Campos Calculados (readonly)

- `appointment_count` **(integer)** — # Appointments 🔒 readonly
