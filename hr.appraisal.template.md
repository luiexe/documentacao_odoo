# Employee Appraisal Template — `hr.appraisal.template`

**Ordenação padrão:** `sequence, description, id`

---

## Campos Obrigatórios

- `description` **(char)** — Short Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `appraisal_employee_feedback_template` **(html)** — Employee Feedback
- `appraisal_manager_feedback_template` **(html)** — Manager Feedback
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `department_ids` **(many2many)** — Departments → `hr.department`
- `survey_template_ids` **(many2many)** — 360 Feedback Survey → `survey.survey`
  > The survey templates available to choose from for the appraisals that use this template.
