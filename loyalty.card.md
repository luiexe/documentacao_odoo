# Loyalty Coupon — `loyalty.card`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `code` **(char)** — Code ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `points` **(float)** — Points
- `expiration_date` **(date)** — Expiration Date
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `program_id` **(many2one)** — Program → `loyalty.program`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `partner_id` **(many2one)** — Partner → `res.partner`
- `history_ids` **(one2many)** — History 🔒 readonly → `loyalty.history`
- `order_id` **(many2one)** — Order Reference 🔒 readonly → `sale.order`
  > The sales order from which coupon is generated
- `order_id_partner_id` **(many2one)** — Sale Order Customer 🔒 readonly → `res.partner`

## Campos Calculados (readonly)

- `program_type` **(selection)** — Program Type 🔒 readonly
  > Opções: `coupons` (Coupons), `gift_card` (Gift Card), `loyalty` (Loyalty Cards), `promotion` (Promotions), `ewallet` (eWallet), `promo_code` (Discount Code), `buy_x_get_y` (Buy X Get Y), `next_order_coupons` (Next Order Coupons)
- `point_name` **(char)** — Portal Point Name 🔒 readonly
- `points_display` **(char)** — Points Display 🔒 readonly
- `use_count` **(integer)** — Use Count 🔒 readonly
