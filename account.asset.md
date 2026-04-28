# Asset/Revenue Recognition — `account.asset`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Asset Name ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `prorata_computation_type` **(selection)** — Computation ⚠️ obrigatório
  > Opções: `none` (No Prorata), `constant_periods` (Constant Periods), `daily_computation` (Based on days per period)
- `prorata_date` **(date)** — Prorata Date ⚠️ obrigatório
  > Starting date of the period used in the prorata calculation of the first depreciation

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `state` **(selection)** — Status 🔒 readonly
  > When an asset is created, the status is 'Draft'. If the asset is confirmed, the status goes in 'Running' and the depreciation lines can be posted in the accounting. The 'On Hold' status can be set manually when you want to pause the depreciation of an asset for some time. You can manually close an asset when the depreciation is over. By cancelling an asset, all depreciation entries will be reversed
  > Opções: `model` (Model), `draft` (Draft), `open` (Running), `paused` (On Hold), `close` (Closed), `cancelled` (Cancelled)
- `active` **(boolean)** — Active
- `method` **(selection)** — Method
  > Choose the method to use to compute the amount of depreciation lines.   * Straight Line: Calculated on basis of: Gross Value / Duration   * Declining: Calculated on basis of: Residual Value * Declining Factor   * Declining then Straight Line: Like Declining but with a minimum depreciation value equal to the straight line value.
  > Opções: `linear` (Straight Line), `degressive` (Declining), `degressive_then_linear` (Declining then Straight Line)
- `method_number` **(integer)** — Duration
  > The number of depreciations needed to depreciate your asset
- `method_period` **(selection)** — Number of Months in a Period
  > The amount of time between two depreciations
  > Opções: `1` (Months), `12` (Years)
- `method_progress_factor` **(float)** — Declining Factor
- `original_value` **(monetary)** — Original Value
- `book_value` **(monetary)** — Book Value 🔒 readonly
  > Sum of the depreciable value, the salvage value and the book value of all value increase items
- `salvage_value` **(monetary)** — Not Depreciable Value
  > It is the amount you plan to have that you cannot depreciate.
- `salvage_value_pct` **(float)** — Not Depreciable Value Percent
  > It is the amount you plan to have that you cannot depreciate.
- `non_deductible_tax_value` **(monetary)** — Non Deductible Tax Value 🔒 readonly
- `asset_properties_definition` **(properties_definition)** — Model Properties
- `asset_properties` **(properties)** — Properties
- `acquisition_date` **(date)** — Acquisition Date
- `disposal_date` **(date)** — Disposal Date
- `already_depreciated_amount_import` **(monetary)** — Already Depreciated Amount Import
  > In case of an import from another software, you might need to use this field to have the right depreciation table report. This is the value that was already depreciated with entries not computed from this model
- `asset_paused_days` **(float)** — Asset Paused Days
- `net_gain_on_sale` **(monetary)** — Net gain on sale
  > Net value of gain or loss on sale of an asset
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `account_asset_id` **(many2one)** — Fixed Asset Account → `account.account`
  > Account used to record the purchase of the asset at its original price.
- `asset_group_id` **(many2one)** — Asset Group → `account.asset.group`
- `account_depreciation_id` **(many2one)** — Depreciation Account → `account.account`
  > Account used in the depreciation entries, to decrease the asset value.
- `account_depreciation_expense_id` **(many2one)** — Expense Account → `account.account`
  > Account used in the periodical entries, to record a part of the asset as expense.
- `journal_id` **(many2one)** — Journal → `account.journal`
- `depreciation_move_ids` **(one2many)** — Depreciation Lines → `account.move`
- `original_move_line_ids` **(many2many)** — Journal Items → `account.move.line`
- `model_id` **(many2one)** — Model → `account.asset`
- `parent_id` **(many2one)** — Parent → `account.asset`
  > An asset has a parent when it is the result of gaining value
- `children_ids` **(one2many)** — Children → `account.asset`
  > The children are the gains in value of this asset
- `linked_assets_ids` **(one2many)** — Linked Assets 🔒 readonly → `account.asset`
- `linked_loans_ids` **(one2many)** — Related Loans 🔒 readonly → `account.loan`

## Campos Calculados (readonly)

- `depreciation_entries_count` **(integer)** — # Posted Depreciation Entries 🔒 readonly
- `gross_increase_count` **(integer)** — # Gross Increases 🔒 readonly
  > Number of assets made to increase the value of the asset
- `total_depreciation_entries_count` **(integer)** — # Depreciation Entries 🔒 readonly
  > Number of depreciation entries (posted or not)
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `paused_prorata_date` **(date)** — Paused Prorata Date 🔒 readonly
- `value_residual` **(monetary)** — Depreciable Value 🔒 readonly
- `total_depreciable_value` **(monetary)** — Total Depreciable Value 🔒 readonly
- `gross_increase_value` **(monetary)** — Gross Increase Value 🔒 readonly
- `related_purchase_value` **(monetary)** — Related Purchase Value 🔒 readonly
- `account_type` **(selection)** — Type of the account 🔒 readonly
  > Account Type is used for information purpose, to generate country-specific legal reports, and set the rules to close a fiscal year and generate opening entries.
  > Opções: `asset_receivable` (Receivable), `asset_cash` (Bank and Cash), `asset_current` (Current Assets), `asset_non_current` (Non-current Assets), `asset_prepayments` (Prepayments), `asset_fixed` (Fixed Assets), `liability_payable` (Payable), `liability_credit_card` (Credit Card), `liability_current` (Current Liabilities), `liability_non_current` (Non-current Liabilities), `equity` (Equity), `equity_unaffected` (Current Year Earnings), `income` (Income), `income_other` (Other Income), `expense` (Expenses), `expense_other` (Other Expenses), `expense_depreciation` (Depreciation), `expense_direct_cost` (Cost of Revenue), `off_balance` (Off-Balance Sheet)
- `display_account_asset_id` **(boolean)** — Display Account Asset 🔒 readonly
- `asset_lifetime_days` **(float)** — Asset Lifetime Days 🔒 readonly
- `count_linked_asset` **(integer)** — Count Linked Asset 🔒 readonly
- `warning_count_assets` **(boolean)** — Warning Count Assets 🔒 readonly
- `count_linked_loans` **(integer)** — Count Linked Loans 🔒 readonly
