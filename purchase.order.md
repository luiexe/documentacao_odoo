# Purchase Order — `purchase.order`

**Ordenação padrão:** `priority desc, id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Order Reference ⚠️ obrigatório
- `date_order` **(datetime)** — Order Deadline ⚠️ obrigatório
  > Depicts the date within which the Quotation should be confirmed and converted into a purchase order.
- `partner_id` **(many2one)** — Vendor ⚠️ obrigatório → `res.partner`
  > You can find a vendor by its Name, TIN, Email or Internal Reference.
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `picking_type_id` **(many2one)** — Deliver To ⚠️ obrigatório → `stock.picking.type`
  > This will determine operation type of incoming shipment

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `access_token` **(char)** — Security Token
- `priority` **(selection)** — Priority
  > Opções: `0` (Normal), `1` (Urgent)
- `origin` **(char)** — Source
  > Reference of the document that generated this purchase order request (e.g. a sales order)
- `partner_ref` **(char)** — Vendor Reference
  > Reference of the sales order or bid sent by the vendor. It's used to do the matching when you receive the products as this reference is usually written on the delivery order sent by your vendor.
- `date_approve` **(datetime)** — Confirmation Date 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (RFQ), `sent` (RFQ Sent), `to approve` (To Approve), `purchase` (Purchase Order), `cancel` (Cancelled)
- `locked` **(boolean)** — Locked
  > Locked Purchase Orders cannot be modified.
- `acknowledged` **(boolean)** — Acknowledged
  > It indicates that the vendor has acknowledged the receipt of the purchase order.
- `note` **(html)** — Terms and Conditions
- `invoice_count` **(integer)** — Bill Count 🔒 readonly
- `invoice_status` **(selection)** — Billing Status 🔒 readonly
  > Opções: `no` (Nothing to Bill), `to invoice` (Waiting Bills), `invoiced` (Fully Billed)
- `date_planned` **(datetime)** — Expected Arrival
  > Delivery date promised by vendor. This date is used to determine expected arrival of products.
- `date_calendar_start` **(datetime)** — Date Calendar Start 🔒 readonly
- `amount_untaxed` **(monetary)** — Untaxed Amount 🔒 readonly
- `amount_tax` **(monetary)** — Taxes 🔒 readonly
- `amount_total` **(monetary)** — Total 🔒 readonly
- `amount_total_cc` **(monetary)** — Total in currency 🔒 readonly
- `currency_rate` **(float)** — Currency Rate 🔒 readonly
- `receipt_reminder_email` **(boolean)** — Receipt Reminder Email
- `reminder_date_before_receipt` **(integer)** — Days Before Receipt
- `is_late` **(boolean)** — Is Late
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `incoterm_location` **(char)** — Incoterm Location
- `effective_date` **(datetime)** — Arrival 🔒 readonly
  > Completion date of the first receipt order.
- `receipt_status` **(selection)** — Receipt Status 🔒 readonly
  > Red: Late             Orange: To process today             Green: On time
  > Opções: `pending` (Not Received), `partial` (Partially Received), `full` (Fully Received)
- `date_planned_mps` **(datetime)** — Scheduled Date 🔒 readonly

## Relacionamentos

- `dest_address_id` **(many2one)** — Dropship Address → `res.partner`
  > Put an address if you want to deliver directly from the vendor to the customer. Otherwise, keep empty to deliver to your own company.
- `order_line` **(one2many)** — Order Lines → `purchase.order.line`
- `invoice_ids` **(many2many)** — Bills 🔒 readonly → `account.move`
- `fiscal_position_id` **(many2one)** — Fiscal Position → `account.fiscal.position`
- `tax_country_id` **(many2one)** — Tax Country 🔒 readonly → `res.country`
  > Technical field to filter the available taxes depending on the fiscal country and fiscal position.
- `payment_term_id` **(many2one)** — Payment Terms → `account.payment.term`
- `incoterm_id` **(many2one)** — Incoterm → `account.incoterms`
  > International Commercial Terms are a series of predefined commercial terms used in international transactions.
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `user_id` **(many2one)** — Buyer → `res.users`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `duplicated_order_ids` **(many2many)** — Duplicated Order 🔒 readonly → `purchase.order`
- `project_id` **(many2one)** — Project → `project.project`
- `picking_ids` **(many2many)** — Receptions 🔒 readonly → `stock.picking`
- `reference_ids` **(many2many)** — References → `stock.reference`

## Campos Calculados (readonly)

- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `lock_confirmed_po` **(selection)** — Purchase Order Modification 🔒 readonly
  > Purchase Order Modification used when you want to purchase order editable after confirm
  > Opções: `edit` (Allow to edit purchase orders), `lock` (Confirmed purchase orders are not editable)
- `partner_bill_count` **(integer)** — # Vendor Bills 🔒 readonly
- `tax_totals` **(binary)** — Tax Totals 🔒 readonly
- `tax_calculation_rounding_method` **(selection)** — Tax calculation rounding method 🔒 readonly
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `country_code` **(char)** — Country code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `company_price_include` **(selection)** — Default Sales Price Include 🔒 readonly
  > Default on whether the sales price used on the product and invoices with this Company includes its taxes.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `show_comparison` **(boolean)** — Show Comparison 🔒 readonly
- `purchase_warning_text` **(text)** — Purchase Warning 🔒 readonly
  > Internal warning for the partner or the products as set by the user.
- `incoming_picking_count` **(integer)** — Incoming Shipment count 🔒 readonly
- `default_location_dest_id_usage` **(selection)** — Destination Location Type 🔒 readonly
  > Technical field used to display the Drop Ship Address
  > Opções: `supplier` (Vendor), `view` (Virtual), `internal` (Internal), `customer` (Customer), `inventory` (Inventory Loss), `production` (Production), `transit` (Transit)
- `is_shipped` **(boolean)** — Is Shipped 🔒 readonly
- `on_time_rate` **(float)** — On-Time Delivery Rate 🔒 readonly
  > Over the past x days; the number of products received on time divided by the number of ordered products.x is either the System Parameter purchase_stock.on_time_delivery_days or the default 365
- `mrp_production_count` **(integer)** — Count of MO Source 🔒 readonly
- `sale_order_count` **(integer)** — Number of Source Sale 🔒 readonly
- `has_sale_order` **(boolean)** — Technical field for whether the purchase order has associated sale orders 🔒 readonly
- `subcontracting_resupply_picking_count` **(integer)** — Count of Subcontracting Resupply 🔒 readonly
  > Count of Subcontracting Resupply for component
- `is_above_budget` **(boolean)** — Is Above Budget 🔒 readonly
- `is_analytic` **(boolean)** — Is Analytic 🔒 readonly
