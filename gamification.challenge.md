# Gamification Challenge — `gamification.challenge`

**Ordenação padrão:** `end_date, start_date, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Challenge Name ⚠️ obrigatório
- `state` **(selection)** — State ⚠️ obrigatório
  > Opções: `draft` (Draft), `inprogress` (In Progress), `done` (Done)
- `period` **(selection)** — Periodicity ⚠️ obrigatório
  > Period of automatic goal assignment. If none is selected, should be launched manually.
  > Opções: `once` (Non recurring), `daily` (Daily), `weekly` (Weekly), `monthly` (Monthly), `yearly` (Yearly)
- `line_ids` **(one2many)** — Lines ⚠️ obrigatório → `gamification.challenge.line`
  > List of goals that will be set
- `visibility_mode` **(selection)** — Display Mode ⚠️ obrigatório
  > Opções: `personal` (Individual Goals), `ranking` (Leader Board (Group Ranking))
- `report_message_frequency` **(selection)** — Report Frequency ⚠️ obrigatório
  > Opções: `never` (Never), `onchange` (On change), `daily` (Daily), `weekly` (Weekly), `monthly` (Monthly), `yearly` (Yearly)
- `report_template_id` **(many2one)** — Report Template ⚠️ obrigatório → `mail.template`
- `challenge_category` **(selection)** — Appears in ⚠️ obrigatório
  > Define the visibility of the challenge through menus
  > Opções: `hr` (Human Resources / Engagement), `other` (Settings / Gamification Tools), `certification` (Certifications), `slides` (Website / Slides)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
- `user_domain` **(char)** — User domain
- `start_date` **(date)** — Start Date
  > The day a new challenge will be automatically started. If no periodicity is set, will use this date as the goal start date.
- `end_date` **(date)** — End Date
  > The day a new challenge will be automatically closed. If no periodicity is set, will use this date as the goal end date.
- `reward_failure` **(boolean)** — Reward Bests if not Succeeded?
- `reward_realtime` **(boolean)** — Reward as soon as every goal is reached
  > With this option enabled, a user can receive a badge only once. The top 3 badges are still rewarded only at the end of the challenge.
- `remind_update_delay` **(integer)** — Non-updated manual goals will be reminded after
  > Never reminded if no value or zero is specified.
- `last_report_date` **(date)** — Last Report Date
- `next_report_date` **(date)** — Next Report Date 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `manager_id` **(many2one)** — Responsible → `res.users`
- `user_ids` **(many2many)** — Participants → `res.users`
- `invited_user_ids` **(many2many)** — Suggest to users → `res.users`
- `reward_id` **(many2one)** — For Every Succeeding User → `gamification.badge`
- `reward_first_id` **(many2one)** — For 1st user → `gamification.badge`
- `reward_second_id` **(many2one)** — For 2nd user → `gamification.badge`
- `reward_third_id` **(many2one)** — For 3rd user → `gamification.badge`
- `report_message_group_id` **(many2one)** — Send a copy to → `discuss.channel`
  > Group that will receive a copy of the report in addition to the user

## Campos Calculados (readonly)

- `user_count` **(integer)** — # Users 🔒 readonly
