# Add applicants to talent pool — `talent.pool.add.applicants`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `applicant_ids` **(many2many)** — Applicants ⚠️ obrigatório → `hr.applicant`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `talent_pool_ids` **(many2many)** — Talent Pool → `hr.talent.pool`
- `categ_ids` **(many2many)** — Tags → `hr.applicant.category`
