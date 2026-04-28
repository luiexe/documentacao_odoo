# Pricelist Rule — `product.pricelist.item`

**Ordenação padrão:** `applied_on, min_quantity desc, categ_id desc, id desc`

---

## Campos Obrigatórios

- `applied_on` **(selection)** — Apply On ⚠️ obrigatório
  > Pricelist Item applicable on selected option
  > Opções: `3_global` (All Products), `2_product_category` (Product Category), `1_product` (Product), `0_product_variant` (Product Variant)
- `display_applied_on` **(selection)** — Display Applied On ⚠️ obrigatório
  > Pricelist Item applicable on selected option
  > Opções: `1_product` (Product), `2_product_category` (Category)
- `base` **(selection)** — Based on ⚠️ obrigatório
  > Base price for computation. Sales Price: The base price will be the Sales Price. Cost Price: The base price will be the cost price. Other Pricelist: Computation of the base price based on another Pricelist.
  > Opções: `list_price` (Sales Price), `standard_price` (Cost), `pricelist` (Other Pricelist)
- `compute_price` **(selection)** — Compute Price ⚠️ obrigatório
  > Use the discount rules and activate the discount settings in order to show discount to customer.
  > Opções: `percentage` (Discount), `formula` (Formula), `fixed` (Fixed Price)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_start` **(datetime)** — Start Date
  > Starting datetime for the pricelist item validation The displayed value depends on the timezone set in your preferences.
- `date_end` **(datetime)** — End Date
  > Ending datetime for the pricelist item validation The displayed value depends on the timezone set in your preferences.
- `min_quantity` **(float)** — Min. Quantity
  > For the rule to apply, bought/sold quantity must be greater than or equal to the minimum quantity specified in this field. Expressed in the default unit of measure of the product.
- `fixed_price` **(float)** — Fixed Price
- `percent_price` **(float)** — Percentage Price
  > You can apply a mark-up by setting a negative discount.
- `price_discount` **(float)** — Price Discount
  > You can apply a mark-up by setting a negative discount.
- `price_round` **(float)** — Price Rounding
  > Sets the price so that it is a multiple of this value. Rounding is applied after the discount and before the surcharge. To have prices that end in 9.99, round off to 10.00 and set an extra at -0.01
- `price_surcharge` **(float)** — Extra Fee
  > Specify the fixed amount to add or subtract (if negative) to the amount calculated with the discount.
- `price_markup` **(float)** — Markup
  > You can apply a mark-up on the cost
- `price_min_margin` **(float)** — Min. Price Margin
  > Specify the minimum amount of margin over the base price.
- `price_max_margin` **(float)** — Max. Price Margin
  > Specify the maximum amount of margin over the base price.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `pricelist_id` **(many2one)** — Pricelist → `product.pricelist`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `categ_id` **(many2one)** — Category → `product.category`
  > Specify a product category if this rule only applies to products belonging to this category or its children categories. Keep empty otherwise.
- `product_tmpl_id` **(many2one)** — Product → `product.template`
  > Specify a template if this rule only applies to one product template. Keep empty otherwise.
- `product_id` **(many2one)** — Variant → `product.product`
  > Specify a product if this rule only applies to one product. Keep empty otherwise.
- `base_pricelist_id` **(many2one)** — Other Pricelist → `product.pricelist`

## Campos Calculados (readonly)

- `is_pricelist_required` **(boolean)** — Is Pricelist Required 🔒 readonly
- `product_uom_name` **(char)** — Unit Name 🔒 readonly
- `product_variant_count` **(integer)** — # Product Variants 🔒 readonly
- `name` **(char)** — Name 🔒 readonly
  > Explicit rule name for this pricelist line.
- `price` **(char)** — Price 🔒 readonly
  > Explicit rule name for this pricelist line.
- `rule_tip` **(char)** — Rule Tip 🔒 readonly
