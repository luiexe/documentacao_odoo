# Loan — `account.loan`

**Ordenação padrão:** `date`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `state` **(selection)** — Status ⚠️ obrigatório
  > Opções: `draft` (Draft), `running` (Running), `closed` (Closed), `cancelled` (Cancelled)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `date` **(date)** — Loan Date
- `amount_borrowed` **(monetary)** — Amount Borrowed
- `interest` **(monetary)** — Interest
- `duration` **(integer)** — Duration
- `skip_until_date` **(date)** — Skip until
  > Upon confirmation of the loan, Odoo will ignore the loan lines that are up to this date (included) and not create entries for them. This is useful if you have already manually created entries prior to the creation of this loan.
- `loan_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `long_term_account_id` **(many2one)** — Long Term Account → `account.account`
- `short_term_account_id` **(many2one)** — Short Term Account → `account.account`
- `expense_account_id` **(many2one)** — Expense Account → `account.account`
- `journal_id` **(many2one)** — Journal → `account.journal`
- `asset_group_id` **(many2one)** — Asset Group → `account.asset.group`
- `line_ids` **(one2many)** — Loan Lines → `account.loan.line`
- `linked_assets_ids` **(one2many)** — Linked Assets 🔒 readonly → `account.asset`

## Campos Calculados (readonly)

- `start_date` **(date)** — Start Date 🔒 readonly
- `end_date` **(date)** — End Date 🔒 readonly
- `is_wrong_date` **(boolean)** — Is Wrong Date 🔒 readonly
- `amount_borrowed_difference` **(monetary)** — Amount Borrowed Difference 🔒 readonly
- `interest_difference` **(monetary)** — Interest Difference 🔒 readonly
- `duration_difference` **(integer)** — Duration Difference 🔒 readonly
- `outstanding_balance` **(monetary)** — Outstanding Balance 🔒 readonly
- `nb_posted_entries` **(integer)** — Nb Posted Entries 🔒 readonly
- `count_linked_assets` **(integer)** — Count Linked Assets 🔒 readonly
