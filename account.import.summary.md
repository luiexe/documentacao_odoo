# Account import summary view — `account.import.summary`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `import_summary_name` **(char)** — Import Summary Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `import_summary_account_ids` **(many2many)** — Import Summary Account → `account.account`
- `import_summary_journal_ids` **(many2many)** — Import Summary Journal → `account.journal`
- `import_summary_move_ids` **(many2many)** — Import Summary Move → `account.move`
- `import_summary_partner_ids` **(many2many)** — Import Summary Partner → `res.partner`
- `import_summary_tax_ids` **(many2many)** — Import Summary Tax → `account.tax`

## Campos Calculados (readonly)

- `import_summary_len_account` **(integer)** — Import Summary Len Account 🔒 readonly
- `import_summary_len_journal` **(integer)** — Import Summary Len Journal 🔒 readonly
- `import_summary_len_move` **(integer)** — Import Summary Len Move 🔒 readonly
- `import_summary_len_partner` **(integer)** — Import Summary Len Partner 🔒 readonly
- `import_summary_len_tax` **(integer)** — Import Summary Len Tax 🔒 readonly
- `import_summary_have_data` **(boolean)** — Import Summary Have Data 🔒 readonly
