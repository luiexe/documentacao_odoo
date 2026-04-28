# Survey User Input Line — `survey.user_input.line`

**Ordenação padrão:** `question_sequence, id`

---

## Campos Obrigatórios

- `user_input_id` **(many2one)** — User Input ⚠️ obrigatório → `survey.user_input`
- `question_id` **(many2one)** — Question ⚠️ obrigatório → `survey.question`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `question_sequence` **(integer)** — Sequence 🔒 readonly
- `skipped` **(boolean)** — Skipped
- `answer_type` **(selection)** — Answer Type
  > Opções: `text_box` (Free Text), `char_box` (Text), `numerical_box` (Number), `scale` (Number), `date` (Date), `datetime` (Datetime), `suggestion` (Suggestion)
- `value_char_box` **(char)** — Text answer
- `value_numerical_box` **(float)** — Numerical answer
- `value_scale` **(integer)** — Scale value
- `value_date` **(date)** — Date answer
- `value_datetime` **(datetime)** — Datetime answer
- `value_text_box` **(text)** — Free Text answer
- `answer_score` **(float)** — Score 🔒 readonly
- `answer_is_correct` **(boolean)** — Correct 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `survey_id` **(many2one)** — Survey → `survey.survey`
- `page_id` **(many2one)** — Section → `survey.question`
- `lang_id` **(many2one)** — Language 🔒 readonly → `res.lang`
- `suggested_answer_id` **(many2one)** — Suggested answer → `survey.question.answer`
- `matrix_row_id` **(many2one)** — Row answer → `survey.question.answer`
