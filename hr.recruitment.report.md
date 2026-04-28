# Recruitment Analysis Report — `hr.recruitment.report`

**Ordenação padrão:** `create_date desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `count` **(integer)** — Applications 🔒 readonly
- `refused` **(integer)** — Refused 🔒 readonly
- `hired` **(integer)** — Hired 🔒 readonly
- `hiring_ratio` **(integer)** — Hired Ratio 🔒 readonly
- `meetings_amount` **(integer)** — Meetings 🔒 readonly
- `in_progress` **(integer)** — In Progress 🔒 readonly
- `state` **(selection)** — State 🔒 readonly
  > Opções: `in_progress` (In Progress), `is_hired` (Hired), `refused` (Refused)
- `create_date` **(date)** — Application Date 🔒 readonly
- `date_closed` **(date)** — End Date 🔒 readonly
- `name` **(char)** — Applicant Name 🔒 readonly
- `process_duration` **(integer)** — Process Duration 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — Recruiter 🔒 readonly → `res.users`
- `stage_id` **(many2one)** — Stage 🔒 readonly → `hr.recruitment.stage`
- `job_id` **(many2one)** — Job 🔒 readonly → `hr.job`
- `medium_id` **(many2one)** — Medium 🔒 readonly → `utm.medium`
- `source_id` **(many2one)** — Source 🔒 readonly → `utm.source`
- `refuse_reason_id` **(many2one)** — Refuse Reason 🔒 readonly → `hr.applicant.refuse.reason`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
