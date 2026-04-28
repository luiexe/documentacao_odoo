# Sales Order — `sale.order`

**Ordenação padrão:** `date_order desc, id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Order Reference ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `partner_id` **(many2one)** — Customer ⚠️ obrigatório → `res.partner`
- `date_order` **(datetime)** — Order Date ⚠️ obrigatório
  > Creation date of draft/sent orders, Confirmation date of confirmed orders.
- `partner_invoice_id` **(many2one)** — Invoice Address ⚠️ obrigatório → `res.partner`
- `partner_shipping_id` **(many2one)** — Delivery Address ⚠️ obrigatório → `res.partner`
- `picking_policy` **(selection)** — Shipping Policy ⚠️ obrigatório
  > If you deliver all products at once, the delivery order will be scheduled based on the greatest product lead time. Otherwise, it will be based on the shortest.
  > Opções: `direct` (As soon as possible), `one` (When all products are ready)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `access_token` **(char)** — Security Token
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
- `locked` **(boolean)** — Locked
  > Locked orders cannot be modified.
- `client_order_ref` **(char)** — Customer Reference
- `create_date` **(datetime)** — Creation Date 🔒 readonly
- `commitment_date` **(datetime)** — Delivery Date
  > This is the delivery date promised to the customer. If set, the delivery order will be scheduled based on this date rather than product lead times.
- `origin` **(char)** — Source Document
  > Reference of the document that generated this sales order request
- `reference` **(char)** — Payment Ref.
  > The payment communication of this sale order.
- `require_signature` **(boolean)** — Online signature
  > Request a online signature from the customer to confirm the order.
- `require_payment` **(boolean)** — Online payment
  > Request a online payment from the customer to confirm the order.
- `prepayment_percent` **(float)** — Prepayment percentage
  > The percentage of the amount needed that must be paid by the customer to confirm the order.
- `signature` **(binary)** — Signature
- `signed_by` **(char)** — Signed By
- `signed_on` **(datetime)** — Signed On
- `validity_date` **(date)** — Expiration
  > Validity of the order, after that you will not able to sign & pay the quotation.
- `note` **(html)** — Terms and conditions
- `currency_rate` **(float)** — Currency Rate 🔒 readonly
- `amount_untaxed` **(monetary)** — Untaxed Amount 🔒 readonly
- `amount_tax` **(monetary)** — Taxes 🔒 readonly
- `amount_total` **(monetary)** — Total 🔒 readonly
- `invoice_status` **(selection)** — Invoice Status 🔒 readonly
  > Opções: `upselling` (Upselling Opportunity), `invoiced` (Fully Invoiced), `to invoice` (To Invoice), `no` (Nothing to Invoice)
- `show_update_fpos` **(boolean)** — Has Fiscal Position Changed
- `show_update_pricelist` **(boolean)** — Has Pricelist Changed
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `pickup_location_data` **(json)** — Pickup Location Data
- `delivery_message` **(char)** — Delivery Message 🔒 readonly
- `recompute_delivery_price` **(boolean)** — Delivery cost should be recomputed
- `shipping_weight` **(float)** — Shipping Weight
- `l10n_br_use_type` **(selection)** — Purpose of Use
  > Brazil: this will override the purpose of use for all products sold here.
  > Opções: `use or consumption` (Use or consumption), `resale` (Resale), `agricultural production` (Agricultural production), `production` (Production), `fixed assets` (Fixed assets), `notApplicable` (Not applicable)
- `l10n_br_presence` **(selection)** — Presence
  > Brazil: Defines if the buyer was physically present during the transaction, affecting tax calculation and location.
  > Opções: `0` (Not applicable), `1` (Present), `2` (Remote, internet), `3` (Remote, phone), `4` (NFC-e home delivery), `5` (In-person operation, for establishment (v3)), `9` (Remote, others)
- `incoterm_location` **(char)** — Incoterm Location
- `delivery_status` **(selection)** — Delivery Status 🔒 readonly
  > Blue: Not Delivered/Started             Orange: Partially Delivered             Green: Fully Delivered
  > Opções: `pending` (Not Delivered), `started` (Started), `partial` (Partially Delivered), `full` (Fully Delivered)
- `effective_date` **(datetime)** — Effective Date 🔒 readonly
  > Completion date of the first delivery order.
- `margin` **(monetary)** — Margin 🔒 readonly
- `margin_percent` **(float)** — Margin (%) 🔒 readonly
- `customizable_pdf_form_fields` **(json)** — Customizable PDF Form Fields
- `cart_recovery_email_sent` **(boolean)** — Cart recovery email already sent
- `shop_warning` **(char)** — Warning
- `l10n_br_edi_freight_model` **(selection)** — Freight Model
  > Brazil: Used to determine the freight model used on this transaction.
  > Opções: `CIF` (Freight contracting on behalf of the Sender (CIF)), `FOB` (Contracting of freight on behalf of the recipient/sender (FOB)), `Thirdparty` (Contracting Freight on behalf of third parties), `SenderVehicle` (Own transport on behalf of the sender), `ReceiverVehicle` (Own transport on behalf of the recipient), `FreeShipping` (Free shipping)
- `l10n_br_edi_payment_method` **(selection)** — Payment Method Brazil
  > Brazil: Expected payment method to be used.
  > Opções: `01` (Money), `02` (Check), `03` (Credit Card), `04` (Debit Card), `05` (Store Credit), `10` (Food voucher), `11` (Meal Voucher), `12` (Gift certificate), `13` (Fuel Voucher), `14` (Duplicate Mercantil), `15` (Boleto Bancario), `16` (Bank Deposit), `17` (Instant Payment (PIX)), `18` (Bank transfer, Digital Wallet), `19` (Loyalty program, Cashback, Virtual Credit), `90` (No Payment), `99` (Others)

## Relacionamentos

- `campaign_id` **(many2one)** — Campaign → `utm.campaign`
  > This is a name that helps you keep track of your different campaign efforts, e.g. Fall_Drive, Christmas_Special
- `source_id` **(many2one)** — Source → `utm.source`
  > This is the source of the link, e.g. Search Engine, another domain, or name of email list
- `medium_id` **(many2one)** — Medium → `utm.medium`
  > This is the method of delivery, e.g. Postcard, Email, or Banner Ad
- `pending_email_template_id` **(many2one)** — Pending Email Template 🔒 readonly → `mail.template`
- `journal_id` **(many2one)** — Invoicing Journal → `account.journal`
  > If set, the SO will invoice in this journal; otherwise the sales journal with the lowest sequence is used.
- `fiscal_position_id` **(many2one)** — Fiscal Position → `account.fiscal.position`
  > Fiscal positions are used to adapt taxes and accounts for particular customers or sales orders/invoices.The default value comes from the customer.
- `payment_term_id` **(many2one)** — Payment Terms → `account.payment.term`
- `preferred_payment_method_line_id` **(many2one)** — Payment Method → `account.payment.method.line`
- `pricelist_id` **(many2one)** — Pricelist → `product.pricelist`
  > If you change the pricelist, only newly added lines will be affected.
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `user_id` **(many2one)** — Salesperson → `res.users`
- `team_id` **(many2one)** — Sales Team → `crm.team`
- `order_line` **(one2many)** — Order Lines → `sale.order.line`
- `invoice_ids` **(many2many)** — Invoices 🔒 readonly → `account.move`
- `tag_ids` **(many2many)** — Tags → `crm.tag`
- `duplicated_order_ids` **(many2many)** — Duplicated Order 🔒 readonly → `sale.order`
- `tax_country_id` **(many2one)** — Tax Country 🔒 readonly → `res.country`
- `carrier_id` **(many2one)** — Delivery Method → `delivery.carrier`
  > Fill this field if you plan to invoice the shipping based on picking.
- `opportunity_id` **(many2one)** — Opportunity → `crm.lead`
- `l10n_br_cnae_code_id` **(many2one)** — CNAE Code → `l10n_br.cnae.code`
  > Brazil: the company's CNAE code for tax calculation and EDI.
- `l10n_br_goods_operation_type_id` **(many2one)** — Goods Operation Type → `l10n_br.operation.type`
  > Brazil: this is the operation type related to the goods transaction. This will be used as a default on transaction lines.
- `applied_coupon_ids` **(many2many)** — Manually Applied Coupons → `loyalty.card`
- `code_enabled_rule_ids` **(many2many)** — Manually Triggered Rules → `loyalty.rule`
- `coupon_point_ids` **(one2many)** — Coupon Point → `sale.order.coupon.points`
- `sale_order_template_id` **(many2one)** — Quotation Template → `sale.order.template`
- `incoterm` **(many2one)** — Incoterm → `account.incoterms`
  > International Commercial Terms are a series of predefined commercial terms used in international transactions.
- `warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`
- `picking_ids` **(one2many)** — Transfers → `stock.picking`
- `stock_reference_ids` **(many2many)** — References → `stock.reference`
- `expense_ids` **(one2many)** — Expenses 🔒 readonly → `hr.expense`
- `mrp_production_ids` **(many2many)** — Manufacturing orders associated with this sales order. 🔒 readonly → `mrp.production`
- `available_quotation_document_ids` **(many2many)** — Available Quotation Documents 🔒 readonly → `quotation.document`
- `quotation_document_ids` **(many2many)** — Headers/Footers → `quotation.document`
- `spreadsheet_template_id` **(many2one)** — Quote calculator 🔒 readonly → `sale.order.spreadsheet`
- `spreadsheet_ids` **(one2many)** — Spreadsheets → `sale.order.spreadsheet`
- `spreadsheet_id` **(many2one)** — Spreadsheet 🔒 readonly → `sale.order.spreadsheet`
- `website_id` **(many2one)** — Website 🔒 readonly → `website`
  > Website through which this order was placed for eCommerce orders.
- `website_order_line` **(one2many)** — Order Lines displayed on Website 🔒 readonly → `sale.order.line`
- `planning_first_sale_line_id` **(many2one)** — Planning First Sale Line 🔒 readonly → `sale.order.line`
- `tasks_ids` **(many2many)** — Tasks associated with this sale 🔒 readonly → `project.task`
- `project_ids` **(many2many)** — Projects 🔒 readonly → `project.project`
- `project_id` **(many2one)** — Project → `project.project`
  > A task will be created for the project upon sales order confirmation. The analytic distribution of this project will also serve as a reference for newly created sales order items.
- `project_account_id` **(many2one)** — Project Account 🔒 readonly → `account.analytic.account`
- `disabled_auto_rewards` **(many2many)** — Disabled Auto Rewards → `loyalty.reward`
- `l10n_br_edi_transporter_id` **(many2one)** — Transporter Brazil → `res.partner`
  > Brazil: If you use a transport company, add its company contact here.
- `timesheet_encode_uom_id` **(many2one)** — Timesheet Encoding Unit 🔒 readonly → `uom.uom`

## Campos Calculados (readonly)

- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `has_archived_products` **(boolean)** — Has Archived Products 🔒 readonly
- `amount_to_invoice` **(monetary)** — Un-invoiced Balance 🔒 readonly
- `amount_invoiced` **(monetary)** — Already invoiced 🔒 readonly
- `invoice_count` **(integer)** — Invoice Count 🔒 readonly
- `sale_warning_text` **(text)** — Sale Warning 🔒 readonly
  > Internal warning for the partner or the products as set by the user.
- `has_authorized_transaction_ids` **(boolean)** — Has Authorized Transactions 🔒 readonly
- `amount_paid` **(float)** — Payment Transactions Amount 🔒 readonly
  > Sum of transactions made in through the online payment form that are in the state 'done' or 'authorized' and linked to this order.
- `amount_undiscounted` **(float)** — Amount Before Discount 🔒 readonly
- `country_code` **(char)** — Country code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `company_price_include` **(selection)** — Default Sales Price Include 🔒 readonly
  > Default on whether the sales price used on the product and invoices with this Company includes its taxes.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `expected_date` **(datetime)** — Expected Date 🔒 readonly
  > Delivery date you can promise to the customer, computed from the minimum lead time of the order lines in case of Service products. In case of shipping, the shipping policy of the order will be taken into account to either use the minimum or maximum lead time of the order lines.
- `is_expired` **(boolean)** — Is Expired 🔒 readonly
- `partner_credit_warning` **(text)** — Partner Credit Warning 🔒 readonly
- `tax_calculation_rounding_method` **(selection)** — Tax Calculation Rounding Method 🔒 readonly
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `tax_totals` **(binary)** — Tax Totals 🔒 readonly
- `terms_type` **(selection)** — Terms & Conditions format 🔒 readonly
  > Opções: `plain` (Add a Note), `html` (Add a link to a Web Page)
- `type_name` **(char)** — Type Name 🔒 readonly
- `has_active_pricelist` **(boolean)** — Has Active Pricelist 🔒 readonly
- `delivery_set` **(boolean)** — Delivery Set 🔒 readonly
- `is_all_service` **(boolean)** — Service Product 🔒 readonly
- `is_tax_computed_externally` **(boolean)** — Is Tax Computed Externally 🔒 readonly
  > Technical field to determine if tax is calculated using an external service instead of Odoo.
- `l10n_br_is_service_transaction` **(boolean)** — Is Service Transaction 🔒 readonly
  > Technical field used to determine if this transaction should be sent to the service or goods API.
- `l10n_br_is_avatax` **(boolean)** — Is Brazilian Avatax 🔒 readonly
  > Technical field used to check if this record requires tax calculation or EDI via Avatax.
- `l10n_br_avatax_warnings` **(json)** — L10N Br Avatax Warnings 🔒 readonly
- `reward_amount` **(float)** — Reward Amount 🔒 readonly
- `gift_card_count` **(integer)** — Gift Card Count 🔒 readonly
- `loyalty_data` **(json)** — Loyalty Data 🔒 readonly
- `purchase_order_count` **(integer)** — Number of Purchase Order Generated 🔒 readonly
- `delivery_count` **(integer)** — Delivery Orders 🔒 readonly
- `late_availability` **(boolean)** — Late Availability 🔒 readonly
  > True if any related picking has late availability
- `json_popover` **(char)** — JSON data for the popover widget 🔒 readonly
- `show_json_popover` **(boolean)** — Has late picking 🔒 readonly
- `expense_count` **(integer)** — # of Expenses 🔒 readonly
- `mrp_production_count` **(integer)** — Count of MO generated 🔒 readonly
- `is_pdf_quote_builder_available` **(boolean)** — Is Pdf Quote Builder Available 🔒 readonly
- `amount_delivery` **(monetary)** — Delivery Amount 🔒 readonly
  > Tax included or excluded depending on the website configuration.
- `cart_quantity` **(integer)** — Cart Quantity 🔒 readonly
- `only_services` **(boolean)** — Only Services 🔒 readonly
- `is_abandoned_cart` **(boolean)** — Abandoned Cart 🔒 readonly
- `planning_hours_planned` **(float)** — Planning Hours Planned 🔒 readonly
- `planning_hours_to_plan` **(float)** — Planning Hours To Plan 🔒 readonly
- `planning_initial_date` **(date)** — Planning Initial Date 🔒 readonly
- `tasks_count` **(integer)** — Tasks 🔒 readonly
- `visible_project` **(boolean)** — Display project 🔒 readonly
- `project_count` **(integer)** — Number of Projects 🔒 readonly
- `milestone_count` **(integer)** — Milestone Count 🔒 readonly
- `is_product_milestone` **(boolean)** — Is Product Milestone 🔒 readonly
- `show_create_project_button` **(boolean)** — Show Create Project Button 🔒 readonly
- `show_project_button` **(boolean)** — Show Project Button 🔒 readonly
- `closed_task_count` **(integer)** — Closed Task Count 🔒 readonly
- `completed_task_percentage` **(float)** — Completed Task Percentage 🔒 readonly
- `calendar_event_count` **(integer)** — Meetings 🔒 readonly
- `timesheet_count` **(float)** — Timesheet activities 🔒 readonly
- `timesheet_total_duration` **(integer)** — Timesheet Total Duration 🔒 readonly
  > Total recorded duration, expressed in the encoding UoM, and rounded to the unit
- `show_hours_recorded_button` **(boolean)** — Show Hours Recorded Button 🔒 readonly
