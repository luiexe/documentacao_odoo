# Source of Applicants — `hr.recruitment.source`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `source_id` **(many2one)** — Source ⚠️ obrigatório → `utm.source`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `job_id` **(many2one)** — Job → `hr.job`
- `alias_id` **(many2one)** — Alias ID → `mail.alias`
- `medium_id` **(many2one)** — Medium → `utm.medium`
- `campaign_id` **(many2one)** — Campaign → `utm.campaign`

## Campos Calculados (readonly)

- `email` **(char)** — Email 🔒 readonly
- `has_domain` **(char)** — Has Domain 🔒 readonly
- `url` **(char)** — Tracker URL 🔒 readonly
