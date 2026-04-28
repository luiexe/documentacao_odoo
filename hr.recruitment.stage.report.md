# Recruitment Stage Analysis — `hr.recruitment.stage.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Applicant Name 🔒 readonly
- `days_in_stage` **(float)** — Average Days in Stage 🔒 readonly
- `state` **(selection)** — State 🔒 readonly
  > Opções: `is_hired` (Hired), `in_progress` (In Progress), `refused` (Refused), `archived` (Archived)
- `date_begin` **(date)** — Start Date 🔒 readonly
- `date_end` **(date)** — End Date 🔒 readonly

## Relacionamentos

- `applicant_id` **(many2one)** — Applicant 🔒 readonly → `hr.applicant`
- `stage_id` **(many2one)** — Stage 🔒 readonly → `hr.recruitment.stage`
- `job_id` **(many2one)** — Job 🔒 readonly → `hr.job`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
