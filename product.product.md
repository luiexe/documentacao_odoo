# Product Variant — `product.product`

**Ordenação padrão:** `default_code, name, id`

---

## Campos Obrigatórios

- `product_tmpl_id` **(many2one)** — Product Template ⚠️ obrigatório → `product.template`
- `base_unit_count` **(float)** — Base Unit Count ⚠️ obrigatório
  > Display base unit price on your eCommerce pages. Set to 0 to hide it for this product.
- `name` **(char)** — Name ⚠️ obrigatório
- `type` **(selection)** — Product Type ⚠️ obrigatório
  > Goods are tangible materials and merchandise you provide. A service is a non-material product you provide.
  > Opções: `consu` (Goods), `service` (Service), `combo` (Combo)
- `service_tracking` **(selection)** — Create on Order ⚠️ obrigatório
  > Opções: `no` (Nothing), `task_global_project` (Task), `task_in_project` (Project & Task), `project_only` (Project)
- `uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
  > Default unit of measure used for all stock operations.
- `product_variant_ids` **(one2many)** — Products ⚠️ obrigatório → `product.product`
- `tracking` **(selection)** — Tracking ⚠️ obrigatório
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `publish_date` **(datetime)** — Publish Date ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lst_price` **(float)** — Sales Price
  > The sale price is managed from the product template. Click on the 'Configure Variants' button to set the extra attribute prices.
- `default_code` **(char)** — Internal Reference
- `active` **(boolean)** — Active
  > If unchecked, it will allow you to hide the product without removing it.
- `barcode` **(char)** — Barcode
  > International Article Number used for product identification.
- `import_attribute_values` **(char)** — Product Values
- `combination_indices` **(char)** — Combination Indices 🔒 readonly
- `standard_price` **(float)** — Cost
  > Value of the product (automatically computed in AVCO).         Used to value the product when the purchase cost is not known (e.g. inventory adjustment).         Used to compute margins on sale orders.
- `volume` **(float)** — Volume
- `weight` **(float)** — Weight
- `image_variant_1920` **(binary)** — Variant Image
- `image_variant_1024` **(binary)** — Variant Image 1024 🔒 readonly
- `image_variant_512` **(binary)** — Variant Image 512 🔒 readonly
- `image_variant_256` **(binary)** — Variant Image 256 🔒 readonly
- `image_variant_128` **(binary)** — Variant Image 128 🔒 readonly
- `can_image_variant_1024_be_zoomed` **(boolean)** — Can Variant Image 1024 be zoomed 🔒 readonly
- `image_1920` **(binary)** — Image
- `write_date` **(datetime)** — Write Date 🔒 readonly
- `is_favorite` **(boolean)** — Favorite
- `is_in_selected_section_of_order` **(boolean)** — Is In Selected Section Of Order
- `create_date` **(datetime)** — Created on 🔒 readonly
- `is_image_fetch_pending` **(boolean)** — Is Image Fetch Pending
  > Whether an image must be fetched for this product. Handled by a cron.
- `qty_available` **(float)** — Quantity On Hand
  > Current quantity of products. In a context with a single Stock Location, this includes goods stored at this Location, or any of its children. In a context with a single Warehouse, this includes goods stored in the Stock Location of this Warehouse, or any of its children. stored in the Stock Location of the Warehouse of this Shop, or any of its children. Otherwise, this includes goods stored in any Stock Location with 'internal' type.
- `lot_properties_definition` **(properties_definition)** — Lot Properties
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `sequence` **(integer)** — Sequence
  > Gives the sequence order when displaying a product list
- `description` **(html)** — Description
- `description_purchase` **(text)** — Purchase Description
- `description_sale` **(text)** — Sales Description
  > A description of the Product that you want to communicate to your customers. This description will be copied to every Sales Order, Delivery Order and Customer Invoice/Credit Note
- `list_price` **(float)** — Sales Price
  > Price at which the product is sold to customers.
- `sale_ok` **(boolean)** — Sales
- `purchase_ok` **(boolean)** — Purchase
- `color` **(integer)** — Color Index
- `product_properties` **(properties)** — Properties
- `is_storable` **(boolean)** — Track Inventory
  > A storable product is a product for which you manage stock.
- `sale_delay` **(integer)** — Customer Lead Time
  > Delivery lead time, in days. It's the number of days, promised to the customer, between the confirmation of the sales order and the delivery.
- `serial_prefix_format` **(char)** — Custom Lot/Serial
  >      If multiple products share the same prefix, they will share the same sequence, otherwise the sequence will be dedicated to the product.      * Legend (for prefix):     - Current Year with Century: %(year)s     - Current Year without Century: %(y)s     - Month: %(month)s     - Day: %(day)s     - Day of the Year: %(doy)s     - Week of the Year: %(woy)s     - Day of the Week (0:Monday): %(weekday)s     - Hour 00->24: %(h24)s     - Hour 00->12: %(h12)s     - Minute: %(min)s     - Second: %(sec)s 
- `description_picking` **(text)** — Description on Picking
- `description_pickingout` **(text)** — Description on Delivery Orders
- `description_pickingin` **(text)** — Description on Receptions
- `can_be_expensed` **(boolean)** — Expenses
  > Specify whether the product can be selected in an expense.
- `purchase_method` **(selection)** — Control Policy
  > On ordered quantities: Control bills based on ordered quantities. On received quantities: Control bills based on received quantities.
  > Opções: `purchase` (On ordered quantities), `receive` (On received quantities)
- `purchase_line_warn_msg` **(text)** — Message for Purchase Order Line
- `lot_valuated` **(boolean)** — Valuation by Lot/Serial
  > If checked, the valuation will be specific by Lot/Serial number.
- `version` **(integer)** — Version
  > The current version of the product.
- `service_type` **(selection)** — Track Service
  > Manually set quantities on order: Invoice based on the manually entered quantity, without creating an analytic account. Timesheets on contract: Invoice based on the tracked hours on the related timesheet. Create a task and track hours: Create a task on the sales order validation and track the work hours.
  > Opções: `manual` (Manually set quantities on order), `milestones` (Project Milestones), `timesheet` (Timesheets on project (one fare per SO/Project))
- `sale_line_warn_msg` **(text)** — Sales Order Line Warning
- `expense_policy` **(selection)** — Re-Invoice Costs
  > Validated expenses, vendor bills, or stock pickings (set up to track costs) can be invoiced to the customer at either cost or sales price.
  > Opções: `no` (No), `cost` (At cost), `sales_price` (Sales price)
- `invoice_policy` **(selection)** — Invoicing Policy
  > Ordered Quantity: Invoice quantities ordered by the customer. Delivered Quantity: Invoice quantities delivered to the customer.
  > Opções: `order` (Ordered quantities), `delivery` (Delivered quantities)
- `service_to_purchase` **(boolean)** — Subcontract Service
  > If ticked, each time you sell this product through a SO, a RfQ is automatically created to buy the product. Tip: don't forget to set a vendor on the product.
- `l10n_br_cest_code` **(char)** — CEST Code
  > A tax classification code used to identify goods and products subject to tax substitution under ICMS regulations.It helps determine the applicable tax treatment and procedures for specific items.Check if your product is subject or not to this in https://www.codigocest.com.br/.
- `l10n_br_labor` **(boolean)** — Labor Assignment
  > Brazil: If your service involves labor, select this checkbox.
- `l10n_br_source_origin` **(selection)** — Source of Origin
  > Brazil: Product Source of Origin indicates if the product has a foreing or national origin with different variations and characteristics dependin on the product use case
  > Opções: `0` (National goods - except those treated in codes 3,4, 5 and 8), `1` (Foreign goods - Imported directly by seller, except those in code 6), `2` (Foreign goods - Acquired in the internal market (inside Brazil), except those in code 7), `3` (National goods - Merchandise or goods with imported content above 40% and with less than or equal to 70%), `4` (National goods from production following 'standard basic processes' as stablished by legislation (standard basic processes are devised to separate simple assembly from manufaturing processes)), `5` (National goods - Merchandise or goods with imported content equal or below 40%), `6` (Foreign goods - Directly imported by Seller, without a National Equivalent as listed by Comex and natural gas), `7` (Foreign goods - Acquired inside Brazil, without a National Equivalent as listed by Comex and natural gas), `8` (National goods - Merchandise or goods with imported content above 70% (pt))
- `l10n_br_sped_type` **(selection)** — SPED Fiscal Product Type
  > Brazil: Fiscal product type according to SPED list table
  > Opções: `FOR PRODUCT` (For product), `FOR MERCHANDISE` (For merchandise), `NO RESTRICTION` (No restriction), `SERVICE` (Service), `FEEDSTOCK` (Feedstock), `FIXED ASSETS` (Fixed assets), `PACKAGING` (Packaging), `PRODUCT IN PROCESS` (Product in process), `SUBPRODUCT` (Subproduct), `INTERMEDIATE PRODUCT` (Intermediate product), `MATERIAL FOR USAGE AND CONSUMPTION` (Material for usage and consumption), `OTHER INPUTS` (Other inputs)
- `l10n_br_use_type` **(selection)** — Purpose of Use
  > Brazil: indicate what is the usage purpose for this product
  > Opções: `use or consumption` (Use or consumption), `resale` (Resale), `agricultural production` (Agricultural production), `production` (Production), `fixed assets` (Fixed assets), `notApplicable` (Not applicable)
- `l10n_br_transport_cost_type` **(selection)** — Transport Cost Type
  > Brazil: select whether this product will be use to register Freight, Insurance or Other Costs amounts related to the transaction.
  > Opções: `freight` (Freight), `insurance` (Insurance), `other` (Other costs)
- `hs_code` **(char)** — HS Code
  > Standardized code for international shipping and goods declaration.
- `website_description` **(html)** — Description for the website
- `description_ecommerce` **(html)** — eCommerce Description
- `website_size_x` **(integer)** — Size X
- `website_size_y` **(integer)** — Size Y
- `website_sequence` **(integer)** — Website Sequence
  > Determine the display order in the Website E-commerce
- `compare_list_price` **(monetary)** — Compare to Price
  > Add a strikethrough price to your /shop and product pages for comparison purposes.It will not be displayed if pricelists apply.
- `planning_enabled` **(boolean)** — Plan Services
  > If enabled, a shift will automatically be generated for the selected role when confirming the Sales Order.                 With the 'auto plan' feature, only employees with this role will be automatically assigned shifts for Sales Orders containing this service.                 The system will consider employee availability and the remaining time to be planned.                 You can also manually schedule open shifts for your Sales Order or assign them to any employee you prefer.
- `service_policy` **(selection)** — Service Invoicing Policy
  > Opções: `ordered_prepaid` (Prepaid/Fixed Price), `delivered_timesheet` (Based on Timesheets), `delivered_milestones` (Based on Milestones), `delivered_manual` (Based on Delivered Quantity (Manual))
- `allow_out_of_stock_order` **(boolean)** — Sell when Out-of-Stock
- `available_threshold` **(float)** — Show Threshold
- `show_availability` **(boolean)** — Show availability Qty
- `out_of_stock_message` **(html)** — Out-of-Stock Message
- `l10n_br_taxable_is` **(boolean)** — IS taxable
  > Brazil: Indicates that this product is exempt from the Selective Tax (IS) due to a specific fiscal benefit, overriding the standard IS taxation rules.
- `service_upsell_threshold` **(float)** — Threshold
  > Percentage of time delivered compared to the prepaid amount that must be reached for the upselling opportunity activity to be triggered.

## Relacionamentos

- `product_uom_ids` **(one2many)** — Unit Barcode → `product.uom`
- `product_template_attribute_value_ids` **(many2many)** — Attribute Values → `product.template.attribute.value`
- `product_template_variant_value_ids` **(many2many)** — Variant Values → `product.template.attribute.value`
- `pricelist_rule_ids` **(one2many)** — Pricelist Rules → `product.pricelist.item`
- `product_document_ids` **(one2many)** — Documents → `product.document`
- `additional_product_tag_ids` **(many2many)** — Variant Tags → `product.tag`
- `all_product_tag_ids` **(many2many)** — All Product Tag 🔒 readonly → `product.tag`
- `stock_quant_ids` **(one2many)** — Stock Quant → `stock.quant`
- `stock_move_ids` **(one2many)** — Stock Move → `stock.move`
- `orderpoint_ids` **(one2many)** — Minimum Stock Rules → `stock.warehouse.orderpoint`
- `putaway_rule_ids` **(one2many)** — Putaway Rules → `stock.putaway.rule`
- `storage_category_capacity_ids` **(one2many)** — Storage Category Capacity → `stock.storage.category.capacity`
- `variant_bom_ids` **(one2many)** — BOM Product Variants → `mrp.bom`
- `bom_line_ids` **(one2many)** — BoM Components → `mrp.bom.line`
- `company_currency_id` **(many2one)** — Valuation Currency 🔒 readonly → `res.currency`
  > Technical field to correctly show the currently selected company's currency that corresponds to the totaled value of the product's valuation layers
- `purchase_order_line_ids` **(one2many)** — PO Lines → `purchase.order.line`
- `variant_ribbon_id` **(many2one)** — Variant Ribbon → `product.ribbon`
- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `product_variant_image_ids` **(one2many)** — Extra Variant Images → `product.image`
- `base_unit_id` **(many2one)** — Custom Unit of Measure → `website.base.unit`
  > Define a custom unit to display in the price per unit of measure field.
- `stock_notification_partner_ids` **(many2many)** — Back in stock Notifications → `res.partner`
- `combo_ids` **(many2many)** — Combo Choices → `product.combo`
- `categ_id` **(many2one)** — Product Category → `product.category`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `cost_currency_id` **(many2one)** — Cost Currency 🔒 readonly → `res.currency`
- `uom_ids` **(many2many)** — Packagings → `uom.uom`
  > Additional packagings for this product which can be used for sales
- `company_id` **(many2one)** — Company → `res.company`
- `seller_ids` **(one2many)** — Vendors → `product.supplierinfo`
- `variant_seller_ids` **(one2many)** — Variant Seller → `product.supplierinfo`
- `attribute_line_ids` **(one2many)** — Product Attributes → `product.template.attribute.line`
- `valid_product_template_attribute_line_ids` **(many2many)** — Valid Product Attribute Lines 🔒 readonly → `product.template.attribute.line`
- `product_variant_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `product_tag_ids` **(many2many)** — Tags → `product.tag`
- `taxes_id` **(many2many)** — Sales Taxes → `account.tax`
  > Default taxes used when selling the product
- `supplier_taxes_id` **(many2many)** — Purchase Taxes → `account.tax`
  > Default taxes used when buying the product
- `property_account_income_id` **(many2one)** — Income Account → `account.account`
  > Keep this field empty to use the default value from the product category.
- `property_account_expense_id` **(many2one)** — Expense Account → `account.account`
  > Keep this field empty to use the default value from the product category. If anglo-saxon accounting with automated valuation method is configured, the expense account on the product category will be used.
- `account_tag_ids` **(many2many)** — Account Tags → `account.account.tag`
  > Tags to be set on the base and tax journal items created for this product.
- `responsible_id` **(many2one)** — Responsible → `res.users`
  > This user will be responsible of the next activities related to logistic operations for this product.
- `property_stock_production` **(many2one)** — Production Location → `stock.location`
  > This stock location will be used, instead of the default one, as the source location for stock moves generated by manufacturing orders.
- `property_stock_inventory` **(many2one)** — Inventory Location → `stock.location`
  > This stock location will be used, instead of the default one, as the source location for stock moves generated when you do an inventory.
- `lot_sequence_id` **(many2one)** — Serial/Lot Numbers Sequence → `ir.sequence`
  > Technical Field: The Ir.Sequence record that is used to generate serial/lot numbers for this product
- `location_id` **(many2one)** — Location → `stock.location`
- `warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`
- `route_ids` **(many2many)** — Routes → `stock.route`
  > Depending on the modules installed, this will allow you to define the route of the product: whether it will be bought, manufactured, replenished on order, etc.
- `route_from_categ_ids` **(many2many)** — Category Routes 🔒 readonly → `stock.route`
- `bom_ids` **(one2many)** — Bill of Materials → `mrp.bom`
- `property_price_difference_account_id` **(many2one)** — Price Difference Account → `account.account`
  > With perpetual valuation, this account will hold the price difference between the standard price and the bill price.
- `eco_ids` **(one2many)** — ECOs → `mrp.eco`
- `optional_product_ids` **(many2many)** — Optional Products → `product.template`
  > Optional Products are suggested whenever the customer hits *Add to Cart* (cross-sell strategy, e.g. for computers: warranty, software, etc.).
- `l10n_br_ncm_code_id` **(many2one)** — Mercosul NCM Code → `l10n_br.ncm.code`
  > Brazil: Use this field to specify the classification code of the item, either the NCM (Nomenclatura Comum do Mercosul) for goods or the LC116 for services.
- `l10n_br_property_service_code_origin_id` **(many2one)** — Service Code Origin → `l10n_br.service.code`
  > Brazil: City service code where the provider is registered.
- `l10n_br_service_code_ids` **(many2many)** — Service Codes → `l10n_br.service.code`
  > Brazil: The service codes for this product, as defined by the cities in which you wish to sell it. If no city-specific code is provided, the Service Code Origin will be used instead.
- `l10n_br_company_city_id` **(many2one)** — L10N Br Company City 🔒 readonly → `res.city`
  > Technical field used to determined the default of a service code when configured as a service code origin.
- `country_of_origin` **(many2one)** — Origin of Goods → `res.country`
  > Rules of origin determine where goods originate, i.e. not where they have been shipped from, but where they have been produced or manufactured. As such, the ‘origin’ is the 'economic nationality' of goods traded in commerce.
- `alternative_product_ids` **(many2many)** — Alternative Products → `product.template`
  > Suggest alternatives to your customer (upsell strategy). Those products show up on the product page.
- `accessory_product_ids` **(many2many)** — Accessory Products → `product.product`
  > Accessories show up when the customer reviews the cart before payment (cross-sell strategy).
- `website_ribbon_id` **(many2one)** — Ribbon → `product.ribbon`
- `public_categ_ids` **(many2many)** — Website Product Category → `product.public.category`
  > The product will be available in each mentioned eCommerce category. Go to Shop > Edit Click on the page and enable 'Categories' to view all eCommerce categories.
- `product_template_image_ids` **(one2many)** — Extra Product Media → `product.image`
- `planning_role_id` **(many2one)** — Planning Role → `planning.role`
- `project_id` **(many2one)** — Project → `project.project`
- `project_template_id` **(many2one)** — Project Template → `project.project`
- `task_template_id` **(many2one)** — Task Template → `project.task`
- `l10n_br_nbs_id` **(many2one)** — NBS Code → `l10n_br.nbs.code`
  > Brazil: Brazilian Service Classification (NBS) code required for services in the tax reform.
- `l10n_br_legal_uom_id` **(many2one)** — Legal Unit of Measure → `uom.uom`
  > Brazil: Determines the conversion factor between the commercial unit and the taxable unit when taxes apply per quantity (ad rem).
- `l10n_br_operation_type_sales_id` **(many2one)** — Sales Operation Type → `l10n_br.operation.type`
  > Brazil: if an Operation Type is selected, it will be added on sale orders and invoices. If empty, it won’t be added on the line, and the one on the header will be used.
- `l10n_br_operation_type_purchases_id` **(many2one)** — Purchases Operation Type → `l10n_br.operation.type`
  > Brazil: if an Operation Type is selected, it will be added on the vendor bill. If empty, it won’t be added on the line, and the one on the header will be used.
- `l10n_br_operation_type_ecommerce_id` **(many2one)** — eCommerce Operation Type → `l10n_br.operation.type`
  > Brazil: if an Operation Type is selected, it will be added on eCommerce sale orders. If empty, it won’t be added on the line, and the one on the header will be used.

## Campos Calculados (readonly)

- `price_extra` **(float)** — Variant Price Extra 🔒 readonly
  > This is the sum of the extra price of all attributes
- `code` **(char)** — Reference 🔒 readonly
- `partner_ref` **(char)** — Customer Ref 🔒 readonly
- `is_product_variant` **(boolean)** — Is Product Variant 🔒 readonly
- `product_document_count` **(integer)** — Documents Count 🔒 readonly
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `can_image_1024_be_zoomed` **(boolean)** — Can Image 1024 be zoomed 🔒 readonly
- `tax_string` **(char)** — Tax String 🔒 readonly
- `virtual_available` **(float)** — Forecasted Quantity 🔒 readonly
  > Forecast quantity (computed as Quantity On Hand - Outgoing + Incoming) In a context with a single Stock Location, this includes goods stored in this location, or any of its children. In a context with a single Warehouse, this includes goods stored in the Stock Location of this Warehouse, or any of its children. Otherwise, this includes goods stored in any Stock Location with 'internal' type.
- `free_qty` **(float)** — Free To Use Quantity  🔒 readonly
  > Available quantity (computed as Quantity On Hand - reserved quantity) In a context with a single Stock Location, this includes goods stored in this location, or any of its children. In a context with a single Warehouse, this includes goods stored in the Stock Location of this Warehouse, or any of its children. Otherwise, this includes goods stored in any Stock Location with 'internal' type.
- `incoming_qty` **(float)** — Incoming 🔒 readonly
  > Quantity of planned incoming products. In a context with a single Stock Location, this includes goods arriving to this Location, or any of its children. In a context with a single Warehouse, this includes goods arriving to the Stock Location of this Warehouse, or any of its children. Otherwise, this includes goods arriving to any Stock Location with 'internal' type.
- `outgoing_qty` **(float)** — Outgoing 🔒 readonly
  > Quantity of planned outgoing products. In a context with a single Stock Location, this includes goods leaving this Location, or any of its children. In a context with a single Warehouse, this includes goods leaving the Stock Location of this Warehouse, or any of its children. Otherwise, this includes goods leaving any Stock Location with 'internal' type.
- `nbr_moves_in` **(integer)** — Nbr Moves In 🔒 readonly
  > Number of incoming stock moves in the past 12 months
- `nbr_moves_out` **(integer)** — Nbr Moves Out 🔒 readonly
  > Number of outgoing stock moves in the past 12 months
- `nbr_reordering_rules` **(integer)** — Reordering Rules 🔒 readonly
- `reordering_min_qty` **(float)** — Reordering Min Qty 🔒 readonly
- `reordering_max_qty` **(float)** — Reordering Max Qty 🔒 readonly
- `show_on_hand_qty_status_button` **(boolean)** — Show On Hand Qty Status Button 🔒 readonly
- `show_forecasted_qty_status_button` **(boolean)** — Show Forecasted Qty Status Button 🔒 readonly
- `show_qty_update_button` **(boolean)** — Show Qty Update Button 🔒 readonly
- `valid_ean` **(boolean)** — Barcode is valid EAN 🔒 readonly
- `standard_price_update_warning` **(char)** — Standard Price Update Warning 🔒 readonly
- `bom_count` **(integer)** — # Bill of Material 🔒 readonly
- `used_in_bom_count` **(integer)** — # BoM Where Used 🔒 readonly
- `mrp_product_qty` **(float)** — Manufactured 🔒 readonly
- `is_kits` **(boolean)** — Is Kits 🔒 readonly
- `product_catalog_product_is_in_bom` **(boolean)** — Product Catalog Product Is In Bom 🔒 readonly
- `product_catalog_product_is_in_mo` **(boolean)** — Product Catalog Product Is In Mo 🔒 readonly
- `purchased_product_qty` **(float)** — Purchased 🔒 readonly
- `is_in_purchase_order` **(boolean)** — Is In Purchase Order 🔒 readonly
- `avg_cost` **(monetary)** — Average Cost 🔒 readonly
- `total_value` **(monetary)** — Total Value 🔒 readonly
- `has_image` **(boolean)** — Has Image 🔒 readonly
- `monthly_demand` **(float)** — Monthly Demand 🔒 readonly
- `suggested_qty` **(integer)** — Suggested Qty 🔒 readonly
- `suggest_estimated_price` **(float)** — Suggest Estimated Price 🔒 readonly
- `quality_control_point_qty` **(integer)** — Quality Control Point Qty 🔒 readonly
- `quality_pass_qty` **(integer)** — Quality Pass Qty 🔒 readonly
- `quality_fail_qty` **(integer)** — Quality Fail Qty 🔒 readonly
- `sales_count` **(float)** — Sold 🔒 readonly
- `product_catalog_product_is_in_sale_order` **(boolean)** — Product Catalog Product Is In Sale Order 🔒 readonly
- `schedule_count` **(integer)** — Schedules 🔒 readonly
- `base_unit_price` **(monetary)** — Price Per Unit 🔒 readonly
- `base_unit_name` **(char)** — Base Unit Name 🔒 readonly
  > Displays the custom unit for the products if defined or the selected unit of measure otherwise.
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full URL to access the document through the website.
- `is_booking_fee` **(boolean)** — Is Booking Fee 🔒 readonly
- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `volume_uom_name` **(char)** — Volume unit of measure label 🔒 readonly
- `weight_uom_name` **(char)** — Weight unit of measure label 🔒 readonly
- `uom_name` **(char)** — Unit Name 🔒 readonly
- `product_variant_count` **(integer)** — # Product Variants 🔒 readonly
- `has_configurable_attributes` **(boolean)** — Is a configurable product 🔒 readonly
- `is_dynamically_created` **(boolean)** — Is Dynamically Created 🔒 readonly
- `product_tooltip` **(char)** — Product Tooltip 🔒 readonly
- `fiscal_country_codes` **(char)** — Fiscal Country Codes 🔒 readonly
- `next_serial` **(char)** — Next Serial 🔒 readonly
- `has_available_route_ids` **(boolean)** — Routes can be selected on this product 🔒 readonly
- `cost_method` **(selection)** — Cost Method 🔒 readonly
  > Opções: `standard` (Standard Price), `fifo` (First In First Out (FIFO)), `average` (Average Cost (AVCO))
- `valuation` **(selection)** — Valuation 🔒 readonly
  > Opções: `periodic` (Periodic (at closing)), `real_time` (Perpetual (at invoicing))
- `eco_count` **(integer)** — # ECOs 🔒 readonly
- `visible_expense_policy` **(boolean)** — Re-Invoice Policy visible 🔒 readonly
- `expense_policy_tooltip` **(char)** — Expense Policy Tooltip 🔒 readonly
- `rating_last_value` **(float)** — Rating Last Value 🔒 readonly
- `rating_last_feedback` **(text)** — Rating Last Feedback 🔒 readonly
- `rating_last_image` **(binary)** — Rating Last Image 🔒 readonly
- `rating_count` **(integer)** — Rating count 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `rating_avg_text` **(selection)** — Rating Avg Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `rating_percentage_satisfaction` **(float)** — Rating Satisfaction 🔒 readonly
- `rating_last_text` **(selection)** — Rating Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `variants_default_code` **(char)** — Variants Default Code 🔒 readonly
  > Technical field to enhance performance when looking up default code of productvariants (LIKE/ILIKE)
- `service_upsell_threshold_ratio` **(char)** — Service Upsell Threshold Ratio 🔒 readonly
