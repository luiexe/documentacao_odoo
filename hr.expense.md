# Expense — `hr.expense`

**Ordenação padrão:** `extract_state_processed desc, date desc, id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Description ⚠️ obrigatório
- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `quantity` **(float)** — Quantity ⚠️ obrigatório
- `price_unit` **(float)** — Unit Price ⚠️ obrigatório 🔒 readonly
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`
- `payment_mode` **(selection)** — Paid By ⚠️ obrigatório
  > Opções: `own_account` (Employee (to reimburse)), `company_account` (Company)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `date` **(date)** — Expense Date
- `description` **(text)** — Internal Notes
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Draft), `submitted` (Submitted), `approved` (Approved), `posted` (Posted), `in_payment` (In Payment), `paid` (Paid), `refused` (Refused)
- `approval_state` **(selection)** — Approval State 🔒 readonly
  > Opções: `submitted` (Submitted), `approved` (Approved), `refused` (Refused)
- `approval_date` **(datetime)** — Approval Date 🔒 readonly
- `tax_amount_currency` **(monetary)** — Tax amount in Currency 🔒 readonly
  > Tax amount in currency
- `tax_amount` **(monetary)** — Tax amount 🔒 readonly
  > Tax amount in company currency
- `total_amount_currency` **(monetary)** — Total In Currency
- `total_amount` **(monetary)** — Total
- `untaxed_amount_currency` **(monetary)** — Total Untaxed Amount In Currency 🔒 readonly
- `untaxed_amount` **(monetary)** — Total Untaxed Amount 🔒 readonly
- `former_sheet_id` **(integer)** — Former Report
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `extract_state` **(selection)** — Extract state
  > Opções: `no_extract_requested` (No extract requested), `not_enough_credit` (Not enough credits), `error_status` (An error occurred), `waiting_extraction` (Waiting extraction), `extract_not_ready` (waiting extraction, but it is not ready), `waiting_validation` (Waiting validation), `to_validate` (To validate), `done` (Completed flow)
- `extract_status` **(char)** — Extract status
- `extract_document_uuid` **(char)** — ID of the request to IAP-OCR 🔒 readonly
- `is_in_extractable_state` **(boolean)** — Is In Extractable State 🔒 readonly
- `extract_state_processed` **(boolean)** — Extract State Processed 🔒 readonly
- `sample` **(boolean)** — Sample
  > Expenses created from sample receipt

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `manager_id` **(many2one)** — Manager 🔒 readonly → `res.users`
- `product_id` **(many2one)** — Category → `product.product`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
- `attachment_ids` **(one2many)** — Attachments → `ir.attachment`
- `duplicate_expense_ids` **(many2many)** — Duplicate Expense 🔒 readonly → `hr.expense`
- `same_receipt_expense_ids` **(many2many)** — Same Receipt Expense 🔒 readonly → `hr.expense`
- `split_expense_origin_id` **(many2one)** — Origin Split Expense → `hr.expense`
  > Original expense from a split.
- `company_currency_id` **(many2one)** — Report Company Currency 🔒 readonly → `res.currency`
- `journal_id` **(many2one)** — Journal 🔒 readonly → `account.journal`
- `selectable_payment_method_line_ids` **(many2many)** — Selectable Payment Method Line 🔒 readonly → `account.payment.method.line`
- `payment_method_line_id` **(many2one)** — Payment Method → `account.payment.method.line`
  > The payment method used when the expense is paid by the company.
- `account_move_id` **(many2one)** — Journal Entry 🔒 readonly → `account.move`
- `vendor_id` **(many2one)** — Vendor → `res.partner`
- `account_id` **(many2one)** — Account → `account.account`
  > An expense account is expected
- `tax_ids` **(many2many)** — Included taxes → `account.tax`
  > Both price-included and price-excluded taxes will behave as price-included taxes for expenses.
- `sale_order_id` **(many2one)** — Customer to Reinvoice → `sale.order`
  > If the category has an expense policy, it will be reinvoiced on this sales order
- `sale_order_line_id` **(many2one)** — Sale Order Line 🔒 readonly → `sale.order.line`

## Campos Calculados (readonly)

- `product_description` **(html)** — Product Description 🔒 readonly
- `product_has_cost` **(boolean)** — Product Has Cost 🔒 readonly
- `product_has_tax` **(boolean)** — Whether tax is defined on a selected product 🔒 readonly
- `message_main_attachment_checksum` **(char)** — Checksum/SHA1 🔒 readonly
- `nb_attachment` **(integer)** — Number of Attachments 🔒 readonly
- `amount_residual` **(monetary)** — Amount Due 🔒 readonly
- `is_multiple_currency` **(boolean)** — Is currency_id different from the company_currency_id 🔒 readonly
- `currency_rate` **(float)** — Currency Rate 🔒 readonly
- `label_currency_rate` **(char)** — Label Currency Rate 🔒 readonly
- `is_editable` **(boolean)** — Is Editable By Current User 🔒 readonly
- `can_reset` **(boolean)** — Can Reset 🔒 readonly
- `can_approve` **(boolean)** — Can Approve 🔒 readonly
- `extract_error_message` **(text)** — Error message 🔒 readonly
- `extract_can_show_send_button` **(boolean)** — Can show the ocr send button 🔒 readonly
- `document_count` **(integer)** — Document Count 🔒 readonly
- `can_be_reinvoiced` **(boolean)** — Can be reinvoiced 🔒 readonly
