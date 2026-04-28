# Salary Structure Type — `hr.payroll.structure.type`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Salary Structure Type
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `default_resource_calendar_id` **(many2one)** — Working Hours → `resource.calendar`
- `country_id` **(many2one)** — Country → `res.country`

## Campos Calculados (readonly)

- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
