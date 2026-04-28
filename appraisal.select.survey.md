# Select survey type for an appraisal to show its results — `appraisal.select.survey`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `survey_input_ids` **(many2many)** — Survey Inputs ⚠️ obrigatório → `survey.user_input`
- `survey_template_id` **(many2one)** — Survey ⚠️ obrigatório → `survey.survey`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `allowed_survey_template_ids` **(many2many)** — Allowed Survey Template 🔒 readonly → `survey.survey`
