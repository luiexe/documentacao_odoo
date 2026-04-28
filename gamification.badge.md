# Gamification Badge — `gamification.badge`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Badge ⚠️ obrigatório
- `rule_auth` **(selection)** — Allowance to Grant ⚠️ obrigatório
  > Who can grant this badge
  > Opções: `everyone` (Everyone), `users` (A selected list of users), `having` (People having some badges), `nobody` (No one, assigned through challenges)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `image_1920` **(binary)** — Image
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `active` **(boolean)** — Active
- `description` **(html)** — Description
- `level` **(selection)** — Forum Badge Level
  > Opções: `bronze` (Bronze), `silver` (Silver), `gold` (Gold)
- `rule_max` **(boolean)** — Monthly Limited Sending
  > Check to set a monthly limit per person of sending this badge
- `rule_max_number` **(integer)** — Limitation Number
  > The maximum number of time this badge can be sent per month per person.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `rule_auth_user_ids` **(many2many)** — Authorized Users → `res.users`
  > Only these people can give this badge
- `rule_auth_badge_ids` **(many2many)** — Required Badges → `gamification.badge`
  > Only the people having these badges can give this badge
- `challenge_ids` **(one2many)** — Reward of Challenges → `gamification.challenge`
- `goal_definition_ids` **(many2many)** — Rewarded by → `gamification.goal.definition`
  > The users that have succeeded these goals will receive automatically the badge.
- `owner_ids` **(one2many)** — Owners → `gamification.badge.user`
  > The list of instances of this badge granted to users
- `unique_owner_ids` **(many2many)** — Unique Owners 🔒 readonly → `res.users`
  > The list of unique users having received this badge.
- `survey_ids` **(one2many)** — Survey Ids → `survey.survey`
- `survey_id` **(many2one)** — Survey 🔒 readonly → `survey.survey`

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `granted_count` **(integer)** — Total 🔒 readonly
  > The number of time this badge has been received.
- `granted_users_count` **(integer)** — Number of users 🔒 readonly
  > The number of time this badge has been received by unique users.
- `stat_this_month` **(integer)** — Monthly total 🔒 readonly
  > The number of time this badge has been received this month.
- `stat_my` **(integer)** — My Total 🔒 readonly
  > The number of time the current user has received this badge.
- `stat_my_this_month` **(integer)** — My Monthly Total 🔒 readonly
  > The number of time the current user has received this badge this month.
- `stat_my_monthly_sending` **(integer)** — My Monthly Sending Total 🔒 readonly
  > The number of time the current user has sent this badge this month.
- `remaining_sending` **(integer)** — Remaining Sending Allowed 🔒 readonly
  > If a maximum is set
- `granted_employees_count` **(integer)** — Granted Employees Count 🔒 readonly
