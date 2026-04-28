# Loyalty Rule — `loyalty.rule`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `program_id` **(many2one)** — Program ⚠️ obrigatório → `loyalty.program`
- `reward_point_mode` **(selection)** — Reward Point Mode ⚠️ obrigatório
  > Opções: `order` (per order), `money` (per R$ spent), `unit` (per unit paid)
- `minimum_amount_tax_mode` **(selection)** — Minimum Amount Tax Mode ⚠️ obrigatório
  > Opções: `incl` (tax included), `excl` (tax excluded)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `product_domain` **(char)** — Product Domain
- `reward_point_amount` **(float)** — Reward
- `reward_point_split` **(boolean)** — Split per unit
  > Whether to separate reward coupons per matched unit, only applies to 'future' programs and trigger mode per money spent or unit paid...
- `minimum_qty` **(integer)** — Minimum Quantity
- `minimum_amount` **(monetary)** — Minimum Purchase
- `mode` **(selection)** — Application
  > Opções: `auto` (Automatic), `with_code` (With a promotion code)
- `code` **(char)** — Discount code
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `product_ids` **(many2many)** — Products → `product.product`
- `product_category_id` **(many2one)** — Categories → `product.category`
- `product_tag_id` **(many2one)** — Product Tag → `product.tag`
- `website_id` **(many2one)** — Website 🔒 readonly → `website`
  > Restrict to a specific website.

## Campos Calculados (readonly)

- `program_type` **(selection)** — Program Type 🔒 readonly
  > Opções: `coupons` (Coupons), `gift_card` (Gift Card), `loyalty` (Loyalty Cards), `promotion` (Promotions), `ewallet` (eWallet), `promo_code` (Discount Code), `buy_x_get_y` (Buy X Get Y), `next_order_coupons` (Next Order Coupons)
- `user_has_debug` **(boolean)** — User Has Debug 🔒 readonly
- `reward_point_name` **(char)** — Portal Point Name 🔒 readonly
