# Onboarding Progress Step Tracker — `onboarding.progress.step`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `step_id` **(many2one)** — Onboarding Step ⚠️ obrigatório → `onboarding.onboarding.step`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `step_state` **(selection)** — Onboarding Step Progress
  > Opções: `not_done` (Not done), `just_done` (Just done), `done` (Done)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `progress_ids` **(many2many)** — Related Onboarding Progress Tracker → `onboarding.progress`
- `company_id` **(many2one)** — Company → `res.company`
