# Journal Entry — `account.move`

**Ordenação padrão:** `date desc, name desc, invoice_date desc, id desc`

---

## Campos Obrigatórios

- `date` **(date)** — Date ⚠️ obrigatório
- `state` **(selection)** — Status ⚠️ obrigatório 🔒 readonly
  > Opções: `draft` (Draft), `posted` (Posted), `cancel` (Cancelled)
- `move_type` **(selection)** — Type ⚠️ obrigatório 🔒 readonly
  > Opções: `entry` (Journal Entry), `out_invoice` (Customer Invoice), `out_refund` (Customer Credit Note), `in_invoice` (Vendor Bill), `in_refund` (Vendor Credit Note), `out_receipt` (Sales Receipt), `in_receipt` (Purchase Receipt)
- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`
- `auto_post` **(selection)** — Auto-post ⚠️ obrigatório
  > Specify whether this entry is posted automatically on its accounting date, and any similar recurring invoices.
  > Opções: `no` (No), `at_date` (At Date), `monthly` (Monthly), `quarterly` (Quarterly), `yearly` (Yearly)
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `l10n_br_use_type` **(selection)** — Purpose of Use
  > Brazil: this will override the purpose of use for all products sold here.
  > Opções: `use or consumption` (Use or consumption), `resale` (Resale), `agricultural production` (Agricultural production), `production` (Production), `fixed assets` (Fixed assets), `notApplicable` (Not applicable)
- `l10n_br_presence` **(selection)** — Presence
  > Brazil: Defines if the buyer was physically present during the transaction, affecting tax calculation and location.
  > Opções: `0` (Not applicable), `1` (Present), `2` (Remote, internet), `3` (Remote, phone), `4` (NFC-e home delivery), `5` (In-person operation, for establishment (v3)), `9` (Remote, others)
- `sequence_prefix` **(char)** — Sequence Prefix 🔒 readonly
- `sequence_number` **(integer)** — Sequence Number 🔒 readonly
- `access_token` **(char)** — Security Token
- `name` **(char)** — Number
- `ref` **(char)** — Reference
- `always_tax_exigible` **(boolean)** — Always Tax Exigible
- `auto_post_until` **(date)** — Auto-post until
  > This recurring move will be posted up to and including this date.
- `checked` **(boolean)** — Reviewed
- `posted_before` **(boolean)** — Posted Before
- `made_sequence_gap` **(boolean)** — Made Sequence Gap 🔒 readonly
- `show_name_warning` **(boolean)** — Show Name Warning
- `no_followup` **(boolean)** — No Follow-Up
  > Exclude this journal entry from follow-up reports.
- `secure_sequence_number` **(integer)** — Inalterability No Gap Sequence # 🔒 readonly
- `inalterable_hash` **(char)** — Inalterability Hash 🔒 readonly
- `invoice_date` **(date)** — Invoice/Bill Date
- `invoice_date_due` **(date)** — Due Date
- `delivery_date` **(date)** — Delivery Date
- `taxable_supply_date` **(date)** — Taxable Supply Date
- `payment_reference` **(char)** — Payment Reference
  > The payment reference to set on journal items.
- `qr_code_method` **(selection)** — Payment QR-code
  > Type of QR-code to be generated for the payment of this invoice, when printing it. If left blank, the first available and usable method will be used.
  > Opções: `emv_qr` (EMV Merchant-Presented QR-code)
- `invoice_currency_rate` **(float)** — Currency Rate
  > Currency rate from company currency to document currency.
- `amount_untaxed` **(monetary)** — Untaxed Amount 🔒 readonly
- `amount_tax` **(monetary)** — Tax 🔒 readonly
- `amount_total` **(monetary)** — Total 🔒 readonly
- `amount_residual` **(monetary)** — Amount Due 🔒 readonly
- `amount_untaxed_signed` **(monetary)** — Untaxed Amount Signed 🔒 readonly
- `amount_untaxed_in_currency_signed` **(monetary)** — Untaxed Amount Signed Currency 🔒 readonly
- `amount_tax_signed` **(monetary)** — Tax Signed 🔒 readonly
- `amount_total_signed` **(monetary)** — Total Signed 🔒 readonly
- `amount_total_in_currency_signed` **(monetary)** — Total in Currency Signed 🔒 readonly
- `amount_residual_signed` **(monetary)** — Amount Due Signed 🔒 readonly
- `tax_totals` **(binary)** — Invoice Totals
  > Edit Tax amounts if you encounter rounding issues.
- `payment_state` **(selection)** — Payment Status 🔒 readonly
  > Opções: `not_paid` (Not Paid), `in_payment` (In Payment), `paid` (Paid), `partial` (Partially Paid), `reversed` (Reversed), `blocked` (Blocked), `invoicing_legacy` (Invoicing App Legacy)
- `invoice_source_email` **(char)** — Source Email
- `invoice_partner_display_name` **(char)** — Invoice Partner Display Name 🔒 readonly
- `is_manually_modified` **(boolean)** — Is Manually Modified
- `quick_edit_total_amount` **(monetary)** — Total (Tax inc.)
  > Use this field to encode the total amount of the invoice. Odoo will automatically create one invoice line with default values to match it.
- `narration` **(html)** — Terms and Conditions
- `is_move_sent` **(boolean)** — Is Move Sent 🔒 readonly
  > It indicates that the invoice/payment has been sent or the PDF has been generated.
- `invoice_origin` **(char)** — Origin 🔒 readonly
  > The document(s) that generated the invoice.
- `incoterm_location` **(char)** — Incoterm Location
- `sending_data` **(json)** — Sending Data
- `invoice_pdf_report_file` **(binary)** — PDF File
- `show_update_fpos` **(boolean)** — Has Fiscal Position Changed
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `payment_state_before_switch` **(char)** — Payment State Before Switch
- `ubl_cii_xml_file` **(binary)** — UBL/CII File
- `l10n_latam_document_number` **(char)** — Document Number
- `asset_value_change` **(boolean)** — Asset Value Change
- `asset_number_days` **(integer)** — Number of days
- `asset_depreciation_beginning_date` **(date)** — Date of the beginning of the depreciation
- `depreciation_value` **(monetary)** — Depreciation
- `asset_move_type` **(selection)** — Asset Move Type 🔒 readonly
  > Opções: `depreciation` (Depreciation), `sale` (Sale), `purchase` (Purchase), `disposal` (Disposal), `negative_revaluation` (Negative revaluation), `positive_revaluation` (Positive revaluation)
- `extract_state` **(selection)** — Extract state
  > Opções: `no_extract_requested` (No extract requested), `not_enough_credit` (Not enough credits), `error_status` (An error occurred), `waiting_extraction` (Waiting extraction), `extract_not_ready` (waiting extraction, but it is not ready), `waiting_validation` (Waiting validation), `to_validate` (To validate), `done` (Completed flow)
- `extract_status` **(char)** — Extract status
- `extract_document_uuid` **(char)** — ID of the request to IAP-OCR 🔒 readonly
- `is_in_extractable_state` **(boolean)** — Is In Extractable State 🔒 readonly
- `extract_state_processed` **(boolean)** — Extract State Processed 🔒 readonly
- `extracted_words` **(json)** — Extracted Words
- `extracted_numbers` **(json)** — Extracted Numbers
- `extracted_dates` **(json)** — Extracted Dates
- `extract_prefill_data` **(json)** — Extract Prefill Data
- `extract_detected_layout` **(integer)** — Extract Detected Layout Id 🔒 readonly
- `extract_partner_name` **(char)** — Extract Detected Partner Name 🔒 readonly
- `is_loan_payment_move` **(boolean)** — Is Loan Payment Move
- `l10n_br_edi_avatax_data` **(text)** — L10N Br Edi Avatax Data
  > Brazil: technical field that remembers the last tax summary returned by Avatax.
- `l10n_br_edi_freight_model` **(selection)** — Freight Model
  > Brazil: used to determine the freight model used on this transaction.
  > Opções: `CIF` (Freight contracting on behalf of the Sender (CIF)), `FOB` (Contracting of freight on behalf of the recipient/sender (FOB)), `Thirdparty` (Contracting Freight on behalf of third parties), `SenderVehicle` (Own transport on behalf of the sender), `ReceiverVehicle` (Own transport on behalf of the recipient), `FreeShipping` (Free shipping)
- `l10n_br_edi_payment_method` **(selection)** — Payment Method Brazil
  > Brazil: expected payment method to be used.
  > Opções: `01` (Money), `02` (Check), `03` (Credit Card), `04` (Debit Card), `05` (Store Credit), `10` (Food voucher), `11` (Meal Voucher), `12` (Gift certificate), `13` (Fuel Voucher), `14` (Duplicate Mercantil), `15` (Boleto Bancario), `16` (Bank Deposit), `17` (Instant Payment (PIX)), `18` (Bank transfer, Digital Wallet), `19` (Loyalty program, Cashback, Virtual Credit), `90` (No Payment), `99` (Others)
- `l10n_br_access_key` **(char)** — Access Key
  > Brazil: access key associated with the electronic document. Can be used to get invoice information directly from the government.
- `l10n_br_edi_error` **(text)** — Brazil E-Invoice Error 🔒 readonly
  > Brazil: error details for invoices in the 'error' state.
- `l10n_br_last_edi_status` **(selection)** — Brazil E-Invoice Status 🔒 readonly
  > Brazil: the state of the most recent e-invoicing attempt.
  > Opções: `pending` (Pending), `accepted` (Accepted), `error` (Error), `cancelled` (Cancelled)
- `l10n_br_edi_xml_attachment_file` **(binary)** — Brazil E-Invoice XML File
  > Brazil: technical field holding the e-invoice XML data for security reasons.
- `l10n_br_edi_last_correction_number` **(integer)** — Brazil Correction Number 🔒 readonly
  > Brazil: technical field that holds the latest correction that happened to this invoice
- `l10n_br_nfse_number` **(char)** — NFS-e Number
  > Brazil: After an NFS-e invoice is issued and confirmed by the municipality, an NFS-e number is provided.
- `l10n_br_nfse_verification` **(char)** — NFS-e Verification Code
  > Brazil: After an NFS-e invoice is issued and confirmed by the municipality, a unique code is provided for online verification of its authenticity.
- `l10n_br_plate_number` **(char)** — Plate Number
  > Brazil: vehicle plate number of the delivery vehicle.

## Relacionamentos

- `campaign_id` **(many2one)** — Campaign → `utm.campaign`
  > This is a name that helps you keep track of your different campaign efforts, e.g. Fall_Drive, Christmas_Special
- `source_id` **(many2one)** — Source → `utm.source`
  > This is the source of the link, e.g. Search Engine, another domain, or name of email list
- `medium_id` **(many2one)** — Medium → `utm.medium`
  > This is the method of delivery, e.g. Postcard, Email, or Banner Ad
- `l10n_br_cnae_code_id` **(many2one)** — CNAE Code → `l10n_br.cnae.code`
  > Brazil: the company's CNAE code for tax calculation and EDI.
- `l10n_br_goods_operation_type_id` **(many2one)** — Goods Operation Type → `l10n_br.operation.type`
  > Brazil: this is the operation type related to the goods transaction. This will be used as a default on transaction lines.
- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `journal_group_id` **(many2one)** — Ledger → `account.journal.group`
- `company_id` **(many2one)** — Company → `res.company`
- `line_ids` **(one2many)** — Journal Items → `account.move.line`
- `journal_line_ids` **(one2many)** — Journal Items (DEPRECATED) → `account.move.line`
- `exchange_diff_partial_ids` **(one2many)** — Related reconciliation → `account.partial.reconcile`
- `origin_payment_id` **(many2one)** — Payment → `account.payment`
- `matched_payment_ids` **(many2many)** — Matched Payments → `account.payment`
- `reconciled_payment_ids` **(many2many)** — Reconciled Payments 🔒 readonly → `account.payment`
  > Payments that have been reconciled with this invoice.
- `statement_line_id` **(many2one)** — Statement Line → `account.bank.statement.line`
- `statement_id` **(many2one)** — Statement 🔒 readonly → `account.bank.statement`
- `adjusting_entry_origin_move_ids` **(many2many)** — Adjusting Entry Origin Moves → `account.move`
- `adjusting_entries_move_ids` **(many2many)** — Created Adjusting Entries → `account.move`
- `tax_cash_basis_rec_id` **(many2one)** — Tax Cash Basis Entry of → `account.partial.reconcile`
- `tax_cash_basis_origin_move_id` **(many2one)** — Cash Basis Origin 🔒 readonly → `account.move`
  > The journal entry from which this tax cash basis journal entry has been created.
- `tax_cash_basis_created_move_ids` **(one2many)** — Cash Basis Entries → `account.move`
  > The cash basis entries created from the taxes on this entry, when reconciling its lines.
- `auto_post_origin_id` **(many2one)** — First recurring entry 🔒 readonly → `account.move`
- `suitable_journal_ids` **(many2many)** — Suitable Journal 🔒 readonly → `account.journal`
- `attachment_ids` **(one2many)** — Attachments → `ir.attachment`
- `invoice_line_ids` **(one2many)** — Invoice lines → `account.move.line`
- `invoice_payment_term_id` **(many2one)** — Payment Terms → `account.payment.term`
- `partner_id` **(many2one)** — Partner → `res.partner`
- `commercial_partner_id` **(many2one)** — Commercial Entity 🔒 readonly → `res.partner`
- `partner_shipping_id` **(many2one)** — Delivery Address → `res.partner`
  > The delivery address will be used in the computation of the fiscal position.
- `partner_bank_id` **(many2one)** — Recipient Bank → `res.partner.bank`
  > Bank Account Number to which the invoice will be paid. A Company bank account if this is a Customer Invoice or Vendor Credit Note, otherwise a Partner bank account number.
- `fiscal_position_id` **(many2one)** — Fiscal Position → `account.fiscal.position`
  > Fiscal positions are used to adapt taxes and accounts for particular customers or sales orders/invoices. The default value comes from the customer.
- `preferred_payment_method_line_id` **(many2one)** — Preferred Payment Method Line → `account.payment.method.line`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `reversed_entry_id` **(many2one)** — Reversal of 🔒 readonly → `account.move`
- `reversal_move_ids` **(one2many)** — Reversal Move → `account.move`
- `invoice_vendor_bill_id` **(many2one)** — Vendor Bill → `account.move`
  > Auto-complete from a previous bill or refund.
- `invoice_user_id` **(many2one)** — Salesperson → `res.users`
- `user_id` **(many2one)** — User 🔒 readonly → `res.users`
- `invoice_incoterm_id` **(many2one)** — Incoterm → `account.incoterms`
  > International Commercial Terms are a series of predefined commercial terms used in international transactions.
- `invoice_cash_rounding_id` **(many2one)** — Cash Rounding Method → `account.cash.rounding`
  > Defines the smallest coinage of the currency that can be used to pay by cash.
- `invoice_pdf_report_id` **(many2one)** — PDF Attachment 🔒 readonly → `ir.attachment`
- `bank_partner_id` **(many2one)** — Bank Partner 🔒 readonly → `res.partner`
  > Technical field to get the domain on the bank
- `tax_country_id` **(many2one)** — Tax Country 🔒 readonly → `res.country`
- `duplicated_ref_ids` **(many2many)** — Duplicated Ref 🔒 readonly → `account.move`
- `payment_ids` **(one2many)** — Payments → `account.payment`
- `statement_line_ids` **(one2many)** — Statements → `account.bank.statement.line`
- `deferred_move_ids` **(many2many)** — Deferred Entries → `account.move`
  > The deferred entries created by this invoice
- `deferred_original_move_ids` **(many2many)** — Original Invoices → `account.move`
  > The original invoices that created the deferred entries
- `signing_user` **(many2one)** — Signer 🔒 readonly → `res.users`
- `debit_origin_id` **(many2one)** — Original Invoice Debited 🔒 readonly → `account.move`
- `debit_note_ids` **(one2many)** — Debit Notes → `account.move`
  > The debit notes created for this invoice
- `ubl_cii_xml_id` **(many2one)** — Attachment 🔒 readonly → `ir.attachment`
- `transaction_ids` **(many2many)** — Transactions 🔒 readonly → `payment.transaction`
- `authorized_transaction_ids` **(many2many)** — Authorized Transactions 🔒 readonly → `payment.transaction`
- `expense_ids` **(one2many)** — Expense → `hr.expense`
- `purchase_vendor_bill_id` **(many2one)** — Auto-complete → `purchase.bill.union`
  > Auto-complete from a previous bill, refund, or purchase order.
- `purchase_id` **(many2one)** — Purchase Order → `purchase.order`
  > Auto-complete from a past purchase order.
- `stock_move_ids` **(one2many)** — Stock Move → `stock.move`
- `closing_return_id` **(many2one)** — Closing Return → `account.return`
- `calendar_booking_ids` **(one2many)** — Meeting Booking → `calendar.booking`
- `l10n_latam_available_document_type_ids` **(many2many)** — L10N Latam Available Document Type 🔒 readonly → `l10n_latam.document.type`
- `l10n_latam_document_type_id` **(many2one)** — Document Type → `l10n_latam.document.type`
- `wip_production_ids` **(many2many)** — Relevant WIP MOs → `mrp.production`
  > The MOs that this WIP entry was based on. Expected to be set at time of WIP entry creation.
- `team_id` **(many2one)** — Sales Team → `crm.team`
- `suspense_statement_line_id` **(many2one)** — Request document from a bank statement line → `account.bank.statement.line`
- `asset_id` **(many2one)** — Asset → `account.asset`
- `asset_ids` **(one2many)** — Assets 🔒 readonly → `account.asset`
- `extract_attachment_id` **(many2one)** — Extract Attachment 🔒 readonly → `ir.attachment`
- `website_id` **(many2one)** — Website 🔒 readonly → `website`
  > Website through which this invoice was created for eCommerce orders.
- `generating_loan_line_id` **(many2one)** — Generating Loan Line 🔒 readonly → `account.loan.line`
  > Line of the loan that generated this entry
- `loan_id` **(many2one)** — Loan 🔒 readonly → `account.loan`
- `l10n_br_edi_transporter_id` **(many2one)** — Transporter Brazil → `res.partner`
  > Brazil: if you use a transport company, add its company contact here.
- `l10n_br_edi_xml_attachment_id` **(many2one)** — Brazil E-Invoice XML 🔒 readonly → `ir.attachment`
  > Brazil: the most recent e-invoice XML returned by Avalara.
- `l10n_br_related_package_ids` **(many2many)** — Related Packages 🔒 readonly → `stock.package`
- `l10n_br_package_ids` **(one2many)** — Packages → `stock.package`
  > Brazil: packages to include in the NF-e used on the deliveries linked to this sales transaction.
- `timesheet_ids` **(one2many)** — Timesheets 🔒 readonly → `account.analytic.line`
- `timesheet_encode_uom_id` **(many2one)** — Timesheet Encoding Unit 🔒 readonly → `uom.uom`

## Campos Calculados (readonly)

- `is_tax_computed_externally` **(boolean)** — Is Tax Computed Externally 🔒 readonly
  > Technical field to determine if tax is calculated using an external service instead of Odoo.
- `l10n_br_is_service_transaction` **(boolean)** — Is Service Transaction 🔒 readonly
  > Technical field used to determine if this transaction should be sent to the service or goods API.
- `l10n_br_is_avatax` **(boolean)** — Is Brazilian Avatax 🔒 readonly
  > Technical field used to check if this record requires tax calculation or EDI via Avatax.
- `l10n_br_avatax_warnings` **(json)** — L10N Br Avatax Warnings 🔒 readonly
- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `name_placeholder` **(char)** — Name Placeholder 🔒 readonly
- `is_storno` **(boolean)** — Is Storno 🔒 readonly
- `payment_count` **(integer)** — Payment Count 🔒 readonly
- `adjusting_entry_origin_label` **(char)** — Adjusting Entry Origin Label 🔒 readonly
- `adjusting_entry_origin_moves_count` **(integer)** — Adjusting Entry Origin Moves Count 🔒 readonly
- `adjusting_entries_count` **(integer)** — Adjusting Entries Count 🔒 readonly
- `hide_post_button` **(boolean)** — Hide Post Button 🔒 readonly
- `highest_name` **(char)** — Highest Name 🔒 readonly
- `type_name` **(char)** — Type Name 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `account_fiscal_country_group_codes` **(json)** — Account Fiscal Country Group Codes 🔒 readonly
- `company_price_include` **(selection)** — Default Sales Price Include 🔒 readonly
  > Default on whether the sales price used on the product and invoices with this Company includes its taxes.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `restrict_mode_hash_table` **(boolean)** — Secure Posted Entries with Hash 🔒 readonly
  > If ticked, when an entry is posted, we retroactively hash all moves in the sequence from the entry back to the last hashed entry. The hash can also be performed on demand by the Secure Entries wizard.
- `secured` **(boolean)** — Secured 🔒 readonly
  > The entry is secured with an inalterable hash.
- `show_delivery_date` **(boolean)** — Show Delivery Date 🔒 readonly
- `show_taxable_supply_date` **(boolean)** — Show Taxable Supply Date 🔒 readonly
- `taxable_supply_date_placeholder` **(char)** — Taxable Supply Date Placeholder 🔒 readonly
- `needed_terms` **(binary)** — Needed Terms 🔒 readonly
- `needed_terms_dirty` **(boolean)** — Needed Terms Dirty 🔒 readonly
- `tax_calculation_rounding_method` **(selection)** — Tax calculation rounding method 🔒 readonly
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `show_journal` **(boolean)** — Show Journal 🔒 readonly
- `display_qr_code` **(boolean)** — Display QR-code 🔒 readonly
- `display_link_qr_code` **(boolean)** — Display Link QR-code 🔒 readonly
- `expected_currency_rate` **(float)** — Expected Currency Rate 🔒 readonly
- `direction_sign` **(integer)** — Direction Sign 🔒 readonly
  > Multiplicator depending on the document type, to convert a price into a balance
- `status_in_payment` **(selection)** — Status In Payment 🔒 readonly
  > Opções: `not_paid` (Not Paid), `in_payment` (In Payment), `paid` (Paid), `partial` (Partially Paid), `reversed` (Reversed), `blocked` (Blocked), `invoicing_legacy` (Invoicing App Legacy), `draft` (Draft), `posted` (Posted), `sent` (Sent), `cancel` (Cancelled)
- `amount_total_words` **(char)** — Amount total in words 🔒 readonly
- `quick_edit_mode` **(boolean)** — Quick Edit Mode 🔒 readonly
- `quick_encoding_vals` **(json)** — Quick Encoding Vals 🔒 readonly
- `is_being_sent` **(boolean)** — Is Being Sent 🔒 readonly
  > Is the move being sent asynchronously
- `move_sent_values` **(selection)** — Sent 🔒 readonly
  > Opções: `sent` (Sent), `not_sent` (Not Sent)
- `invoice_incoterm_placeholder` **(char)** — Invoice Incoterm Placeholder 🔒 readonly
- `invoice_filter_type_domain` **(char)** — Invoice Filter Type Domain 🔒 readonly
- `tax_lock_date_message` **(char)** — Tax Lock Date Message 🔒 readonly
- `display_inactive_currency_warning` **(boolean)** — Display Inactive Currency Warning 🔒 readonly
- `tax_country_code` **(char)** — Tax Country Code 🔒 readonly
- `has_reconciled_entries` **(boolean)** — Has Reconciled Entries 🔒 readonly
- `show_reset_to_draft_button` **(boolean)** — Show Reset To Draft Button 🔒 readonly
- `is_draft_duplicated_ref_ids` **(boolean)** — Is Draft Duplicated Ref 🔒 readonly
- `is_exact_move_duplicate` **(boolean)** — Is Exact Move Duplicate 🔒 readonly
- `need_cancel_request` **(boolean)** — Need Cancel Request 🔒 readonly
- `payment_term_details` **(binary)** — Payment Term Details 🔒 readonly
- `show_payment_term_details` **(boolean)** — Show Payment Term Details 🔒 readonly
- `show_discount_details` **(boolean)** — Show Discount Details 🔒 readonly
- `abnormal_amount_warning` **(text)** — Abnormal Amount Warning 🔒 readonly
- `abnormal_date_warning` **(text)** — Abnormal Date Warning 🔒 readonly
- `alerts` **(json)** — Alerts 🔒 readonly
- `taxes_legal_notes` **(html)** — Taxes Legal Notes 🔒 readonly
- `next_payment_date` **(date)** — Next Payment Date 🔒 readonly
- `display_send_button` **(boolean)** — Display Send Button 🔒 readonly
- `highlight_send_button` **(boolean)** — Highlight Send Button 🔒 readonly
- `is_sale_installed` **(boolean)** — Is Sale Installed 🔒 readonly
- `deferred_entry_type` **(selection)** — Deferred Entry Type 🔒 readonly
  > Opções: `expense` (Deferred Expense), `revenue` (Deferred Revenue), `misc` (Deferred Miscellaneous)
- `show_signature_area` **(boolean)** — Show Signature Area 🔒 readonly
- `signature` **(binary)** — Signature 🔒 readonly
- `debit_note_count` **(integer)** — Number of Debit Notes 🔒 readonly
- `ubl_cii_xml_filename` **(char)** — UBL/CII Filename 🔒 readonly
- `transaction_count` **(integer)** — Transaction Count 🔒 readonly
- `amount_paid` **(monetary)** — Amount paid 🔒 readonly
- `nb_expenses` **(integer)** — Number of Expenses 🔒 readonly
- `purchase_order_count` **(integer)** — Purchase Order Count 🔒 readonly
- `purchase_order_name` **(char)** — Purchase Order Name 🔒 readonly
- `is_purchase_matched` **(boolean)** — Is Purchase Matched 🔒 readonly
- `purchase_warning_text` **(text)** — Purchase Warning 🔒 readonly
  > Internal warning for the partner or the products as set by the user.
- `l10n_latam_use_documents` **(boolean)** — L10N Latam Use Documents 🔒 readonly
- `l10n_latam_manual_document_number` **(boolean)** — Manual Number 🔒 readonly
- `l10n_latam_document_type_id_code` **(char)** — Doc Type 🔒 readonly
  > Code used by different localizations
- `wip_production_count` **(integer)** — Manufacturing Orders Count 🔒 readonly
- `sale_order_count` **(integer)** — Sale Order Count 🔒 readonly
- `sale_warning_text` **(text)** — Sale Warning 🔒 readonly
  > Internal warning for the partner or the products as set by the user.
- `has_documents` **(boolean)** — Has Documents 🔒 readonly
- `asset_remaining_value` **(monetary)** — Depreciable Value 🔒 readonly
- `asset_depreciated_value` **(monetary)** — Cumulative Depreciation 🔒 readonly
- `asset_id_display_name` **(char)** — Asset Id Display Name 🔒 readonly
- `count_asset` **(integer)** — Count Asset 🔒 readonly
- `draft_asset_exists` **(boolean)** — Draft Asset Exists 🔒 readonly
- `extract_error_message` **(text)** — Error message 🔒 readonly
- `extract_can_show_send_button` **(boolean)** — Can show the ocr send button 🔒 readonly
- `extract_can_show_banners` **(boolean)** — Can show the ocr banners 🔒 readonly
- `l10n_br_edi_is_needed` **(boolean)** — L10N Br Edi Is Needed 🔒 readonly
  > Brazil: technical field to determine if this invoice is eligible to be e-invoiced.
- `l10n_br_picking_count` **(integer)** — L10N Br Picking Count 🔒 readonly
- `timesheet_count` **(integer)** — Number of timesheets 🔒 readonly
- `timesheet_total_duration` **(integer)** — Timesheet Total Duration 🔒 readonly
  > Total recorded duration, expressed in the encoding UoM, and rounded to the unit

## Campos de Auditoria

- `audit_trail_message_ids` **(one2many)** — Audit Trail Messages → `mail.message`
