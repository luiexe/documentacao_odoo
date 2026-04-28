# Sales Order Line — `sale.order.line`

**Ordenação padrão:** `order_id, sequence, id`

---

## Campos Obrigatórios

- `order_id` **(many2one)** — Order Reference ⚠️ obrigatório → `sale.order`
- `name` **(text)** — Description ⚠️ obrigatório
- `product_uom_qty` **(float)** — Quantity ⚠️ obrigatório
- `price_unit` **(float)** — Unit Price ⚠️ obrigatório
- `customer_lead` **(float)** — Lead Time ⚠️ obrigatório
  > Number of days between the order confirmation and the shipping of the products to the customer

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `sequence` **(integer)** — Sequence
- `state` **(selection)** — Order Status 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
- `display_type` **(selection)** — Display Type
  > Opções: `line_section` (Section), `line_subsection` (Subsection), `line_note` (Note)
- `is_downpayment` **(boolean)** — Is a down payment
  > Down payments are made when creating invoices from a sales order. They are not copied when duplicating a sales order.
- `is_expense` **(boolean)** — Is expense
  > Is true if the sales order line comes from an expense or a vendor bills
- `virtual_id` **(char)** — Virtual
- `linked_virtual_id` **(char)** — Linked Virtual
- `selected_combo_items` **(char)** — Selected Combo Items
- `technical_price_unit` **(float)** — Technical Price Unit
- `discount` **(float)** — Discount (%)
- `price_subtotal` **(monetary)** — Subtotal 🔒 readonly
- `price_tax` **(float)** — Total Tax 🔒 readonly
- `price_total` **(monetary)** — Total 🔒 readonly
- `price_reduce_taxexcl` **(monetary)** — Price Reduce Tax excl 🔒 readonly
- `price_reduce_taxinc` **(monetary)** — Price Reduce Tax incl 🔒 readonly
- `qty_delivered_method` **(selection)** — Method to update delivered qty 🔒 readonly
  > According to product configuration, the delivered quantity can be automatically computed by mechanism:   - Manual: the quantity is set manually on the line   - Analytic From expenses: the quantity is the quantity sum from posted expenses   - Timesheet: the quantity is the sum of hours recorded on tasks linked to this sale line   - Stock Moves: the quantity comes from confirmed pickings 
  > Opções: `manual` (Manual), `analytic` (Analytic From Expenses), `stock_move` (Stock Moves), `milestones` (Milestones), `timesheet` (Timesheets)
- `qty_delivered` **(float)** — Delivery Quantity
- `qty_invoiced` **(float)** — Invoiced Quantity 🔒 readonly
- `qty_to_invoice` **(float)** — Quantity To Invoice 🔒 readonly
- `invoice_status` **(selection)** — Invoice Status 🔒 readonly
  > Opções: `upselling` (Upselling Opportunity), `invoiced` (Fully Invoiced), `to invoice` (To Invoice), `no` (Nothing to Invoice)
- `untaxed_amount_invoiced` **(monetary)** — Untaxed Invoiced Amount 🔒 readonly
- `untaxed_amount_to_invoice` **(monetary)** — Untaxed Amount To Invoice 🔒 readonly
- `extra_tax_data` **(json)** — Extra Tax Data
- `collapse_prices` **(boolean)** — Collapse Prices
- `collapse_composition` **(boolean)** — Collapse Composition
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `is_delivery` **(boolean)** — Is a Delivery
- `deferred_revenue` **(boolean)** — Deferred Revenue
- `invoice_to_be_issued` **(boolean)** — Invoice to be Issued
- `reward_identifier_code` **(char)** — Reward Identifier Code
  > Technical field used to link multiple reward lines from the same reward together.
- `points_cost` **(float)** — Points Cost
  > How much point this reward costs on the loyalty card.
- `is_optional` **(boolean)** — Optional Line
- `margin` **(float)** — Margin 🔒 readonly
- `margin_percent` **(float)** — Margin (%) 🔒 readonly
- `purchase_price` **(float)** — Cost
- `is_service` **(boolean)** — Is a Service 🔒 readonly
- `shop_warning` **(char)** — Warning
- `planning_hours_planned` **(float)** — Planning Hours Planned 🔒 readonly
- `planning_hours_to_plan` **(float)** — Planning Hours To Plan 🔒 readonly
- `remaining_hours` **(float)** — Time Remaining on SO 🔒 readonly
- `has_displayed_warning_upsell` **(boolean)** — Has Displayed Warning Upsell

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `order_partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `salesman_id` **(many2one)** — Salesperson 🔒 readonly → `res.users`
- `tax_country_id` **(many2one)** — Tax Country 🔒 readonly → `res.country`
- `product_id` **(many2one)** — Product → `product.product`
- `product_template_id` **(many2one)** — Product Template → `product.template`
- `product_template_attribute_value_ids` **(many2many)** — Attribute Values 🔒 readonly → `product.template.attribute.value`
- `product_custom_attribute_value_ids` **(one2many)** — Custom Values → `product.attribute.custom.value`
- `product_no_variant_attribute_value_ids` **(many2many)** — Extra Values → `product.template.attribute.value`
- `product_uom_id` **(many2one)** — Unit → `uom.uom`
- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `linked_line_id` **(many2one)** — Linked Order Line → `sale.order.line`
- `linked_line_ids` **(one2many)** — Linked Order Lines → `sale.order.line`
- `categ_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `combo_item_id` **(many2one)** — Combo Item → `product.combo.item`
- `tax_ids` **(many2many)** — Taxes → `account.tax`
- `pricelist_item_id` **(many2one)** — Pricelist Item 🔒 readonly → `product.pricelist.item`
- `analytic_line_ids` **(one2many)** — Analytic lines → `account.analytic.line`
- `invoice_lines` **(many2many)** — Invoice Lines → `account.move.line`
- `parent_id` **(many2one)** — Parent Section Line 🔒 readonly → `sale.order.line`
- `reward_id` **(many2one)** — Reward 🔒 readonly → `loyalty.reward`
- `coupon_id` **(many2one)** — Coupon 🔒 readonly → `loyalty.card`
- `purchase_line_ids` **(one2many)** — Generated Purchase Lines 🔒 readonly → `purchase.order.line`
  > Purchase line generated by this Sales item on order confirmation, or when the quantity was increased.
- `route_ids` **(many2many)** — Routes → `stock.route`
- `move_ids` **(one2many)** — Stock Moves → `stock.move`
- `warehouse_id` **(many2one)** — Warehouse 🔒 readonly → `stock.warehouse`
- `expense_ids` **(one2many)** — Expenses 🔒 readonly → `hr.expense`
- `available_product_document_ids` **(many2many)** — Available Product Documents 🔒 readonly → `product.document`
- `product_document_ids` **(many2many)** — Product Documents → `product.document`
  > The product documents for this order line that will be merged in the PDF quote.
- `l10n_br_goods_operation_type_id` **(many2one)** — Override Operation Type → `l10n_br.operation.type`
  > Brazil: If an Operation Type is selected, it will be applied to the product in the line, determining the CFOP for that line. If no selection is made, the operation type will be inherited from the header.
- `expense_id` **(many2one)** — Expense → `hr.expense`
- `planning_slot_ids` **(one2many)** — Planning Slot → `planning.slot`
- `project_id` **(many2one)** — Generated Project → `project.project`
- `task_id` **(many2one)** — Generated Task → `project.task`
- `reached_milestones_ids` **(one2many)** — Reached Milestones → `project.milestone`
- `calendar_booking_ids` **(one2many)** — Bookings → `calendar.booking`
- `calendar_event_id` **(many2one)** — Meeting → `calendar.event`
- `timesheet_ids` **(one2many)** — Timesheets → `account.analytic.line`

## Campos Calculados (readonly)

- `is_configurable_product` **(boolean)** — Is the product configurable? 🔒 readonly
- `is_product_archived` **(boolean)** — Is Product Archived 🔒 readonly
- `translated_product_name` **(text)** — Translated Product Name 🔒 readonly
- `qty_invoiced_posted` **(float)** — Invoiced Quantity (posted) 🔒 readonly
- `amount_invoiced` **(monetary)** — Invoiced Amount 🔒 readonly
- `amount_to_invoice` **(monetary)** — Un-invoiced Balance 🔒 readonly
- `amount_to_invoice_at_date` **(float)** — Amount 🔒 readonly
- `qty_delivered_at_date` **(float)** — Delivered 🔒 readonly
- `qty_invoiced_at_date` **(float)** — Invoiced 🔒 readonly
- `product_type` **(selection)** — Product Type 🔒 readonly
  > Goods are tangible materials and merchandise you provide. A service is a non-material product you provide.
  > Opções: `consu` (Goods), `service` (Service), `combo` (Combo)
- `service_tracking` **(selection)** — Create on Order 🔒 readonly
  > Opções: `no` (Nothing), `task_global_project` (Task), `task_in_project` (Project & Task), `project_only` (Project)
- `product_updatable` **(boolean)** — Can Edit Product 🔒 readonly
- `product_uom_readonly` **(boolean)** — Product Uom Readonly 🔒 readonly
- `tax_calculation_rounding_method` **(selection)** — Tax calculation rounding method 🔒 readonly
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `company_price_include` **(selection)** — Default Sales Price Include 🔒 readonly
  > Default on whether the sales price used on the product and invoices with this Company includes its taxes.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `sale_line_warn_msg` **(text)** — Sale Line Warn Msg 🔒 readonly
- `product_qty` **(float)** — Product Qty 🔒 readonly
- `recompute_delivery_price` **(boolean)** — Delivery cost should be recomputed 🔒 readonly
- `product_invoice_policy` **(selection)** — Invoicing Policy 🔒 readonly
  > Ordered Quantity: Invoice quantities ordered by the customer. Delivered Quantity: Invoice quantities delivered to the customer.
  > Opções: `order` (Ordered quantities), `delivery` (Delivered quantities)
- `is_reward_line` **(boolean)** — Is a program reward line 🔒 readonly
- `purchase_line_count` **(integer)** — Number of generated purchase items 🔒 readonly
- `virtual_available_at_date` **(float)** — Virtual Available At Date 🔒 readonly
- `scheduled_date` **(datetime)** — Scheduled Date 🔒 readonly
- `forecast_expected_date` **(datetime)** — Forecast Expected Date 🔒 readonly
- `free_qty_today` **(float)** — Free Qty Today 🔒 readonly
- `qty_available_today` **(float)** — Qty Available Today 🔒 readonly
- `qty_to_deliver` **(float)** — Qty To Deliver 🔒 readonly
- `is_mto` **(boolean)** — Is Mto 🔒 readonly
- `display_qty_widget` **(boolean)** — Display Qty Widget 🔒 readonly
- `is_storable` **(boolean)** — Track Inventory 🔒 readonly
  > A storable product is a product for which you manage stock.
- `name_short` **(char)** — Name Short 🔒 readonly
- `remaining_hours_available` **(boolean)** — Remaining Hours Available 🔒 readonly
