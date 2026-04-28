# Generate Coupons — `loyalty.generate.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `program_id` **(many2one)** — Program ⚠️ obrigatório → `loyalty.program`
- `mode` **(selection)** — For ⚠️ obrigatório
  > Opções: `anonymous` (Anonymous Customers), `selected` (Selected Customers)
- `points_granted` **(float)** — Grant ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `coupon_qty` **(integer)** — Quantity
- `valid_until` **(date)** — Valid Until
- `description` **(text)** — Description
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `customer_ids` **(many2many)** — Customers → `res.partner`
- `customer_tag_ids` **(many2many)** — Customer Tags → `res.partner.category`

## Campos Calculados (readonly)

- `program_type` **(selection)** — Program Type 🔒 readonly
  > Opções: `coupons` (Coupons), `gift_card` (Gift Card), `loyalty` (Loyalty Cards), `promotion` (Promotions), `ewallet` (eWallet), `promo_code` (Discount Code), `buy_x_get_y` (Buy X Get Y), `next_order_coupons` (Next Order Coupons)
- `points_name` **(char)** — Portal Point Name 🔒 readonly
- `will_send_mail` **(boolean)** — Will Send Mail 🔒 readonly
- `confirmation_message` **(char)** — Confirmation Message 🔒 readonly
