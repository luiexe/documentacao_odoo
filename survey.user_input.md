# Survey User Input — `survey.user_input`

**Ordenação padrão:** `create_date desc`

---

## Campos Obrigatórios

- `survey_id` **(many2one)** — Survey ⚠️ obrigatório 🔒 readonly → `survey.survey`
- `access_token` **(char)** — Identification token ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `start_datetime` **(datetime)** — Start date and time 🔒 readonly
- `end_datetime` **(datetime)** — End date and time 🔒 readonly
- `deadline` **(datetime)** — Deadline
  > Datetime until customer can open the survey and submit answers
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `new` (New), `in_progress` (In Progress), `done` (Completed)
- `test_entry` **(boolean)** — Test Entry 🔒 readonly
- `invite_token` **(char)** — Invite token 🔒 readonly
- `email` **(char)** — Email 🔒 readonly
- `nickname` **(char)** — Nickname
  > Attendee nickname, mainly used to identify them in the survey session leaderboard.
- `scoring_percentage` **(float)** — Score (%) 🔒 readonly
- `scoring_total` **(float)** — Total Score 🔒 readonly
- `scoring_success` **(boolean)** — Quiz Passed 🔒 readonly
- `survey_first_submitted` **(boolean)** — Survey First Submitted
- `is_session_answer` **(boolean)** — Is in a Session
  > Is that user input part of a survey session or not.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `lang_id` **(many2one)** — Language → `res.lang`
- `last_displayed_page_id` **(many2one)** — Last displayed question/page → `survey.question`
- `partner_id` **(many2one)** — Contact 🔒 readonly → `res.partner`
- `user_input_line_ids` **(one2many)** — Answers → `survey.user_input.line`
- `predefined_question_ids` **(many2many)** — Predefined Questions 🔒 readonly → `survey.question`
- `lead_id` **(many2one)** — Lead → `crm.lead`
- `appraisal_id` **(many2one)** — Appraisal → `hr.appraisal`
- `requested_by` **(many2one)** — Requested by 🔒 readonly → `res.partner`
  > Partner-related data of the user
- `slide_id` **(many2one)** — Related course slide → `slide.slide`
  > The related course slide when there is no membership information
- `slide_partner_id` **(many2one)** — Subscriber information → `slide.slide.partner`
  > Slide membership information for the logged in user

## Campos Calculados (readonly)

- `scoring_type` **(selection)** — Scoring 🔒 readonly
  > Opções: `no_scoring` (No scoring), `scoring_with_answers_after_page` (Scoring with answers after each page), `scoring_with_answers` (Scoring with answers at the end), `scoring_without_answers` (Scoring without answers)
- `is_attempts_limited` **(boolean)** — Limited number of attempts 🔒 readonly
  > Check this option if you want to limit the number of attempts per user
- `attempts_limit` **(integer)** — Number of attempts 🔒 readonly
- `attempts_count` **(integer)** — Attempts Count 🔒 readonly
- `attempts_number` **(integer)** — Attempt n° 🔒 readonly
- `survey_time_limit_reached` **(boolean)** — Survey Time Limit Reached 🔒 readonly
- `question_time_limit_reached` **(boolean)** — Question Time Limit Reached 🔒 readonly
