# Survey Label — `survey.question.answer`

**Ordenação padrão:** `question_id, sequence, id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Label Sequence order
- `value` **(char)** — Suggested value
- `value_image` **(binary)** — Image
- `value_image_filename` **(char)** — Image Filename
- `is_correct` **(boolean)** — Correct
- `answer_score` **(float)** — Score
  > A positive score indicates a correct choice; a negative or null score indicates a wrong answer
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `generate_lead` **(boolean)** — Lead creation
  > Creates a lead when participants choose this answer

## Relacionamentos

- `question_id` **(many2one)** — Question → `survey.question`
- `matrix_question_id` **(many2one)** — Question (as matrix row) → `survey.question`
- `survey_id` **(many2one)** — Survey 🔒 readonly → `survey.survey`

## Campos Calculados (readonly)

- `question_type` **(selection)** — Question Type 🔒 readonly
  > Opções: `simple_choice` (Multiple choice: only one answer), `multiple_choice` (Multiple choice: multiple answers allowed), `text_box` (Multiple Lines Text Box), `char_box` (Single Line Text Box), `numerical_box` (Numerical Value), `scale` (Scale), `date` (Date), `datetime` (Datetime), `matrix` (Matrix)
- `scoring_type` **(selection)** — Scoring Type 🔒 readonly
  > Opções: `no_scoring` (No scoring), `scoring_with_answers_after_page` (Scoring with answers after each page), `scoring_with_answers` (Scoring with answers at the end), `scoring_without_answers` (Scoring without answers)
- `value_label` **(char)** — Value Label 🔒 readonly
  > Answer label as either the value itself if not empty or a letter representing the index of the answer otherwise.
