# Appointment Question Answers — `appointment.answer`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `question_id` **(many2one)** — Question ⚠️ obrigatório → `appointment.question`
- `name` **(char)** — Answer ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
