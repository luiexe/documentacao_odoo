# Slide Question's Answer — `slide.answer`

**Ordenação padrão:** `question_id, sequence, id`

---

## Campos Obrigatórios

- `question_id` **(many2one)** — Question ⚠️ obrigatório → `slide.question`
- `text_value` **(char)** — Answer ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `is_correct` **(boolean)** — Is correct answer
- `comment` **(text)** — Comment
  > This comment will be displayed to the user if they select this answer
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
