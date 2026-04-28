# Cleaning Record — `data_cleaning.record`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `rule_ids` **(many2many)** — Rule ⚠️ obrigatório → `data_cleaning.rule`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `res_id` **(integer)** — Record ID
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `field_id` **(many2one)** — Field → `ir.model.fields`
- `cleaning_model_id` **(many2one)** — Cleaning Model → `data_cleaning.model`
- `res_model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
- `country_id` **(many2one)** — Country 🔒 readonly → `res.country`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `name` **(char)** — Record Name 🔒 readonly
- `field_name` **(char)** — Field Name 🔒 readonly
- `action` **(char)** — Actions 🔒 readonly
- `current_value` **(char)** — Current 🔒 readonly
- `suggested_value` **(char)** — Suggested Value 🔒 readonly
- `suggested_value_display` **(char)** — Suggested 🔒 readonly
