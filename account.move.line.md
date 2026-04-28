# Journal Item — `account.move.line`

**Ordenação padrão:** `date desc, move_name desc, id`

---

## Campos Obrigatórios

- `move_id` **(many2one)** — Journal Entry ⚠️ obrigatório 🔒 readonly → `account.move`
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`
- `display_type` **(selection)** — Display Type ⚠️ obrigatório
  > Opções: `product` (Product), `cogs` (Cost of Goods Sold), `tax` (Tax), `discount` (Discount), `rounding` (Rounding), `payment_term` (Payment Term), `line_section` (Section), `line_subsection` (Subsection), `line_note` (Note), `epd` (Early Payment Discount), `non_deductible_product_total` (Non Deductible Products Total), `non_deductible_product` (Non Deductible Products), `non_deductible_tax` (Non Deductible Tax)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `move_name` **(char)** — Number 🔒 readonly
- `parent_state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Draft), `posted` (Posted), `cancel` (Cancelled)
- `date` **(date)** — Date 🔒 readonly
- `invoice_date` **(date)** — Invoice/Bill Date 🔒 readonly
- `ref` **(char)** — Reference 🔒 readonly
- `is_storno` **(boolean)** — Company Storno Accounting
  > Utility field to express whether the journal item is subject to storno accounting
- `sequence` **(integer)** — Sequence
- `name` **(char)** — Label
- `debit` **(monetary)** — Debit
- `credit` **(monetary)** — Credit
- `balance` **(monetary)** — Balance
- `amount_currency` **(monetary)** — Amount in Currency
  > The amount expressed in an optional other currency if it is a multi-currency entry.
- `is_imported` **(boolean)** — Is Imported
- `tax_base_amount` **(monetary)** — Base Amount 🔒 readonly
- `extra_tax_data` **(json)** — Extra Tax Data
- `amount_residual` **(monetary)** — Residual Amount 🔒 readonly
  > The residual amount on a journal item expressed in the company currency.
- `amount_residual_currency` **(monetary)** — Residual Amount in Currency 🔒 readonly
  > The residual amount on a journal item expressed in its currency (possibly not the company currency).
- `reconciled` **(boolean)** — Reconciled 🔒 readonly
- `matching_number` **(char)** — Matching #
  > Matching number for this line, 'P' if it is only partially reconcile, or the name of the full reconcile if it exists.
- `collapse_composition` **(boolean)** — Hide Composition
  > If checked, the lines below this section will not be displayed in reports and portal.
- `collapse_prices` **(boolean)** — Hide Prices
  > If checked, the prices of the lines below this section will not be displayed in reports and portal.
- `quantity` **(float)** — Quantity
  > The optional quantity expressed by this line, eg: number of product sold. The quantity is not a legal requirement but is very useful for some reports.
- `date_maturity` **(date)** — Due Date
  > This field is used for payable and receivable journal entries. You can put the limit date for the payment of this line.
- `price_unit` **(float)** — Unit Price
- `price_subtotal` **(monetary)** — Subtotal 🔒 readonly
- `price_total` **(monetary)** — Total 🔒 readonly
- `discount` **(float)** — Discount (%)
- `deductible_amount` **(float)** — Deductibility
- `discount_date` **(date)** — Discount Date 🔒 readonly
  > Last date at which the discounted amount must be paid in order for the Early Payment Discount to be granted
- `discount_amount_currency` **(monetary)** — Discount amount in Currency
- `discount_balance` **(monetary)** — Discount Balance
- `no_followup` **(boolean)** — No Follow-Up
  > Exclude this journal item from follow-up reports.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `deferred_start_date` **(date)** — Start Date
  > Date at which the deferred expense/revenue starts
- `deferred_end_date` **(date)** — End Date
  > Date at which the deferred expense/revenue ends
- `is_downpayment` **(boolean)** — Is Downpayment
- `exclude_bank_lines` **(boolean)** — Exclude Bank Lines 🔒 readonly
- `l10n_br_cbs_ibs_deduction` **(monetary)** — CBS/IBS Credit
  > Brazil: Deduction value to reduce the CBS/IBS taxable base in outbound invoices for certain operations.

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `journal_id` **(many2one)** — Journal 🔒 readonly → `account.journal`
- `journal_group_id` **(many2one)** — Ledger → `account.journal.group`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `account_id` **(many2one)** — Account → `account.account`
- `search_account_id` **(many2one)** — Search Account → `account.account`
- `partner_id` **(many2one)** — Partner → `res.partner`
- `reconcile_model_id` **(many2one)** — Reconciliation Model 🔒 readonly → `account.reconcile.model`
- `payment_id` **(many2one)** — Originator Payment 🔒 readonly → `account.payment`
  > The payment that created this entry
- `statement_line_id` **(many2one)** — Originator Statement Line 🔒 readonly → `account.bank.statement.line`
  > The statement line that created this entry
- `statement_id` **(many2one)** — Statement 🔒 readonly → `account.bank.statement`
  > The bank statement used for bank reconciliation
- `commercial_partner_country` **(many2one)** — Commercial Partner Country 🔒 readonly → `res.country`
- `tax_ids` **(many2many)** — Taxes → `account.tax`
- `group_tax_id` **(many2one)** — Originator Group of Taxes → `account.tax`
- `tax_line_id` **(many2one)** — Originator Tax 🔒 readonly → `account.tax`
  > Indicates that this journal item is a tax line
- `tax_group_id` **(many2one)** — Originator tax group 🔒 readonly → `account.tax.group`
- `tax_repartition_line_id` **(many2one)** — Originator Tax Distribution Line 🔒 readonly → `account.tax.repartition.line`
  > Tax distribution line that caused the creation of this move line, if any
- `tax_tag_ids` **(many2many)** — Tags → `account.account.tag`
  > Tags assigned to this line by the tax creating it, if any. It determines its impact on financial reports.
- `full_reconcile_id` **(many2one)** — Matching 🔒 readonly → `account.full.reconcile`
- `matched_debit_ids` **(one2many)** — Matched Debits 🔒 readonly → `account.partial.reconcile`
  > Debit journal items that are matched with this journal item.
- `matched_credit_ids` **(one2many)** — Matched Credits 🔒 readonly → `account.partial.reconcile`
  > Credit journal items that are matched with this journal item.
- `reconciled_lines_ids` **(many2many)** — Reconciled Lines → `account.move.line`
- `reconciled_lines_excluding_exchange_diff_ids` **(many2many)** — Reconciled Lines Excluding Exchange Diff 🔒 readonly → `account.move.line`
- `account_root_id` **(many2one)** — Account Root 🔒 readonly → `account.root`
- `product_category_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `parent_id` **(many2one)** — Parent Section Line 🔒 readonly → `account.move.line`
- `product_id` **(many2one)** — Product → `product.product`
- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `product_uom_id` **(many2one)** — Unit → `uom.uom`
- `analytic_line_ids` **(one2many)** — Analytic lines → `account.analytic.line`
- `move_attachment_ids` **(one2many)** — Move Attachment 🔒 readonly → `ir.attachment`
- `expense_id` **(many2one)** — Expense → `hr.expense`
- `purchase_line_id` **(many2one)** — Purchase Order Line → `purchase.order.line`
- `purchase_order_id` **(many2one)** — Purchase Order 🔒 readonly → `purchase.order`
- `cogs_origin_id` **(many2one)** — Cogs Origin → `account.move.line`
- `l10n_latam_document_type_id` **(many2one)** — Document Type 🔒 readonly → `l10n_latam.document.type`
- `sale_line_ids` **(many2many)** — Sales Order Lines 🔒 readonly → `sale.order.line`
- `followup_line_id` **(many2one)** — Follow-up Level → `account_followup.followup.line`
- `asset_ids` **(many2many)** — Related Assets → `account.asset`
- `l10n_br_goods_operation_type_id` **(many2one)** — Override Operation Type → `l10n_br.operation.type`
  > Brazil: If an Operation Type is selected, it will be applied to the product in the line, determining the CFOP for that line. If no selection is made, the operation type will be inherited from the header.

## Campos Calculados (readonly)

- `move_type` **(selection)** — Type 🔒 readonly
  > Opções: `entry` (Journal Entry), `out_invoice` (Customer Invoice), `out_refund` (Customer Credit Note), `in_invoice` (Vendor Bill), `in_refund` (Vendor Credit Note), `out_receipt` (Sales Receipt), `in_receipt` (Purchase Receipt)
- `account_name` **(char)** — Account Name 🔒 readonly
- `account_code` **(char)** — Code 🔒 readonly
- `translated_product_name` **(text)** — Translated Product Name 🔒 readonly
- `cumulated_balance` **(monetary)** — Cumulated Balance 🔒 readonly
  > Cumulated balance depending on the domain and the order chosen in the view.
- `currency_rate` **(float)** — Currency Rate 🔒 readonly
  > Currency rate from company currency to document currency.
- `is_same_currency` **(boolean)** — Is Same Currency 🔒 readonly
- `is_account_reconcile` **(boolean)** — Account Reconcile 🔒 readonly
  > Check this box if this account allows invoices & payments matching of journal items.
- `account_type` **(selection)** — Internal Type 🔒 readonly
  > Account Type is used for information purpose, to generate country-specific legal reports, and set the rules to close a fiscal year and generate opening entries.
  > Opções: `asset_receivable` (Receivable), `asset_cash` (Bank and Cash), `asset_current` (Current Assets), `asset_non_current` (Non-current Assets), `asset_prepayments` (Prepayments), `asset_fixed` (Fixed Assets), `liability_payable` (Payable), `liability_credit_card` (Credit Card), `liability_current` (Current Liabilities), `liability_non_current` (Non-current Liabilities), `equity` (Equity), `equity_unaffected` (Current Year Earnings), `income` (Income), `income_other` (Other Income), `expense` (Expenses), `expense_other` (Other Expenses), `expense_depreciation` (Depreciation), `expense_direct_cost` (Cost of Revenue), `off_balance` (Off-Balance Sheet)
- `account_internal_group` **(selection)** — Internal Group 🔒 readonly
  > Opções: `equity` (Equity), `asset` (Asset), `liability` (Liability), `income` (Income), `expense` (Expense), `off` (Off Balance)
- `tax_calculation_rounding_method` **(selection)** — Tax calculation rounding method 🔒 readonly
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `term_key` **(binary)** — Term Key 🔒 readonly
- `epd_key` **(binary)** — Epd Key 🔒 readonly
- `epd_needed` **(binary)** — Epd Needed 🔒 readonly
- `epd_dirty` **(boolean)** — Epd Dirty 🔒 readonly
- `discount_allocation_key` **(binary)** — Discount Allocation Key 🔒 readonly
- `discount_allocation_needed` **(binary)** — Discount Allocation Needed 🔒 readonly
- `discount_allocation_dirty` **(boolean)** — Discount Allocation Dirty 🔒 readonly
- `has_invalid_analytics` **(boolean)** — Has Invalid Analytics 🔒 readonly
- `payment_date` **(date)** — Next Payment Date 🔒 readonly
- `is_refund` **(boolean)** — Is Refund 🔒 readonly
- `has_deferred_moves` **(boolean)** — Has Deferred Moves 🔒 readonly
- `has_abnormal_deferred_dates` **(boolean)** — Has Abnormal Deferred Dates 🔒 readonly
- `full_amount_switch_html` **(html)** — Full Amount Switch Html 🔒 readonly
- `purchase_line_warn_msg` **(text)** — Purchase Line Warn Msg 🔒 readonly
- `analytic_coverage` **(float)** — Analytic Coverage 🔒 readonly
- `l10n_latam_use_documents` **(boolean)** — L10N Latam Use Documents 🔒 readonly
- `sale_line_warn_msg` **(text)** — Sale Line Warn Msg 🔒 readonly
- `invoice_origin` **(char)** — Origin 🔒 readonly
  > The document(s) that generated the invoice.
- `non_deductible_tax_value` **(monetary)** — Non Deductible Tax Value 🔒 readonly
- `l10n_br_cfop` **(char)** — CFOP 🔒 readonly
  > Brazil: CFOP returned from the tax calculation that will be used for submitting your electronic invoice per line. This is computed based on the Operation Type, product, contact and company configuration.
