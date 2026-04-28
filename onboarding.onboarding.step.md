# Onboarding Step — `onboarding.onboarding.step`

**Ordenação padrão:** `sequence asc, id asc`

---

## Campos Obrigatórios

- `button_text` **(char)** — Button text ⚠️ obrigatório
  > Text on the panel's button to start this step

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `title` **(char)** — Title
- `description` **(char)** — Description
- `done_icon` **(char)** — Font Awesome Icon when completed
- `done_text` **(char)** — Text to show when step is completed
- `step_image` **(binary)** — Step Image
- `step_image_filename` **(char)** — Step Image Filename
- `step_image_alt` **(char)** — Alt Text for the Step Image
  > Show when impossible to load the image
- `panel_step_open_action_name` **(char)** — Opening action
  > Name of the onboarding step model action to execute when opening the step, e.g. action_open_onboarding_1_step_1
- `is_per_company` **(boolean)** — Is per company
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `onboarding_ids` **(many2many)** — Onboardings → `onboarding.onboarding`
- `current_progress_step_id` **(many2one)** — Step Progress 🔒 readonly → `onboarding.progress.step`
  > Onboarding Progress Step for the current context (company).
- `progress_ids` **(one2many)** — Onboarding Progress Step Records 🔒 readonly → `onboarding.progress.step`
  > All related Onboarding Progress Step Records (across companies)

## Campos Calculados (readonly)

- `current_step_state` **(selection)** — Completion State 🔒 readonly
  > Opções: `not_done` (Not done), `just_done` (Just done), `done` (Done)
