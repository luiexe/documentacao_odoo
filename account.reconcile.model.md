# Preset to create journal entries during a invoices and payments matching — `account.reconcile.model`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `sequence` **(integer)** — Sequence ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `trigger` **(selection)** — Trigger ⚠️ obrigatório
  > Validate the statement line automatically (reconciliation based on your rule).
  > Opções: `manual` (Manual), `auto_reconcile` (Automated)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `can_be_proposed` **(boolean)** — Can Be Proposed 🔒 readonly
- `match_amount` **(selection)** — Amount
  > The reconciliation model will only be applied when the amount being lower than, greater than or between specified amount(s).
  > Opções: `lower` (Is lower than or equal to), `greater` (Is greater than or equal to), `between` (Is between)
- `match_amount_min` **(float)** — Amount Min Parameter
- `match_amount_max` **(float)** — Amount Max Parameter
- `match_label` **(selection)** — Label
  > The reconciliation model will only be applied when either the statement line label, the transaction details or the note matches the following:         * Contains: The statement line must contains this string (case insensitive).         * Not Contains: Negation of "Contains".         * Match Regex: Define your own regular expression.
  > Opções: `contains` (Contains), `not_contains` (Not Contains), `match_regex` (Match Regex)
- `match_label_param` **(char)** — Label Parameter
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `created_automatically` **(boolean)** — Created Automatically

## Relacionamentos

- `next_activity_type_id` **(many2one)** — Next Activity → `mail.activity.type`
- `mapped_partner_id` **(many2one)** — Mapped Partner 🔒 readonly → `res.partner`
- `match_journal_ids` **(many2many)** — Journals → `account.journal`
  > The reconciliation model will only be available from the selected journals.
- `match_partner_ids` **(many2many)** — Partners → `res.partner`
  > The reconciliation model will only be applied to the selected customers/vendors.
- `line_ids` **(one2many)** — Line → `account.reconcile.model.line`
