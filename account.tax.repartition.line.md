# Tax Repartition Line — `account.tax.repartition.line`

**Ordenação padrão:** `document_type, repartition_type, sequence, id`

---

## Campos Obrigatórios

- `factor_percent` **(float)** — % ⚠️ obrigatório
  > Factor to apply on the account move lines generated from this distribution line, in percents
- `repartition_type` **(selection)** — Based On ⚠️ obrigatório
  > Base on which the factor will be applied.
  > Opções: `base` (Base), `tax` (of tax)
- `document_type` **(selection)** — Related to ⚠️ obrigatório
  > Opções: `invoice` (Invoice), `refund` (Refund)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > The order in which distribution lines are displayed and matched. For refunds to work properly, invoice distribution lines should be arranged in the same order as the credit note distribution lines they correspond to.
- `use_in_tax_closing` **(boolean)** — Tax Closing Entry
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_id` **(many2one)** — Account → `account.account`
  > Account on which to post the tax amount
- `tag_ids` **(many2many)** — Tax Grids → `account.account.tag`
- `tax_id` **(many2one)** — Tax → `account.tax`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
  > The company this distribution line belongs to.

## Campos Calculados (readonly)

- `factor` **(float)** — Factor Ratio 🔒 readonly
  > Factor to apply on the account move lines generated from this distribution line
- `tag_ids_domain` **(binary)** — tag domain 🔒 readonly
  > Dynamic domain used for the tag that can be set on tax
