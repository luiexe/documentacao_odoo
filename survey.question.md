# Survey Question — `survey.question`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `title` **(char)** — Title ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(html)** — Description
  > Use this field to add additional explanations about your question or to illustrate it with pictures or a video
- `question_placeholder` **(char)** — Placeholder
- `background_image` **(binary)** — Background Image
- `sequence` **(integer)** — Sequence
- `is_page` **(boolean)** — Is a page?
- `random_questions_count` **(integer)** — # Questions Randomly Picked
  > Used on randomized sections to take X random questions from all the questions of that section.
- `question_type` **(selection)** — Question Type
  > Opções: `simple_choice` (Multiple choice: only one answer), `multiple_choice` (Multiple choice: multiple answers allowed), `text_box` (Multiple Lines Text Box), `char_box` (Single Line Text Box), `numerical_box` (Numerical Value), `scale` (Scale), `date` (Date), `datetime` (Datetime), `matrix` (Matrix)
- `is_scored_question` **(boolean)** — Scored
  > Include this question as part of quiz scoring. Requires an answer and answer score to be taken into account.
- `answer_numerical_box` **(float)** — Correct numerical answer
  > Correct number answer for this question.
- `answer_date` **(date)** — Correct date answer
  > Correct date answer for this question.
- `answer_datetime` **(datetime)** — Correct datetime answer
  > Correct date and time answer for this question.
- `answer_score` **(float)** — Score
  > Score value for a correct answer to this question.
- `save_as_email` **(boolean)** — Save as user email
  > If checked, this option will save the user's answer as its email address.
- `save_as_nickname` **(boolean)** — Save as user nickname
  > If checked, this option will save the user's answer as its nickname.
- `matrix_subtype` **(selection)** — Matrix Type
  > Opções: `simple` (One choice per row), `multiple` (Multiple choices per row)
- `scale_min` **(integer)** — Scale Minimum Value
- `scale_max` **(integer)** — Scale Maximum Value
- `scale_min_label` **(char)** — Scale Minimum Label
- `scale_mid_label` **(char)** — Scale Middle Label
- `scale_max_label` **(char)** — Scale Maximum Label
- `is_time_limited` **(boolean)** — The question is limited in time
  > Currently only supported for live sessions.
- `is_time_customized` **(boolean)** — Customized speed rewards
- `time_limit` **(integer)** — Time limit (seconds)
- `comments_allowed` **(boolean)** — Show Comments Field
- `comments_message` **(char)** — Comment Message
- `comment_count_as_answer` **(boolean)** — Comment is an answer
- `validation_required` **(boolean)** — Validate entry
- `validation_email` **(boolean)** — Input must be an email
- `validation_length_min` **(integer)** — Minimum Text Length
- `validation_length_max` **(integer)** — Maximum Text Length
- `validation_min_float_value` **(float)** — Minimum value
- `validation_max_float_value` **(float)** — Maximum value
- `validation_min_date` **(date)** — Minimum Date
- `validation_max_date` **(date)** — Maximum Date
- `validation_min_datetime` **(datetime)** — Minimum Datetime
- `validation_max_datetime` **(datetime)** — Maximum Datetime
- `validation_error_msg` **(char)** — Validation Error
- `constr_mandatory` **(boolean)** — Mandatory Answer
- `constr_error_msg` **(char)** — Error message
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `survey_id` **(many2one)** — Survey → `survey.survey`
- `question_ids` **(one2many)** — Questions 🔒 readonly → `survey.question`
- `page_id` **(many2one)** — Page 🔒 readonly → `survey.question`
- `suggested_answer_ids` **(one2many)** — Types of answers → `survey.question.answer`
  > Labels used for proposed choices: simple choice, multiple choice and columns of matrix
- `matrix_row_ids` **(one2many)** — Matrix Rows → `survey.question.answer`
  > Labels used for proposed choices: rows of matrix
- `user_input_line_ids` **(one2many)** — Answers → `survey.user_input.line`
- `triggering_question_ids` **(many2many)** — Triggering Questions 🔒 readonly → `survey.question`
  > Questions containing the triggering answer(s) to display the current question.
- `allowed_triggering_question_ids` **(many2many)** — Allowed Triggering Questions 🔒 readonly → `survey.question`
- `triggering_answer_ids` **(many2many)** — Triggering Answers → `survey.question.answer`
  > Picking any of these answers will trigger this question. Leave the field empty if the question should always be displayed.

## Campos Calculados (readonly)

- `background_image_url` **(char)** — Background Url 🔒 readonly
- `scoring_type` **(selection)** — Scoring Type 🔒 readonly
  > Opções: `no_scoring` (No scoring), `scoring_with_answers_after_page` (Scoring with answers after each page), `scoring_with_answers` (Scoring with answers at the end), `scoring_without_answers` (Scoring without answers)
- `session_available` **(boolean)** — Live Session available 🔒 readonly
- `survey_session_speed_rating` **(boolean)** — Reward quick answers 🔒 readonly
  > Attendees get more points if they answer quickly
- `survey_session_speed_rating_time_limit` **(integer)** — General Time limit (seconds) 🔒 readonly
  > Default time given to receive additional points for right answers
- `questions_selection` **(selection)** — Question Selection 🔒 readonly
  > If randomized is selected, add the number of random questions next to the section.
  > Opções: `all` (All questions), `random` (Randomized per Section)
- `has_image_only_suggested_answer` **(boolean)** — Has image only suggested answer 🔒 readonly
- `is_placed_before_trigger` **(boolean)** — Is misplaced? 🔒 readonly
  > Is this question placed before any of its trigger questions?
- `survey_type` **(selection)** — Survey Type 🔒 readonly
  > Opções: `survey` (Survey), `live_session` (Live session), `assessment` (Assessment), `custom` (Custom), `appraisal` (Appraisal)
- `generate_lead` **(boolean)** — Lead Generating 🔒 readonly
  > At least one of the question answers can generate leads.
