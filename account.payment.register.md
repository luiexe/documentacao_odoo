# Pay — `account.payment.register`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `payment_date` **(date)** — Payment Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount` **(monetary)** — Amount
- `communication` **(char)** — Memo
- `group_payment` **(boolean)** — Group Payments
  > Only one payment will be created by partner (bank), instead of one per bill.
- `installments_mode` **(selection)** — Installments Mode
  > Opções: `next` (Next Installment), `overdue` (Overdue Amount), `before_date` (Before Next Payment Date), `full` (Full Amount)
- `custom_user_amount` **(monetary)** — Custom User Amount
- `payment_type` **(selection)** — Payment Type 🔒 readonly
  > Opções: `outbound` (Send Money), `inbound` (Receive Money)
- `partner_type` **(selection)** — Partner Type 🔒 readonly
  > Opções: `customer` (Customer), `supplier` (Vendor)
- `source_amount` **(monetary)** — Amount to Pay (company currency) 🔒 readonly
- `source_amount_currency` **(monetary)** — Amount to Pay (foreign currency) 🔒 readonly
- `can_edit_wizard` **(boolean)** — Can Edit Wizard 🔒 readonly
- `can_group_payments` **(boolean)** — Can Group Payments 🔒 readonly
- `payment_difference_handling` **(selection)** — Payment Difference Handling
  > Opções: `open` (Keep open), `reconcile` (Mark as fully paid)
- `writeoff_label` **(char)** — Journal Item Label
  > Change label of the counterpart that will hold the payment difference
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency → `res.currency`
  > The payment's currency.
- `journal_id` **(many2one)** — Journal → `account.journal`
- `available_journal_ids` **(many2many)** — Available Journal 🔒 readonly → `account.journal`
- `available_partner_bank_ids` **(many2many)** — Available Partner Bank 🔒 readonly → `res.partner.bank`
- `partner_bank_id` **(many2one)** — Recipient Bank Account → `res.partner.bank`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `custom_user_currency_id` **(many2one)** — Custom User Currency → `res.currency`
- `line_ids` **(many2many)** — Journal items 🔒 readonly → `account.move.line`
- `source_currency_id` **(many2one)** — Source Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `partner_id` **(many2one)** — Customer/Vendor 🔒 readonly → `res.partner`
- `payment_method_line_id` **(many2one)** — Payment Method → `account.payment.method.line`
  > Manual: Pay or Get paid by any method outside of Odoo. Payment Providers: Each payment provider has its own Payment Method. Request a transaction on/to a card thanks to a payment token saved by the partner when buying or subscribing online. Check: Pay bills by check and print it from Odoo. Batch Deposit: Collect several customer checks at once generating and submitting a batch deposit to your bank. Module account_batch_payment is necessary. SEPA Credit Transfer: Pay in the SEPA zone by submitting a SEPA Credit Transfer file to your bank. Module account_sepa is necessary. SEPA Direct Debit: Get paid in the SEPA zone thanks to a mandate your partner will have granted to you. Module account_sepa is necessary. 
- `available_payment_method_line_ids` **(many2many)** — Available Payment Method Line 🔒 readonly → `account.payment.method.line`
- `writeoff_account_id` **(many2one)** — Difference Account → `account.account`
- `duplicate_payment_ids` **(many2many)** — Duplicate Payment 🔒 readonly → `account.payment`
- `untrusted_bank_ids` **(many2many)** — Untrusted Bank 🔒 readonly → `res.partner.bank`
- `missing_account_partners` **(many2many)** — Missing Account Partners 🔒 readonly → `res.partner`
- `payment_token_id` **(many2one)** — Saved payment token → `payment.token`
  > Note that tokens from providers set to only authorize transactions (instead of capturing the amount) are not available.
- `suitable_payment_token_ids` **(many2many)** — Suitable Payment Token 🔒 readonly → `payment.token`

## Campos Calculados (readonly)

- `hide_writeoff_section` **(boolean)** — Hide Writeoff Section 🔒 readonly
- `early_payment_discount_mode` **(boolean)** — Early Payment Discount Mode 🔒 readonly
- `qr_code` **(html)** — QR Code URL 🔒 readonly
- `batches` **(binary)** — Batches 🔒 readonly
- `installments_switch_html` **(html)** — Installments Switch Html 🔒 readonly
- `installments_switch_amount` **(monetary)** — Installments Switch Amount 🔒 readonly
- `payment_method_code` **(char)** — Code 🔒 readonly
- `payment_difference` **(monetary)** — Payment Difference 🔒 readonly
- `writeoff_is_exchange_account` **(boolean)** — Writeoff Is Exchange Account 🔒 readonly
- `show_payment_difference` **(boolean)** — Show Payment Difference 🔒 readonly
- `show_partner_bank_account` **(boolean)** — Show Partner Bank Account 🔒 readonly
- `require_partner_bank_account` **(boolean)** — Require Partner Bank Account 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `is_register_payment_on_draft` **(boolean)** — Is Register Payment On Draft 🔒 readonly
- `actionable_errors` **(json)** — Actionable Errors 🔒 readonly
- `total_payments_amount` **(integer)** — Total Payments Amount 🔒 readonly
- `untrusted_payments_count` **(integer)** — Untrusted Payments Count 🔒 readonly
- `use_electronic_payment_method` **(boolean)** — Use Electronic Payment Method 🔒 readonly
