# Accounting Report External Value — `account.report.external.value`

**Ordenação padrão:** `date, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `date` **(date)** — Date ⚠️ obrigatório
- `target_report_expression_id` **(many2one)** — Target Expression ⚠️ obrigatório → `account.report.expression`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `value` **(float)** — Numeric Value
- `text_value` **(char)** — Text Value
- `carryover_origin_expression_label` **(char)** — Origin Expression Label
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `target_report_line_id` **(many2one)** — Target Line 🔒 readonly → `account.report.line`
- `report_country_id` **(many2one)** — Country 🔒 readonly → `res.country`
- `carryover_origin_report_line_id` **(many2one)** — Origin Line → `account.report.line`

## Campos Calculados (readonly)

- `target_report_expression_label` **(char)** — Target Expression Label 🔒 readonly
