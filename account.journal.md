# Journal — `account.journal`

**Ordenação padrão:** `sequence, type, code`

---

## Campos Obrigatórios

- `name` **(char)** — Journal Name ⚠️ obrigatório
- `code` **(char)** — Sequence Prefix ⚠️ obrigatório
  > Shorter name used for display. The journal entries of this journal will also be named using this prefix by default.
- `type` **(selection)** — Type ⚠️ obrigatório
  >          Select 'Sale' for customer invoices journals.         Select 'Purchase' for vendor bills journals.         Select 'Cash', 'Bank' or 'Credit Card' for journals that are used in customer or vendor payments.         Select 'General' for miscellaneous operations journals.         
  > Opções: `sale` (Sales), `purchase` (Purchase), `cash` (Cash), `bank` (Bank), `credit` (Credit Card), `general` (Miscellaneous)
- `invoice_reference_type` **(selection)** — Communication Type ⚠️ obrigatório
  > You can set here the default communication that will appear on customer invoices, once validated, to help the customer to refer to that particular invoice when making the payment.
  > Opções: `partner` (Based on Customer), `invoice` (Based on Invoice)
- `invoice_reference_model` **(selection)** — Communication Standard ⚠️ obrigatório
  > You can choose different models for each type of reference. The default one is the Odoo reference.
  > Opções: `odoo` (Full Reference (INV/2024/00001)), `euro` (European (RF83INV202400001)), `number` (Numbers only (202400001))
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
  > Company related to this journal

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `alias_name` **(char)** — Alias Name
  > Send one separate email for each invoice. Any file extension will be accepted. Only PDF and XML files will be interpreted by Odoo
- `access_token` **(char)** — Security Token
- `active` **(boolean)** — Active
  > Set active to false to hide the Journal without removing it.
- `is_self_billing` **(boolean)** — Self Billing
  > This journal is for self-billing invoices. Invoices will be created using a different sequence per partner.
- `restrict_mode_hash_table` **(boolean)** — Secure Posted Entries with Hash
  > If ticked, when an entry is posted, we retroactively hash all moves in the sequence from the entry back to the last hashed entry. The hash can also be performed on demand by the Secure Entries wizard.
- `sequence` **(integer)** — Sequence
  > Used to order Journals in the dashboard view
- `refund_sequence` **(boolean)** — Dedicated Credit Note Sequence
  > Check this box if you don't want to share the same sequence for invoices and credit notes made from this journal
- `payment_sequence` **(boolean)** — Dedicated Payment Sequence
  > Check this box if you don't want to share the same sequence on payments and bank transactions posted on this journal
- `display_invoice_template_pdf_report_id` **(boolean)** — Display Invoice Template Pdf Report
- `sequence_override_regex` **(text)** — Sequence Override Regex
  > Technical field used to enforce complex sequence composition that the system would normally misunderstand. This is a regex that can include all the following capture groups: prefix1, year, prefix2, month, prefix3, seq, suffix. The prefix* groups are the separators between the year, month and the actual increasing sequence number (seq). e.g: ^(?P<prefix1>.*?)(?P<year>\d{4})(?P<prefix2>\D*?)(?P<month>\d{2})(?P<prefix3>\D+?)(?P<seq>\d+)(?P<suffix>\D*?)$
- `bank_statements_source` **(selection)** — Bank Feeds
  > Defines how the bank statements will be registered
  > Opções: `undefined` (Undefined Yet), `file_import` (Manual (or import CAMT, CSV, JPEG, OFX, PDF, PNG, XLS, XLSX)), `online_sync` (Online Synchronization)
- `bank_acc_number` **(char)** — Account Number
- `incoming_einvoice_notification_email` **(char)** — Send Copy To
  > Email addresses that will receive copy for sent and received invoices. Separate entries with ';'.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `show_on_dashboard` **(boolean)** — Show journal on dashboard
  > Whether this journal should be displayed on the dashboard or not
- `color` **(integer)** — Color Index
- `debit_sequence` **(boolean)** — Dedicated Debit Note Sequence
  > Check this box if you don't want to share the same sequence for invoices and debit notes made from this journal
- `renewal_contact_email` **(char)** — Connection Requests
  > Comma separated list of email addresses to send consent renewal notifications 15, 3 and 1 days before expiry
- `l10n_latam_use_documents` **(boolean)** — Use Documents?
  > If active: will be using for legal invoicing (invoices, debit/credit notes). If not set means that will be used to register accounting entries not related to invoicing legal documents. For Example: Receipts, Tax Payments, Register journal entries
- `l10n_br_invoice_serial` **(char)** — Series
  > Brazil: Series number associated with this Journal. If more than one Series needs to be used, duplicate this Journal and assign the new Series to the duplicated Journal.
- `loan_properties_definition` **(properties_definition)** — Model Properties

## Relacionamentos

- `alias_id` **(many2one)** — Alias → `mail.alias`
- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `default_account_id` **(many2one)** — Default Account → `account.account`
- `suspense_account_id` **(many2one)** — Suspense Account → `account.account`
  > Bank statements transactions will be posted on the suspense account until the final reconciliation allowing finding the right account.
- `non_deductible_account_id` **(many2one)** — Private Share Account → `account.account`
  > Account used to register the private part of mixed expenses.
- `currency_id` **(many2one)** — Currency → `res.currency`
  > The currency used to enter statement
- `invoice_template_pdf_report_id` **(many2one)** — Invoice report → `ir.actions.report`
- `available_invoice_template_pdf_report_ids` **(one2many)** — Available Invoice Template Pdf Report 🔒 readonly → `ir.actions.report`
- `inbound_payment_method_line_ids` **(one2many)** — Inbound Payment Methods → `account.payment.method.line`
  > Manual: Get paid by any method outside of Odoo. Payment Providers: Each payment provider has its own Payment Method. Request a transaction on/to a card thanks to a payment token saved by the partner when buying or subscribing online. Batch Deposit: Collect several customer checks at once generating and submitting a batch deposit to your bank. Module account_batch_payment is necessary. SEPA Direct Debit: Get paid in the SEPA zone thanks to a mandate your partner will have granted to you. Module account_sepa is necessary. 
- `outbound_payment_method_line_ids` **(one2many)** — Outbound Payment Methods → `account.payment.method.line`
  > Manual: Pay by any method outside of Odoo. Check: Pay bills by check and print it from Odoo. SEPA Credit Transfer: Pay in the SEPA zone by submitting a SEPA Credit Transfer file to your bank. Module account_sepa is necessary. 
- `profit_account_id` **(many2one)** — Profit Account → `account.account`
  > Used to register a profit when the ending balance of a cash register differs from what the system computes
- `loss_account_id` **(many2one)** — Loss Account → `account.account`
  > Used to register a loss when the ending balance of a cash register differs from what the system computes
- `company_partner_id` **(many2one)** — Account Holder 🔒 readonly → `res.partner`
- `bank_account_id` **(many2one)** — Bank Account → `res.partner.bank`
- `bank_id` **(many2one)** — Bank → `res.bank`
- `journal_group_ids` **(many2many)** — Ledger Group → `account.journal.group`
- `available_payment_method_ids` **(many2many)** — Available Payment Method 🔒 readonly → `account.payment.method`
- `last_statement_id` **(many2one)** — Last Statement 🔒 readonly → `account.bank.statement`
- `account_online_account_id` **(many2one)** — Account Online Account → `account.online.account`
- `account_online_link_id` **(many2one)** — Account Online Link 🔒 readonly → `account.online.link`

## Campos Calculados (readonly)

- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_defaults` **(text)** — Default Values 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `alias_email` **(char)** — Email Alias 🔒 readonly
- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `name_placeholder` **(char)** — Name Placeholder 🔒 readonly
- `default_account_type` **(char)** — Default Account Type 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `account_fiscal_country_group_codes` **(json)** — Account Fiscal Country Group Codes 🔒 readonly
- `selected_payment_method_codes` **(char)** — Selected Payment Method Codes 🔒 readonly
- `accounting_date` **(date)** — Accounting Date 🔒 readonly
- `display_alias_fields` **(boolean)** — Display Alias Fields 🔒 readonly
- `has_invalid_statements` **(boolean)** — Has Invalid Statements 🔒 readonly
- `show_fetch_in_einvoices_button` **(boolean)** — Show E-Invoice Buttons 🔒 readonly
- `show_refresh_out_einvoices_status_button` **(boolean)** — Show E-Invoice Status Buttons 🔒 readonly
- `kanban_dashboard` **(text)** — Kanban Dashboard 🔒 readonly
- `kanban_dashboard_graph` **(text)** — Kanban Dashboard Graph 🔒 readonly
- `json_activity_data` **(text)** — Json Activity Data 🔒 readonly
- `current_statement_balance` **(monetary)** — Current Statement Balance 🔒 readonly
- `has_statement_lines` **(boolean)** — Has Statement Lines 🔒 readonly
- `entries_count` **(integer)** — Entries Count 🔒 readonly
- `has_posted_entries` **(boolean)** — Has Posted Entries 🔒 readonly
- `has_entries` **(boolean)** — Has Entries 🔒 readonly
- `has_sequence_holes` **(boolean)** — Has Sequence Holes 🔒 readonly
- `has_unhashed_entries` **(boolean)** — Unhashed Entries 🔒 readonly
- `next_link_synchronization` **(datetime)** — Online Link Next synchronization 🔒 readonly
- `expiring_synchronization_date` **(date)** — Expiring Synchronization Date 🔒 readonly
  > Date when the consent for this connection expires
- `expiring_synchronization_due_day` **(integer)** — Expiring Synchronization Due Day 🔒 readonly
- `account_online_link_state` **(selection)** — State 🔒 readonly
  > Opções: `connected` (Connected), `error` (Error), `disconnected` (Not Connected)
- `online_sync_fetching_status` **(selection)** — Fetching Status 🔒 readonly
  > Opções: `planned` (Planned), `waiting` (Waiting), `processing` (Processing), `done` (Done)
- `l10n_latam_company_use_documents` **(boolean)** — L10N Latam Company Use Documents 🔒 readonly
