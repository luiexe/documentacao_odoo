# Onboarding Progress Tracker — `onboarding.progress`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `onboarding_id` **(many2one)** — Related onboarding tracked ⚠️ obrigatório → `onboarding.onboarding`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `onboarding_state` **(selection)** — Onboarding progress 🔒 readonly
  > Opções: `not_done` (Not done), `just_done` (Just done), `done` (Done)
- `is_onboarding_closed` **(boolean)** — Was panel closed?
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `progress_step_ids` **(many2many)** — Progress Steps Trackers → `onboarding.progress.step`
