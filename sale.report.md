# Sales Analysis Report — `sale.report`

**Ordenação padrão:** `date desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Order Reference 🔒 readonly
- `date` **(datetime)** — Order Date 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
- `invoice_status` **(selection)** — Order Invoice Status 🔒 readonly
  > Opções: `upselling` (Upselling Opportunity), `invoiced` (Fully Invoiced), `to invoice` (To Invoice), `no` (Nothing to Invoice)
- `partner_zip` **(char)** — Customer ZIP 🔒 readonly
- `order_reference` **(reference)** — Order
  > Opções: `sale.order` (Sales Order)
- `product_uom_qty` **(float)** — Qty Ordered 🔒 readonly
- `qty_to_deliver` **(float)** — Qty To Deliver 🔒 readonly
- `qty_delivered` **(float)** — Qty Delivered 🔒 readonly
- `qty_to_invoice` **(float)** — Qty To Invoice 🔒 readonly
- `qty_invoiced` **(float)** — Qty Invoiced 🔒 readonly
- `price_subtotal` **(monetary)** — Untaxed Total 🔒 readonly
- `price_total` **(monetary)** — Total 🔒 readonly
- `untaxed_amount_to_invoice` **(monetary)** — Untaxed Amount To Invoice 🔒 readonly
- `untaxed_amount_invoiced` **(monetary)** — Untaxed Amount Invoiced 🔒 readonly
- `line_invoice_status` **(selection)** — Invoice Status 🔒 readonly
  > Opções: `upselling` (Upselling Opportunity), `invoiced` (Fully Invoiced), `to invoice` (To Invoice), `no` (Nothing to Invoice)
- `weight` **(float)** — Gross Weight 🔒 readonly
- `volume` **(float)** — Volume 🔒 readonly
- `price_unit` **(float)** — Unit Price 🔒 readonly
- `discount` **(float)** — Discount % 🔒 readonly
- `discount_amount` **(monetary)** — Discount Amount 🔒 readonly
- `nbr` **(integer)** — # of Lines 🔒 readonly
- `margin` **(float)** — Margin
- `is_abandoned_cart` **(boolean)** — Abandoned Cart 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `pricelist_id` **(many2one)** — Pricelist 🔒 readonly → `product.pricelist`
- `team_id` **(many2one)** — Sales Team 🔒 readonly → `crm.team`
- `user_id` **(many2one)** — Salesperson 🔒 readonly → `res.users`
- `campaign_id` **(many2one)** — Campaign 🔒 readonly → `utm.campaign`
- `medium_id` **(many2one)** — Medium 🔒 readonly → `utm.medium`
- `source_id` **(many2one)** — Source 🔒 readonly → `utm.source`
- `commercial_partner_id` **(many2one)** — Customer Entity 🔒 readonly → `res.partner`
- `country_id` **(many2one)** — Customer Country 🔒 readonly → `res.country`
- `industry_id` **(many2one)** — Customer Industry 🔒 readonly → `res.partner.industry`
- `state_id` **(many2one)** — Customer State 🔒 readonly → `res.country.state`
- `categ_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `product_id` **(many2one)** — Product Variant 🔒 readonly → `product.product`
- `product_tmpl_id` **(many2one)** — Product 🔒 readonly → `product.template`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `warehouse_id` **(many2one)** — Warehouse 🔒 readonly → `stock.warehouse`
- `website_id` **(many2one)** — Website 🔒 readonly → `website`
- `public_categ_ids` **(many2many)** — eCommerce Categories 🔒 readonly → `product.public.category`
  > The product will be available in each mentioned eCommerce category. Go to Shop > Edit Click on the page and enable 'Categories' to view all eCommerce categories.
- `project_id` **(many2one)** — Project 🔒 readonly → `project.project`
