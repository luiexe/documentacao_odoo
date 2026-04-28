# Shipping Methods — `delivery.carrier`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Delivery Method ⚠️ obrigatório
- `delivery_type` **(selection)** — Provider ⚠️ obrigatório
  > Opções: `base_on_rule` (Based on Rules), `fixed` (Fixed Price), `envia` (Envia), `in_store` (Pick up in store)
- `product_id` **(many2one)** — Delivery Product ⚠️ obrigatório → `product.product`
- `invoice_policy` **(selection)** — Invoicing Policy ⚠️ obrigatório
  > Estimated Cost: the customer will be invoiced the estimated cost of the shipping. Real Cost: the customer will be invoiced the real cost of the shipping, the cost of theshipping will be updated on the SO after the delivery.
  > Opções: `estimated` (Estimated cost), `real` (Real cost)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
  > Determine the display order
- `allow_cash_on_delivery` **(boolean)** — Cash on Delivery
  > Allow customers to choose Cash on Delivery as their payment method.
- `integration_level` **(selection)** — Integration Level
  > Action while validating Delivery Orders
  > Opções: `rate` (Get Rate), `rate_and_ship` (Get Rate and Create Shipment)
- `prod_environment` **(boolean)** — Environment
  > Set to True if your credentials are certified for production.
- `debug_logging` **(boolean)** — Debug logging
  > Log requests in order to ease debugging
- `tracking_url` **(char)** — Tracking Link
  > This option adds a link for the customer in the portal to track their package easily. Use <shipmenttrackingnumber> as a placeholder in your URL.
- `max_weight` **(float)** — Max Weight
  > If the total weight of the order is over this weight, the method won't be available.
- `max_volume` **(float)** — Max Volume
  > If the total volume of the order is over this volume, the method won't be available.
- `carrier_description` **(text)** — Carrier Description
  > A description of the delivery method that you want to communicate to your customers on the Sales Order and sales confirmation email.E.g. instructions for customers to follow.
- `margin` **(float)** — Margin
  > This percentage will be added to the shipping price.
- `fixed_margin` **(float)** — Fixed Margin
  > This fixed amount will be added to the shipping price.
- `free_over` **(boolean)** — Free if order amount is above
  > If the order total amount (shipping excluded) is above or equal to this value, the customer benefits from a free shipping
- `amount` **(float)** — Amount
  > Amount of the order to benefit from a free shipping, expressed in the company currency
- `return_label_on_delivery` **(boolean)** — Generate Return Label
  > The return label is automatically generated at the delivery.
- `get_return_label_from_portal` **(boolean)** — Return Label Accessible from Customer Portal
  > The return label can be downloaded by the customer from the customer portal.
- `shipping_insurance` **(integer)** — Insurance Percentage
  > Shipping insurance is a service which may reimburse senders whose parcels are lost, stolen, and/or damaged in transit.
- `fixed_price` **(float)** — Fixed Price
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `website_description` **(text)** — Description for Online Quotations
  > A description of the Product that you want to communicate to your customers. This description will be copied to every Sales Order, Delivery Order and Customer Invoice/Credit Note
- `envia_production_api_key` **(text)** — Envia Production Access Token
  > Generate an Access Token from within the Production Portal of Envia
- `envia_sandbox_api_key` **(text)** — Envia Sandbox Access Token
  > Generate an Access Token from within the Sandbox Portal of Envia
- `envia_carrier_code` **(char)** — Envia.com Carrier Code 🔒 readonly
  > The carrier on Envia.com used by this carrier. The service code belongs to it.
- `envia_service_code` **(char)** — Envia.com Service Code 🔒 readonly
  > The service that will be used for this carrier. This is set when you select a carrier from the wizard.
- `envia_service_name` **(char)** — Envia.com Service Name 🔒 readonly
  > The service that will be used for this carrier. This is set when you select a carrier from the wizard.
- `envia_label_stock_type` **(selection)** — Envia Label Type
  > Select the size of the label
  > Opções: `PAPER_4X6` (PAPER_4X6), `PAPER_4X8` (PAPER_4X8), `PAPER_7X4.75` (PAPER_7X4.75), `PAPER_8.27X11.67` (PAPER_8.27X11.67), `PAPER_8.5X11_BOTTOM_HALF_LABEL` (PAPER_8.5X11_BOTTOM_HALF_LABEL), `PAPER_8.5X11` (PAPER_8.5X11), `STOCK_2.4X6` (STOCK_2.4X6), `STOCK_2.9X5` (STOCK_2.9X5), `STOCK_3.8X4.2` (STOCK_3.8X4.2), `STOCK_3.9X7` (STOCK_3.9X7), `STOCK_4X4` (STOCK_4X4), `STOCK_4X6` (STOCK_4X6), `STOCK_4X6.5` (STOCK_4X6.5), `STOCK_4X6.75_LEADING_DOC_TAB` (STOCK_4X6.75_LEADING_DOC_TAB), `STOCK_4X7.5` (STOCK_4X7.5), `STOCK_4X8` (STOCK_4X8)
- `envia_label_file_type` **(selection)** — Envia Label File Type
  > Select the printing format of the label
  > Opções: `PNG` (PNG), `ZPLII` (ZPLII), `EPL` (EPL), `PDF` (PDF), `ZPL` (ZPL)
- `envia_return_at_senders_expense` **(boolean)** — Returned at Shippers Expense
  > If the carrier is unable to deliver the package, the package can be returned to the shipper or abandoned at the door. (Canada only)
- `envia_lift_pickup` **(boolean)** — Lift Assistance on Pickup
  > Provide liftgate assitance if the supplier doesn't have a dock or forklift to load the shipment. (United States and Mexico Only)
- `envia_lift_delivery` **(boolean)** — Lift Assistance on Delivery
  > Provide liftgate assistance if the recipient doesn't have a dock or forklift to unload the shipment. (United States and Mexico Only)
- `envia_residential_delivery` **(boolean)** — Delivery Residential Zone
  > Certain carriers like UPS will charge an extra fee to deliver to a residential zone (United States Only)
- `envia_residential_pickup` **(boolean)** — Pickup Residential Zone
  > Certain carriers like UPS will charge an extra fee to pickup from residential zones (United States Only)
- `l10n_br_edi_freight_model` **(selection)** — Freight Model
  > Brazil: Used to determine the freight model used on orders.
  > Opções: `CIF` (Freight contracting on behalf of the Sender (CIF)), `FOB` (Contracting of freight on behalf of the recipient/sender (FOB)), `Thirdparty` (Contracting Freight on behalf of third parties), `SenderVehicle` (Own transport on behalf of the sender), `ReceiverVehicle` (Own transport on behalf of the recipient), `FreeShipping` (Free shipping)

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `company_id` **(many2one)** — Company → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `country_ids` **(many2many)** — Countries → `res.country`
- `state_ids` **(many2many)** — States → `res.country.state`
- `zip_prefix_ids` **(many2many)** — Zip Prefixes → `delivery.zip.prefix`
  > Prefixes of zip codes that this carrier applies to. Note that regular expressions can be used to support countries with varying zip code lengths, i.e. '$' can be added to end of prefix to match the exact zip (e.g. '100$' will only match '100' and not '1000')
- `must_have_tag_ids` **(many2many)** — Must Have Tags → `product.tag`
  > The method is available only if at least one product of the order has one of these tags.
- `excluded_tag_ids` **(many2many)** — Excluded Tags → `product.tag`
  > The method is NOT available if at least one product of the order has one of these tags.
- `price_rule_ids` **(one2many)** — Pricing Rules → `delivery.price.rule`
- `route_ids` **(many2many)** — Routes → `stock.route`
- `envia_default_package_type_id` **(many2one)** — Envia Default Package → `stock.package.type`
  > Envia requires package dimensions for getting accurate rate, you can define these in a package type that you set as default
- `envia_currency_id` **(many2one)** — Envia Account Main Currency → `res.currency`
  > Currency set in Envia
- `country_id` **(many2one)** — Ship From → `res.country`
  > Select the country to be used by this delivery method
- `warehouse_ids` **(many2many)** — Stores → `stock.warehouse`
- `l10n_br_edi_transporter_id` **(many2one)** — Transporter Brazil → `res.partner`
  > Brazil: If this uses a transport company, add its company contact here.

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `weight_uom_name` **(char)** — Weight unit of measure label 🔒 readonly
- `volume_uom_name` **(char)** — Volume unit of measure label 🔒 readonly
- `can_generate_return` **(boolean)** — Can Generate Return 🔒 readonly
- `supports_shipping_insurance` **(boolean)** — Supports Shipping Insurance 🔒 readonly
- `envia_mail_type` **(selection)** — Envia Package Type 🔒 readonly
  > Select the package type for the shipment
  > Opções: `pallet` (Pallet), `box` (Box), `envelope` (Envelope)
