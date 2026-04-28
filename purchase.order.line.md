# Purchase Order Line — `purchase.order.line`

**Ordenação padrão:** `order_id, sequence, id`

---

## Campos Obrigatórios

- `name` **(text)** — Description ⚠️ obrigatório
- `product_qty` **(float)** — Quantity ⚠️ obrigatório
- `price_unit` **(float)** — Unit Price ⚠️ obrigatório
- `order_id` **(many2one)** — Order Reference ⚠️ obrigatório → `purchase.order`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `sequence` **(integer)** — Sequence
- `product_uom_qty` **(float)** — Total Quantity 🔒 readonly
- `date_planned` **(datetime)** — Expected Arrival
  > Delivery date expected from vendor. This date respectively defaults to vendor pricelist lead time then today's date.
- `discount` **(float)** — Discount (%)
- `price_subtotal` **(monetary)** — Subtotal 🔒 readonly
- `price_total` **(monetary)** — Total 🔒 readonly
- `price_tax` **(float)** — Tax 🔒 readonly
- `qty_invoiced` **(float)** — Billed Qty 🔒 readonly
- `qty_received_method` **(selection)** — Received Qty Method 🔒 readonly
  > According to product configuration, the received quantity can be automatically computed by mechanism:   - Manual: the quantity is set manually on the line   - Stock Moves: the quantity comes from confirmed pickings 
  > Opções: `manual` (Manual), `stock_moves` (Stock Moves)
- `qty_received` **(float)** — Received Qty
- `qty_received_manual` **(float)** — Manual Received Qty
- `qty_to_invoice` **(float)** — To Invoice Quantity 🔒 readonly
- `display_type` **(selection)** — Display Type
  > Technical field for UX purpose.
  > Opções: `line_section` (Section), `line_subsection` (Subsection), `line_note` (Note)
- `is_downpayment` **(boolean)** — Is Downpayment
- `technical_price_unit` **(float)** — Technical Price Unit
  > Technical field for price computation
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `product_description_variants` **(char)** — Custom Description
- `propagate_cancel` **(boolean)** — Propagate cancellation
- `analytic_json` **(json)** — Analytic JSON 🔒 readonly

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `tax_ids` **(many2many)** — Taxes → `account.tax`
- `allowed_uom_ids` **(many2many)** — Allowed Uom 🔒 readonly → `uom.uom`
- `product_uom_id` **(many2one)** — Unit → `uom.uom`
- `product_id` **(many2one)** — Product → `product.product`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `invoice_lines` **(one2many)** — Bill Lines 🔒 readonly → `account.move.line`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
  > You can find a vendor by its Name, TIN, Email or Internal Reference.
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `selected_seller_id` **(many2one)** — Selected Seller 🔒 readonly → `product.supplierinfo`
  > Technical field to get the vendor pricelist used to generate this line
- `product_template_attribute_value_ids` **(many2many)** — Attribute Values 🔒 readonly → `product.template.attribute.value`
- `product_no_variant_attribute_value_ids` **(many2many)** — Product attribute values that do not create variants → `product.template.attribute.value`
- `parent_id` **(many2one)** — Parent Section Line 🔒 readonly → `purchase.order.line`
- `move_ids` **(one2many)** — Reservation 🔒 readonly → `stock.move`
- `orderpoint_id` **(many2one)** — Orderpoint → `stock.warehouse.orderpoint`
- `move_dest_ids` **(many2many)** — Downstream moves alt → `stock.move`
- `location_final_id` **(many2one)** — Location from procurement → `stock.location`
- `sale_order_id` **(many2one)** — Sale Order 🔒 readonly → `sale.order`
- `sale_line_id` **(many2one)** — Origin Sale Item → `sale.order.line`
- `budget_line_ids` **(one2many)** — Budget Lines 🔒 readonly → `budget.line`

## Campos Calculados (readonly)

- `translated_product_name` **(text)** — Translated Product Name 🔒 readonly
- `product_type` **(selection)** — Product Type 🔒 readonly
  > Goods are tangible materials and merchandise you provide. A service is a non-material product you provide.
  > Opções: `consu` (Goods), `service` (Service), `combo` (Combo)
- `price_unit_product_uom` **(float)** — Unit Price Product UoM 🔒 readonly
  > The Price of one unit of the product's Unit of Measure
- `price_unit_discounted` **(float)** — Unit Price (Discounted) 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (RFQ), `sent` (RFQ Sent), `to approve` (To Approve), `purchase` (Purchase Order), `cancel` (Cancelled)
- `qty_received_at_date` **(float)** — Received 🔒 readonly
- `qty_invoiced_at_date` **(float)** — Billed 🔒 readonly
- `amount_to_invoice_at_date` **(float)** — Amount 🔒 readonly
- `date_order` **(datetime)** — Order Date 🔒 readonly
  > Depicts the date within which the Quotation should be confirmed and converted into a purchase order.
- `date_approve` **(datetime)** — Confirmation Date 🔒 readonly
- `tax_calculation_rounding_method` **(selection)** — Tax calculation rounding method 🔒 readonly
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `purchase_line_warn_msg` **(text)** — Purchase Line Warn Msg 🔒 readonly
- `forecasted_issue` **(boolean)** — Forecasted Issue 🔒 readonly
- `is_storable` **(boolean)** — Track Inventory 🔒 readonly
  > A storable product is a product for which you manage stock.
- `is_above_budget` **(boolean)** — Is Above Budget 🔒 readonly
