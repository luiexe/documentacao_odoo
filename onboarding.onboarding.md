# Onboarding — `onboarding.onboarding`

**Ordenação padrão:** `sequence asc, id desc`

---

## Campos Obrigatórios

- `route_name` **(char)** — One word name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name of the onboarding
- `text_completed` **(char)** — Message at completion
  > Text shown on onboarding when completed
- `panel_close_action_name` **(char)** — Closing action
  > Name of the onboarding model action to execute when closing the panel.
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `step_ids` **(many2many)** — Onboarding steps → `onboarding.onboarding.step`
- `current_progress_id` **(many2one)** — Onboarding Progress 🔒 readonly → `onboarding.progress`
  > Onboarding Progress for the current context (company).
- `progress_ids` **(one2many)** — Onboarding Progress Records 🔒 readonly → `onboarding.progress`
  > All Onboarding Progress Records (across companies).

## Campos Calculados (readonly)

- `is_per_company` **(boolean)** — Should be done per company? 🔒 readonly
- `current_onboarding_state` **(selection)** — Completion State 🔒 readonly
  > Opções: `not_done` (Not done), `just_done` (Just done), `done` (Done)
- `is_onboarding_closed` **(boolean)** — Was panel closed? 🔒 readonly
