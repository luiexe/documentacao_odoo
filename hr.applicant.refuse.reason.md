# Refuse Reason of Applicant — `hr.applicant.refuse.reason`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Description ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Email Template → `mail.template`
