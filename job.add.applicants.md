# Add applicants to a job — `job.add.applicants`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `applicant_ids` **(many2many)** — Applications ⚠️ obrigatório → `hr.applicant`
- `job_ids` **(many2many)** — Job Positions ⚠️ obrigatório → `hr.job`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
