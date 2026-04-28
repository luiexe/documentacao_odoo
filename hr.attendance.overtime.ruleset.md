# Overtime Ruleset — `hr.attendance.overtime.ruleset`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `rate_combination_mode` **(selection)** — Rate Combination Mode ⚠️ obrigatório
  > Controls how the rates from the different rules that apply are combined.   Max: use the highest rate. (e.g.: combined for 150% and 120 = 150%)   Sum: sum the *extra* pay (i.e. above 100%).     e.g.: combined rate for 150% & 120% = 100% (baseline) + (150-100)% + (120-100)% = 170% 
  > Opções: `max` (Maximum Rate), `sum` (Sum of all rates)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(html)** — Description
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `rule_ids` **(one2many)** — Rule → `hr.attendance.overtime.rule`
- `company_id` **(many2one)** — Company → `res.company`
- `country_id` **(many2one)** — Country → `res.country`

## Campos Calculados (readonly)

- `rules_count` **(integer)** — Rules Count 🔒 readonly
