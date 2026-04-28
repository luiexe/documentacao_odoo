# Gamification Goal — `gamification.goal`

**Ordenação padrão:** `start_date desc, end_date desc, definition_id, id`

---

## Campos Obrigatórios

- `definition_id` **(many2one)** — Goal Definition ⚠️ obrigatório → `gamification.goal.definition`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `target_goal` **(float)** — To Reach ⚠️ obrigatório
- `current` **(float)** — Current Value ⚠️ obrigatório
- `state` **(selection)** — State ⚠️ obrigatório
  > Opções: `draft` (Draft), `inprogress` (In progress), `reached` (Reached), `failed` (Failed), `canceled` (Cancelled)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `start_date` **(date)** — Start Date
- `end_date` **(date)** — End Date
- `to_update` **(boolean)** — To update
- `closed` **(boolean)** — Closed goal
- `computation_mode` **(selection)** — Computation Mode
  > Define how the goals will be computed. The result of the operation will be stored in the field 'Current'.
  > Opções: `manually` (Recorded manually), `count` (Automatic: number of records), `sum` (Automatic: sum on a field), `python` (Automatic: execute a specific Python code)
- `remind_update_delay` **(integer)** — Remind delay
  > The number of days after which the user assigned to a manual goal will be reminded. Never reminded if no value is specified.
- `last_update` **(date)** — Last Update
  > In case of manual goal, reminders are sent if the goal as not been updated for a while (defined in challenge). Ignored in case of non-manual goal or goal not linked to a challenge.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_partner_id` **(many2one)** — Related Partner 🔒 readonly → `res.partner`
  > Partner-related data of the user
- `line_id` **(many2one)** — Challenge Line → `gamification.challenge.line`
- `challenge_id` **(many2one)** — Challenge 🔒 readonly → `gamification.challenge`
  > Challenge that generated the goal, assign challenge to users to generate goals with a value in this field.

## Campos Calculados (readonly)

- `completeness` **(float)** — Completeness 🔒 readonly
- `color` **(integer)** — Color Index 🔒 readonly
- `definition_description` **(text)** — Definition Description 🔒 readonly
- `definition_condition` **(selection)** — Definition Condition 🔒 readonly
  > A goal is considered as completed when the current value is compared to the value to reach
  > Opções: `higher` (The higher the better), `lower` (The lower the better)
- `definition_suffix` **(char)** — Suffix 🔒 readonly
  > The currency and suffix field
- `definition_display` **(selection)** — Display Mode 🔒 readonly
  > Opções: `progress` (Progressive (using numerical values)), `boolean` (Exclusive (done or not-done))
