# Loyalty Reward — `loyalty.reward`

**Ordenação padrão:** `required_points asc`

---

## Campos Obrigatórios

- `program_id` **(many2one)** — Program ⚠️ obrigatório → `loyalty.program`
- `description` **(char)** — Description ⚠️ obrigatório
- `reward_type` **(selection)** — Reward Type ⚠️ obrigatório
  > Opções: `product` (Free Product), `discount` (Discount), `shipping` (Free Shipping)
- `discount_mode` **(selection)** — Discount Mode ⚠️ obrigatório
  > Opções: `percent` (%), `per_order` (R$), `per_point` (R$ per point)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `discount` **(float)** — Discount
- `discount_applicability` **(selection)** — Discount Applicability
  > Opções: `order` (Order), `cheapest` (Cheapest Product), `specific` (Specific Products)
- `discount_product_domain` **(char)** — Discount Product Domain
- `discount_max_amount` **(monetary)** — Max Discount
  > This is the max amount this reward may discount, leave to 0 for no limit.
- `reward_product_qty` **(integer)** — Reward Product Qty
- `required_points` **(float)** — Points needed
- `clear_wallet` **(boolean)** — Clear Wallet
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `discount_product_ids` **(many2many)** — Discounted Products → `product.product`
- `discount_product_category_id` **(many2one)** — Discounted Prod. Categories → `product.category`
- `discount_product_tag_id` **(many2one)** — Discounted Prod. Tag → `product.tag`
- `all_discount_product_ids` **(many2many)** — All Discount Product 🔒 readonly → `product.product`
- `discount_line_product_id` **(many2one)** — Discount Line Product → `product.product`
  > Product used in the sales order to apply the discount. Each reward has its own product for reporting purpose
- `reward_product_id` **(many2one)** — Product → `product.product`
- `reward_product_tag_id` **(many2one)** — Product Tag → `product.tag`
- `reward_product_ids` **(many2many)** — Reward Products 🔒 readonly → `product.product`
  > These are the products that can be claimed with this rule.
- `reward_product_uom_id` **(many2one)** — Reward Product Uom 🔒 readonly → `uom.uom`

## Campos Calculados (readonly)

- `program_type` **(selection)** — Program Type 🔒 readonly
  > Opções: `coupons` (Coupons), `gift_card` (Gift Card), `loyalty` (Loyalty Cards), `promotion` (Promotions), `ewallet` (eWallet), `promo_code` (Discount Code), `buy_x_get_y` (Buy X Get Y), `next_order_coupons` (Next Order Coupons)
- `user_has_debug` **(boolean)** — User Has Debug 🔒 readonly
- `reward_product_domain` **(char)** — Reward Product Domain 🔒 readonly
- `is_global_discount` **(boolean)** — Is Global Discount 🔒 readonly
- `multi_product` **(boolean)** — Multi Product 🔒 readonly
- `point_name` **(char)** — Portal Point Name 🔒 readonly
