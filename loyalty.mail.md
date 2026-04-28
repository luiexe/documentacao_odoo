# Loyalty Communication — `loyalty.mail`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `program_id` **(many2one)** — Program ⚠️ obrigatório → `loyalty.program`
- `trigger` **(selection)** — When ⚠️ obrigatório
  > Opções: `create` (At Creation), `points_reach` (When Reaching)
- `mail_template_id` **(many2one)** — Email Template ⚠️ obrigatório → `mail.template`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `points` **(float)** — Points
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
