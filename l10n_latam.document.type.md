# Latam Document Type — `l10n_latam.document.type`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `sequence` **(integer)** — Sequence ⚠️ obrigatório
  > To set in which order show the documents type taking into account the most commonly used first
- `country_id` **(many2one)** — Country ⚠️ obrigatório → `res.country`
  > Country in which this type of document is valid
- `name` **(char)** — Name ⚠️ obrigatório
  > The document name

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `doc_code_prefix` **(char)** — Document Code Prefix
  > Prefix for Documents Codes on Invoices and Account Moves. For eg. 'FA ' will build 'FA 0001-0000001' Document Number
- `code` **(char)** — Code
  > Code used by different localizations
- `report_name` **(char)** — Name on Reports
  > Name that will be printed in reports, for example "CREDIT NOTE"
- `internal_type` **(selection)** — Internal Type
  > Analog to odoo account.move.move_type but with more options allowing to identify the kind of document we are working with. (not only related to account.move, could be for documents of other models like stock.picking)
  > Opções: `invoice` (Invoices), `debit_note` (Debit Notes), `credit_note` (Credit Notes), `all` (All Documents)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
