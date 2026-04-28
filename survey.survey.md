# Survey — `survey.survey`

**Ordenação padrão:** `create_date DESC`

---

## Campos Obrigatórios

- `survey_type` **(selection)** — Survey Type ⚠️ obrigatório
  > Opções: `survey` (Survey), `live_session` (Live session), `assessment` (Assessment), `custom` (Custom), `appraisal` (Appraisal)
- `title` **(char)** — Survey Title ⚠️ obrigatório
- `questions_layout` **(selection)** — Pagination ⚠️ obrigatório
  > Opções: `page_per_question` (One page per question), `page_per_section` (One page per section), `one_page` (One page with all the questions)
- `questions_selection` **(selection)** — Question Selection ⚠️ obrigatório
  > If randomized is selected, you can configure the number of random questions by section. This mode is ignored in live session.
  > Opções: `all` (All questions), `random` (Randomized per Section)
- `access_mode` **(selection)** — Access Mode ⚠️ obrigatório
  > Opções: `public` (Anyone with the link), `token` (Invited people only)
- `scoring_type` **(selection)** — Scoring ⚠️ obrigatório
  > Opções: `no_scoring` (No scoring), `scoring_with_answers_after_page` (Scoring with answers after each page), `scoring_with_answers` (Scoring with answers at the end), `scoring_without_answers` (Scoring without answers)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color Index
- `description` **(html)** — Description
  > The description will be displayed on the home page of the survey. You can use this to give the purpose and guidelines to your candidates before they start it.
- `description_done` **(html)** — End Message
  > This message will be displayed when survey is completed
- `background_image` **(binary)** — Background Image
- `active` **(boolean)** — Active
- `progression_mode` **(selection)** — Display Progress as
  > If Number is selected, it will display the number of questions answered on the total number of question to answer.
  > Opções: `percent` (Percentage left), `number` (Number)
- `access_token` **(char)** — Access Token
- `users_login_required` **(boolean)** — Require Login
  > If checked, users have to login before answering even with a valid token.
- `users_can_go_back` **(boolean)** — Users can go back
  > If checked, users can go back to previous pages.
- `scoring_success_min` **(float)** — Required Score (%)
- `is_attempts_limited` **(boolean)** — Limited number of attempts
  > Check this option if you want to limit the number of attempts per user
- `attempts_limit` **(integer)** — Number of attempts
- `is_time_limited` **(boolean)** — The survey is limited in time
- `time_limit` **(float)** — Time limit (minutes)
- `certification` **(boolean)** — Is a Certification
- `certification_report_layout` **(selection)** — Certification template
  > Opções: `modern_purple` (Modern Purple), `modern_blue` (Modern Blue), `modern_gold` (Modern Gold), `classic_purple` (Classic Purple), `classic_blue` (Classic Blue), `classic_gold` (Classic Gold)
- `certification_give_badge` **(boolean)** — Give Badge
- `session_state` **(selection)** — Session State
  > Opções: `ready` (Ready), `in_progress` (In Progress)
- `session_code` **(char)** — Session Code
  > This code will be used by your attendees to reach your session. Feel free to customize it however you like!
- `session_start_time` **(datetime)** — Current Session Start Time
- `session_question_start_time` **(datetime)** — Current Question Start Time
  > The time at which the current question has started, used to handle the timer for attendees.
- `session_speed_rating` **(boolean)** — Reward quick answers
  > Attendees get more points if they answer quickly
- `session_speed_rating_time_limit` **(integer)** — Time limit (seconds)
  > Default time given to receive additional points for right answers
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `generate_lead` **(boolean)** — Lead Generating 🔒 readonly
- `certification_validity_months` **(integer)** — Validity
  > Specify the number of months the certification is valid after being awarded. Enter 0 for certifications that never expire.

## Relacionamentos

- `lang_ids` **(many2many)** — Languages → `res.lang`
  > Leave the field empty to support all installed languages.
- `user_id` **(many2one)** — Responsible → `res.users`
- `restrict_user_ids` **(many2many)** — Restricted to → `res.users`
- `question_and_page_ids` **(one2many)** — Sections and Questions → `survey.question`
- `page_ids` **(one2many)** — Pages 🔒 readonly → `survey.question`
- `question_ids` **(one2many)** — Questions 🔒 readonly → `survey.question`
- `user_input_ids` **(one2many)** — User responses 🔒 readonly → `survey.user_input`
- `certification_mail_template_id` **(many2one)** — Certified Email Template → `mail.template`
  > Automated email sent to the user when they succeed the certification, containing their certification document.
- `certification_badge_id` **(many2one)** — Certification Badge → `gamification.badge`
- `certification_badge_id_dummy` **(many2one)** — Certification Badge  🔒 readonly → `gamification.badge`
- `session_question_id` **(many2one)** — Current Question → `survey.question`
  > The current question of the survey session.
- `lead_ids` **(one2many)** — Lead → `crm.lead`
- `team_id` **(many2one)** — Assign Leads to → `crm.team`
- `spreadsheet_document_id` **(many2one)** — Spreadsheet Document → `documents.document`
- `appraisal_manager_user_ids` **(many2many)** — Appraisals Managers Users 🔒 readonly → `res.users`
  > Users allowed to view the survey used in an appraisal
- `slide_ids` **(one2many)** — Certification Slides → `slide.slide`
  > The slides this survey is linked to through the e-learning application

## Campos Calculados (readonly)

- `allowed_survey_types` **(json)** — Allowed survey types 🔒 readonly
- `background_image_url` **(char)** — Background Url 🔒 readonly
- `question_count` **(integer)** — # Questions 🔒 readonly
- `users_can_signup` **(boolean)** — Users can signup 🔒 readonly
- `answer_count` **(integer)** — Registered 🔒 readonly
- `answer_done_count` **(integer)** — Attempts 🔒 readonly
- `answer_score_avg` **(float)** — Avg Score (%) 🔒 readonly
- `answer_duration_avg` **(float)** — Average Duration 🔒 readonly
  > Average duration of the survey (in hours)
- `success_count` **(integer)** — Success 🔒 readonly
- `success_ratio` **(integer)** — Success Ratio (%) 🔒 readonly
- `scoring_max_obtainable` **(float)** — Maximum obtainable score 🔒 readonly
- `session_available` **(boolean)** — Live session available 🔒 readonly
- `session_link` **(char)** — Session Link 🔒 readonly
- `session_answer_count` **(integer)** — Answers Count 🔒 readonly
- `session_question_answer_count` **(integer)** — Question Answers Count 🔒 readonly
- `session_show_leaderboard` **(boolean)** — Show Session Leaderboard 🔒 readonly
  > Whether or not we want to show the attendees leaderboard for this survey.
- `has_conditional_questions` **(boolean)** — Contains conditional questions 🔒 readonly
- `lead_count` **(integer)** — Leads 🔒 readonly
  > Number of leads created by this survey
