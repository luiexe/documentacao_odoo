# Account Tag — `account.account.tag`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Tag Name ⚠️ obrigatório
- `applicability` **(selection)** — Applicability ⚠️ obrigatório
  > Opções: `accounts` (Accounts), `taxes` (Taxes), `products` (Products)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color Index
- `active` **(boolean)** — Active
  > Set active to false to hide the Account Tag without removing it.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `country_id` **(many2one)** — Country → `res.country`
  > Country for which this tag is available, when applied on taxes.
- `report_expression_id` **(many2one)** — Report Expression 🔒 readonly → `account.report.expression`

## Campos Calculados (readonly)

- `balance_negate` **(boolean)** — Balance Negate 🔒 readonly
