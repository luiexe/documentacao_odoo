# Account — `account.account`

**Ordenação padrão:** `code, placeholder_code`

---

## Campos Obrigatórios

- `name` **(char)** — Account Name ⚠️ obrigatório
- `account_type` **(selection)** — Type ⚠️ obrigatório
  > Account Type is used for information purpose, to generate country-specific legal reports, and set the rules to close a fiscal year and generate opening entries.
  > Opções: `asset_receivable` (Receivable), `asset_cash` (Bank and Cash), `asset_current` (Current Assets), `asset_non_current` (Non-current Assets), `asset_prepayments` (Prepayments), `asset_fixed` (Fixed Assets), `liability_payable` (Payable), `liability_credit_card` (Credit Card), `liability_current` (Current Liabilities), `liability_non_current` (Non-current Liabilities), `equity` (Equity), `equity_unaffected` (Current Year Earnings), `income` (Income), `income_other` (Other Income), `expense` (Expenses), `expense_other` (Other Expenses), `expense_depreciation` (Depreciation), `expense_direct_cost` (Cost of Revenue), `off_balance` (Off-Balance Sheet)
- `company_ids` **(many2many)** — Companies ⚠️ obrigatório → `res.company`
- `create_asset` **(selection)** — Create Asset ⚠️ obrigatório
  > Opções: `no` (No), `draft` (Create in draft), `validate` (Create and validate)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
- `code` **(char)** — Code
- `code_store` **(char)** — Code Store
- `active` **(boolean)** — Active
- `reconcile` **(boolean)** — Allow Reconciliation
  > Check this box if this account allows invoices & payments matching of journal items.
- `note` **(text)** — Internal Notes
- `opening_debit` **(monetary)** — Opening Debit
- `opening_credit` **(monetary)** — Opening Credit
- `opening_balance` **(monetary)** — Opening Balance
- `non_trade` **(boolean)** — Non Trade
  > If set, this account will belong to Non Trade Receivable/Payable in reports and filters. If not, this account will belong to Trade Receivable/Payable in reports and filters.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `multiple_assets_per_line` **(boolean)** — Multiple Assets per Line
  > Multiple asset items will be generated depending on the bill line quantity instead of 1 global asset.

## Relacionamentos

- `currency_id` **(many2one)** — Account Currency → `res.currency`
  > Forces all journal items in this account to have a specific currency (i.e. bank journals). If no currency is set, entries can use any currency.
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `tax_ids` **(many2many)** — Default Taxes → `account.tax`
- `code_mapping_ids` **(one2many)** — Code Mapping → `account.code.mapping`
- `tag_ids` **(many2many)** — Tags → `account.account.tag`
  > Optional tags you may want to assign for custom reporting
- `group_id` **(many2one)** — Group 🔒 readonly → `account.group`
  > Account prefixes can determine account groups.
- `root_id` **(many2one)** — Root 🔒 readonly → `account.root`
- `account_stock_variation_id` **(many2one)** — Variation Account → `account.account`
  > At closing, register the inventory variation of the period into a specific account
- `account_stock_expense_id` **(many2one)** — Expense Account → `account.account`
  > Counterpart used at closing for accounting adjustments to inventory valuation.
- `exclude_provision_currency_ids` **(many2many)** — Exclude Provision Currency → `res.currency`
  > Whether or not we have to make provisions for the selected foreign currencies.
- `budget_item_ids` **(one2many)** — Budget Item → `account.report.budget.item`
- `account_status` **(one2many)** — Account Status → `account.audit.account.status`
- `fiscal_category_id` **(many2one)** — Fiscal Category → `account.fiscal.category`
- `rate_ids` **(one2many)** — Rate → `account.account.fiscal.rate`
- `asset_model_ids` **(many2many)** — Asset Model → `account.asset`
  > An asset wil be created for each asset model when this account is used on a vendor bill or a refund

## Campos Calculados (readonly)

- `company_fiscal_country_code` **(char)** — Company Fiscal Country Code 🔒 readonly
- `placeholder_code` **(char)** — Display code 🔒 readonly
- `used` **(boolean)** — Used 🔒 readonly
- `include_initial_balance` **(boolean)** — Bring Accounts Balance Forward 🔒 readonly
  > Used in reports to know if we should consider journal items from the beginning of time instead of from the fiscal year only. Account types that should be reset to zero at each new fiscal year (like expenses, revenue..) should not have this option set.
- `internal_group` **(selection)** — Internal Group 🔒 readonly
  > Opções: `equity` (Equity), `asset` (Asset), `liability` (Liability), `income` (Income), `expense` (Expense), `off` (Off Balance)
- `current_balance` **(float)** — Current Balance 🔒 readonly
- `related_taxes_amount` **(integer)** — Related Taxes Amount 🔒 readonly
- `last_message` **(char)** — Last Message 🔒 readonly
- `current_rate` **(float)** — Current Rate 🔒 readonly
- `can_create_asset` **(boolean)** — Can Create Asset 🔒 readonly

## Campos de Auditoria

- `audit_debit` **(monetary)** — Debit 🔒 readonly
- `audit_credit` **(monetary)** — Credit 🔒 readonly
- `audit_balance` **(monetary)** — Balance 🔒 readonly
- `audit_previous_balance` **(monetary)** — Balance N-1 🔒 readonly
- `audit_var_n_1` **(monetary)** — Var N-1 🔒 readonly
- `audit_var_percentage` **(float)** — Var % 🔒 readonly
- `audit_status` **(selection)** — Status
  > Opções: `todo` (To Review), `reviewed` (Reviewed), `supervised` (Supervised), `anomaly` (Anomaly)
