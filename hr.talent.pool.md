# Talent Pool — `hr.talent.pool`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Title ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `description` **(html)** — Talent Pool Description
- `color` **(integer)** — Color
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `pool_manager` **(many2one)** — Pool Manager → `res.users`
- `talent_ids` **(many2many)** — Talent → `hr.applicant`
- `categ_ids` **(many2many)** — Tags → `hr.applicant.category`

## Campos Calculados (readonly)

- `no_of_talents` **(integer)** — # Talents 🔒 readonly
  > The number of talents in this talent pool.
