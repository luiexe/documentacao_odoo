# Payment Method — `payment.method`

**Ordenação padrão:** `active desc, sequence, name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `code` **(char)** — Code ⚠️ obrigatório
  > The technical code of this payment method.
- `image` **(binary)** — Image ⚠️ obrigatório
  > The base image used for this payment method; in a 64x64 px format.
- `support_manual_capture` **(selection)** — Manual Capture ⚠️ obrigatório
  > The payment is authorized and captured in two steps instead of one.
  > Opções: `none` (Unsupported), `full_only` (Full Only), `partial` (Full & Partial)
- `support_refund` **(selection)** — Refund ⚠️ obrigatório
  > Refund is a feature allowing to refund customers directly from the payment in Odoo.
  > Opções: `none` (Unsupported), `full_only` (Full Only), `partial` (Full & Partial)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
- `image_payment_form` **(binary)** — The resized image displayed on the payment form. 🔒 readonly
  > The base image used for this payment method; in a 64x64 px format.
- `support_tokenization` **(boolean)** — Tokenization
  > Tokenization is the process of saving the payment details as a token that can later be reused without having to enter the payment details again.
- `support_express_checkout` **(boolean)** — Express Checkout
  > Express checkout allows customers to pay faster by using a payment method that provides all required billing and shipping information, thus allowing to skip the checkout process.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `l10n_br_edi_payment_method` **(selection)** — Payment Method Brazil
  > Brazil: expected payment method to be used.
  > Opções: `01` (Money), `02` (Check), `03` (Credit Card), `04` (Debit Card), `05` (Store Credit), `10` (Food voucher), `11` (Meal Voucher), `12` (Gift certificate), `13` (Fuel Voucher), `14` (Duplicate Mercantil), `15` (Boleto Bancario), `16` (Bank Deposit), `17` (Instant Payment (PIX)), `18` (Bank transfer, Digital Wallet), `19` (Loyalty program, Cashback, Virtual Credit), `90` (No Payment), `99` (Others)

## Relacionamentos

- `primary_payment_method_id` **(many2one)** — Primary Payment Method → `payment.method`
  > The primary payment method of the current payment method, if the latter is a brand. For example, "Card" is the primary payment method of the card brand "VISA".
- `brand_ids` **(one2many)** — Brands → `payment.method`
  > The brands of the payment methods that will be displayed on the payment form.
- `provider_ids` **(many2many)** — Providers → `payment.provider`
  > The list of providers supporting this payment method.
- `supported_country_ids` **(many2many)** — Countries → `res.country`
  > The list of countries in which this payment method can be used (if the provider allows it). In other countries, this payment method is not available to customers.
- `supported_currency_ids` **(many2many)** — Currencies → `res.currency`
  > The list of currencies for that are supported by this payment method (if the provider allows it). When paying with another currency, this payment method is not available to customers.

## Campos Calculados (readonly)

- `is_primary` **(boolean)** — Is Primary Payment Method 🔒 readonly
