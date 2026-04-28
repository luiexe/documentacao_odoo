# Payments — `account.payment`

**Ordenação padrão:** `date desc, name desc`

---

## Campos Obrigatórios

- `date` **(date)** — Date ⚠️ obrigatório
- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `state` **(selection)** — State ⚠️ obrigatório
  > Opções: `draft` (Draft), `in_process` (In Process), `paid` (Paid), `canceled` (Canceled), `rejected` (Rejected)
- `payment_type` **(selection)** — Payment Type ⚠️ obrigatório
  > Opções: `outbound` (Send), `inbound` (Receive)
- `partner_type` **(selection)** — Partner Type ⚠️ obrigatório
  > Opções: `customer` (Customer), `supplier` (Vendor)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Number 🔒 readonly
- `is_reconciled` **(boolean)** — Is Reconciled 🔒 readonly
- `is_matched` **(boolean)** — Is Matched With a Bank Statement 🔒 readonly
- `is_sent` **(boolean)** — Is Sent 🔒 readonly
- `amount` **(monetary)** — Amount
- `memo` **(char)** — Memo
- `payment_reference` **(char)** — Payment Reference
  > Reference of the document used to issue this payment. Eg. check number, file name, etc.
- `amount_company_currency_signed` **(monetary)** — Amount Company Currency Signed 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `move_id` **(many2one)** — Journal Entry → `account.move`
- `available_partner_bank_ids` **(many2many)** — Available Partner Bank 🔒 readonly → `res.partner.bank`
- `partner_bank_id` **(many2one)** — Recipient Bank Account → `res.partner.bank`
- `paired_internal_transfer_payment_id` **(many2one)** — Paired Internal Transfer Payment → `account.payment`
  > When an internal transfer is posted, a paired payment is created. They are cross referenced through this field
- `payment_method_line_id` **(many2one)** — Payment Method → `account.payment.method.line`
  > Manual: Pay or Get paid by any method outside of Odoo. Payment Providers: Each payment provider has its own Payment Method. Request a transaction on/to a card thanks to a payment token saved by the partner when buying or subscribing online. Check: Pay bills by check and print it from Odoo. Batch Deposit: Collect several customer checks at once generating and submitting a batch deposit to your bank. Module account_batch_payment is necessary. SEPA Credit Transfer: Pay in the SEPA zone by submitting a SEPA Credit Transfer file to your bank. Module account_iso20022 is necessary. SEPA Direct Debit: Get paid in the SEPA zone thanks to a mandate your partner will have granted to you. Module account_iso20022 is necessary. U.S. ISO20022: Pay in the US by submitting an ISO20022 file to your bank. Module account_iso20022 is necessary. 
- `available_payment_method_line_ids` **(many2many)** — Available Payment Method Line 🔒 readonly → `account.payment.method.line`
- `payment_method_id` **(many2one)** — Method 🔒 readonly → `account.payment.method`
- `available_journal_ids` **(many2many)** — Available Journal 🔒 readonly → `account.journal`
- `currency_id` **(many2one)** — Currency → `res.currency`
  > The payment's currency.
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `partner_id` **(many2one)** — Customer/Vendor → `res.partner`
- `outstanding_account_id` **(many2one)** — Outstanding Account 🔒 readonly → `account.account`
- `destination_account_id` **(many2one)** — Destination Account → `account.account`
- `invoice_ids` **(many2many)** — Invoices → `account.move`
- `reconciled_invoice_ids` **(many2many)** — Reconciled Invoices 🔒 readonly → `account.move`
  > Invoices whose journal items have been reconciled with these payments.
- `reconciled_bill_ids` **(many2many)** — Reconciled Bills 🔒 readonly → `account.move`
  > Invoices whose journal items have been reconciled with these payments.
- `reconciled_statement_line_ids` **(many2many)** — Reconciled Statement Lines 🔒 readonly → `account.bank.statement.line`
  > Statements lines matched to this payment
- `duplicate_payment_ids` **(many2many)** — Duplicate Payment 🔒 readonly → `account.payment`
- `attachment_ids` **(one2many)** — Attachments → `ir.attachment`
- `payment_transaction_id` **(many2one)** — Payment Transaction 🔒 readonly → `payment.transaction`
- `payment_token_id` **(many2one)** — Saved Payment Token → `payment.token`
  > Note that only tokens from providers allowing to capture the amount are available.
- `suitable_payment_token_ids` **(many2many)** — Suitable Payment Token 🔒 readonly → `payment.token`
- `source_payment_id` **(many2one)** — Source Payment 🔒 readonly → `account.payment`
  > The source payment of related refund payments
- `expense_ids` **(one2many)** — Expense 🔒 readonly → `hr.expense`

## Campos Calculados (readonly)

- `qr_code` **(html)** — QR Code URL 🔒 readonly
- `reconciled_invoices_count` **(integer)** — # Reconciled Invoices 🔒 readonly
- `reconciled_invoices_type` **(selection)** — Reconciled Invoices Type 🔒 readonly
  > Opções: `credit_note` (Credit Note), `invoice` (Invoice)
- `reconciled_bills_count` **(integer)** — # Reconciled Bills 🔒 readonly
- `reconciled_statement_lines_count` **(integer)** — # Reconciled Statement Lines 🔒 readonly
- `payment_method_code` **(char)** — Code 🔒 readonly
- `payment_receipt_title` **(char)** — Payment Receipt Title 🔒 readonly
- `need_cancel_request` **(boolean)** — Need Cancel Request 🔒 readonly
- `show_partner_bank_account` **(boolean)** — Show Partner Bank Account 🔒 readonly
- `require_partner_bank_account` **(boolean)** — Require Partner Bank Account 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `amount_signed` **(monetary)** — Amount Signed 🔒 readonly
  > Negative value of amount field if payment_type is outbound
- `amount_available_for_refund` **(monetary)** — Amount Available For Refund 🔒 readonly
- `use_electronic_payment_method` **(boolean)** — Use Electronic Payment Method 🔒 readonly
- `refunds_count` **(integer)** — Refunds Count 🔒 readonly
- `is_donation` **(boolean)** — Is Donation 🔒 readonly
