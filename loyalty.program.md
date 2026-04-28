# Loyalty Program — `loyalty.program`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Program Name ⚠️ obrigatório
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`
- `program_type` **(selection)** — Program Type ⚠️ obrigatório
  > Opções: `coupons` (Coupons), `gift_card` (Gift Card), `loyalty` (Loyalty Cards), `promotion` (Promotions), `ewallet` (eWallet), `promo_code` (Discount Code), `buy_x_get_y` (Buy X Get Y), `next_order_coupons` (Next Order Coupons)
- `applies_on` **(selection)** — Applies On ⚠️ obrigatório
  > Opções: `current` (Current order), `future` (Future orders), `both` (Current & Future orders)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `date_from` **(date)** — Start Date
  > The start date is included in the validity period of this program
- `date_to` **(date)** — End date
  > The end date is included in the validity period of this program
- `limit_usage` **(boolean)** — Limit Usage
- `max_usage` **(integer)** — Max Usage
- `trigger` **(selection)** — Trigger
  >          Automatic: Customers will be eligible for a reward automatically in their cart.         Use a code: Customers will be eligible for a reward if they enter a code.         
  > Opções: `auto` (Automatic), `with_code` (Use a code)
- `portal_visible` **(boolean)** — Portal Visible
  >          Show in web portal, PoS customer ticket, eCommerce checkout, the number of points available          and used by reward.         
- `portal_point_name` **(char)** — Portal Point Name
- `available_on` **(boolean)** — Available On
  > Manage where your program should be available for use.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `sale_ok` **(boolean)** — Sales
- `ecommerce_ok` **(boolean)** — Available on Website

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `company_id` **(many2one)** — Company → `res.company`
- `pricelist_ids` **(many2many)** — Pricelist → `product.pricelist`
  > This program is specific to this pricelist set.
- `rule_ids` **(one2many)** — Conditional rules → `loyalty.rule`
- `reward_ids` **(one2many)** — Rewards → `loyalty.reward`
- `communication_plan_ids` **(one2many)** — Communication Plan → `loyalty.mail`
- `mail_template_id` **(many2one)** — Email template → `mail.template`
- `trigger_product_ids` **(many2many)** — Products → `product.product`
- `coupon_ids` **(one2many)** — Coupon → `loyalty.card`
- `payment_program_discount_product_id` **(many2one)** — Discount Product 🔒 readonly → `product.product`
  > Product used in the sales order to apply the discount.

## Campos Calculados (readonly)

- `currency_symbol` **(char)** — Symbol 🔒 readonly
  > Currency sign, to be used when printing amounts.
- `total_order_count` **(integer)** — Total Order Count 🔒 readonly
- `coupon_count` **(integer)** — Coupon Count 🔒 readonly
- `coupon_count_display` **(char)** — Items 🔒 readonly
- `is_nominative` **(boolean)** — Is Nominative 🔒 readonly
- `is_payment_program` **(boolean)** — Is Payment Program 🔒 readonly
- `order_count` **(integer)** — Order Count 🔒 readonly
- `show_non_published_product_warning` **(boolean)** — Show Non Published Product Warning 🔒 readonly
