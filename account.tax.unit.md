# Tax Unit — `account.tax.unit`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `country_id` **(many2one)** — Country ⚠️ obrigatório → `res.country`
  > The country in which this tax unit is used to group your companies' tax reports declaration.
- `vat` **(char)** — Tax ID ⚠️ obrigatório
  > The identifier to be used when submitting a report for this unit.
- `company_ids` **(many2many)** — Companies ⚠️ obrigatório → `res.company`
  > Members of this unit
- `main_company_id` **(many2one)** — Main Company ⚠️ obrigatório → `res.company`
  > Main company of this unit; the one actually reporting and paying the taxes.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `fpos_synced` **(boolean)** — Fiscal Positions Synchronised 🔒 readonly
  > Technical field indicating whether Fiscal Positions exist for all companies in the unit
