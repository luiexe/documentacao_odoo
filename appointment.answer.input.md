# Appointment Answer Inputs — `appointment.answer.input`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `question_id` **(many2one)** — Question ⚠️ obrigatório → `appointment.question`
- `appointment_type_id` **(many2one)** — Appointment Type ⚠️ obrigatório → `appointment.type`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `value_text_box` **(text)** — Text Answer
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `value_answer_id` **(many2one)** — Selected Answer → `appointment.answer`
- `calendar_event_id` **(many2one)** — Calendar Event → `calendar.event`
- `partner_id` **(many2one)** — Customer → `res.partner`
- `calendar_booking_id` **(many2one)** — Meeting Booking → `calendar.booking`

## Campos Calculados (readonly)

- `question_type` **(selection)** — Answer Type 🔒 readonly
  > Opções: `char` (Single line text), `text` (Multi-line text), `phone` (Phone Number), `select` (Dropdown (one answer)), `radio` (Radio (one answer)), `checkbox` (Checkboxes (multiple answers))
