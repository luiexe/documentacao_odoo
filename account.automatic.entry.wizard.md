# Create Automatic Entries — `account.automatic.entry.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `action` **(selection)** — Action ⚠️ obrigatório
  > Opções: `change_period` (Change Period), `change_account` (Change Account)
- `date` **(date)** — Date ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`
  > Journal where to create the entry.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `percentage` **(float)** — Percentage
  > Percentage of each line to execute the action on.
- `total_amount` **(monetary)** — Total Amount
  > Total amount impacted by the automatic entry.
- `account_type` **(selection)** — Account Type 🔒 readonly
  > Opções: `income` (Revenue), `expense` (Expense)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `move_line_ids` **(many2many)** — Move Line → `account.move.line`
- `company_currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `expense_accrual_account` **(many2one)** — Expense Accrual Account → `account.account`
- `revenue_accrual_account` **(many2one)** — Revenue Accrual Account → `account.account`
- `destination_account_id` **(many2one)** — To → `account.account`
  > Account to transfer to.

## Campos Calculados (readonly)

- `move_data` **(text)** — Move Data 🔒 readonly
- `preview_move_data` **(text)** — Preview Move Data 🔒 readonly
- `lock_date_message` **(char)** — Lock Date Message 🔒 readonly
- `display_currency_helper` **(boolean)** — Currency Conversion Helper 🔒 readonly
