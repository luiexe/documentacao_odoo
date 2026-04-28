# Supplier Pricelist — `product.supplierinfo`

**Ordenação padrão:** `sequence, min_qty DESC, price, id`

---

## Campos Obrigatórios

- `partner_id` **(many2one)** — Vendor ⚠️ obrigatório → `res.partner`
- `product_uom_id` **(many2one)** — Unit ⚠️ obrigatório → `uom.uom`
- `min_qty` **(float)** — Quantity ⚠️ obrigatório
  > The quantity to purchase from this vendor to benefit from the unit price. If a vendor unit is set, quantity should be specified in this unit, otherwise it should be specified in the default unit of the product.
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`
- `product_tmpl_id` **(many2one)** — Product Template ⚠️ obrigatório → `product.template`
- `delay` **(integer)** — Lead Time ⚠️ obrigatório
  > Lead time in days between the confirmation of the purchase order and the receipt of the products in your warehouse. Used by the scheduler for automatic computation of the purchase order planning.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `product_name` **(char)** — Vendor Product Name
  > This vendor's product name will be used when printing a request for quotation. Keep empty to use the internal one.
- `product_code` **(char)** — Vendor Product Code
  > This vendor's product code will be used when printing a request for quotation. Keep empty to use the internal one.
- `sequence` **(integer)** — Sequence
  > Assigns the priority to the list of product vendor.
- `price` **(float)** — Unit Price
  > The price to purchase a product
- `date_start` **(date)** — Start Date
  > Start date for this vendor price
- `date_end` **(date)** — End Date
  > End date for this vendor price
- `discount` **(float)** — Discount (%)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `product_id` **(many2one)** — Product Variant → `product.product`
  > If not set, the vendor price will apply to all variants of this product.

## Campos Calculados (readonly)

- `price_discounted` **(float)** — Discounted Price 🔒 readonly
- `product_variant_count` **(integer)** — Variant Count 🔒 readonly
- `is_subcontractor` **(boolean)** — Subcontracted 🔒 readonly
  > Choose a vendor of type subcontractor if you want to subcontract the product
- `last_purchase_date` **(date)** — Last Purchase 🔒 readonly
- `show_set_supplier_button` **(boolean)** — Show Set Supplier Button 🔒 readonly
