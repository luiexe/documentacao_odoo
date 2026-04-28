# Fiscal Position — `account.fiscal.position`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Fiscal Position ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
  > By unchecking the active field, you may hide a fiscal position without deleting it.
- `note` **(html)** — Notes
  > Legal mentions that have to be printed on the invoices.
- `auto_apply` **(boolean)** — Detect Automatically
  > Apply tax & account mappings on invoices automatically if the matching criterias (VAT/Country) are met.
- `vat_required` **(boolean)** — VAT required
  > Apply only if partner has a VAT number.
- `is_domestic` **(boolean)** — Is Domestic 🔒 readonly
- `zip_from` **(char)** — Zip Range From
- `zip_to` **(char)** — Zip Range To
- `foreign_vat` **(char)** — Foreign Tax ID
  > The tax ID of your company in the region mapped by this fiscal position.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `l10n_br_fp_type` **(selection)** — Interstate Fiscal Position Type
  > Opções: `internal` (Internal), `ss_nnm` (South/Southeast selling to North/Northeast/Midwest), `interstate` (Other interstate)
- `l10n_br_is_avatax` **(boolean)** — Use Avatax Brazil API

## Relacionamentos

- `account_ids` **(one2many)** — Account Mapping → `account.fiscal.position.account`
- `tax_ids` **(many2many)** — Taxes → `account.tax`
- `company_country_id` **(many2one)** — Company Country 🔒 readonly → `res.country`
  > The country to use the tax reports from for this company
- `country_id` **(many2one)** — Country → `res.country`
  > Apply only if delivery country matches.
- `country_group_id` **(many2one)** — Country Group → `res.country.group`
  > Apply only if delivery country matches the group.
- `state_ids` **(many2many)** — Federal States → `res.country.state`

## Campos Calculados (readonly)

- `account_map` **(binary)** — Account Map 🔒 readonly
- `tax_map` **(binary)** — Tax Map 🔒 readonly
- `fiscal_country_codes` **(char)** — Company Fiscal Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `states_count` **(integer)** — States Count 🔒 readonly
- `foreign_vat_header_mode` **(selection)** — Foreign Vat Header Mode 🔒 readonly
  > Opções: `templates_found` (Templates Found), `no_template` (No Template)
