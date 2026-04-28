# Payment Transaction — `payment.transaction`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `provider_id` **(many2one)** — Provider ⚠️ obrigatório 🔒 readonly → `payment.provider`
- `payment_method_id` **(many2one)** — Payment Method ⚠️ obrigatório 🔒 readonly → `payment.method`
- `reference` **(char)** — Reference ⚠️ obrigatório 🔒 readonly
  > The internal reference of the transaction
- `amount` **(monetary)** — Amount ⚠️ obrigatório 🔒 readonly
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório 🔒 readonly → `res.currency`
- `state` **(selection)** — Status ⚠️ obrigatório 🔒 readonly
  > Opções: `draft` (Draft), `pending` (Pending), `authorized` (Authorized), `done` (Confirmed), `cancel` (Canceled), `error` (Error)
- `partner_id` **(many2one)** — Customer ⚠️ obrigatório 🔒 readonly → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `provider_reference` **(char)** — Provider Reference 🔒 readonly
  > The provider reference of the transaction
- `state_message` **(text)** — Message 🔒 readonly
  > The complementary information message about the state
- `last_state_change` **(datetime)** — Last State Change Date 🔒 readonly
- `operation` **(selection)** — Operation 🔒 readonly
  > Opções: `online_redirect` (Online payment with redirection), `online_direct` (Online direct payment), `online_token` (Online payment by token), `validation` (Validation of the payment method), `offline` (Offline payment by token), `refund` (Refund)
- `is_live` **(boolean)** — Production Environment
  > Whether the transaction happened in a production environment. False for transactions created before this tracking was implemented.
- `is_post_processed` **(boolean)** — Is Post-processed
  > Has the payment been post-processed
- `tokenize` **(boolean)** — Create Token
  > Whether a payment token should be created when post-processing the transaction
- `landing_route` **(char)** — Landing Route
  > The route the user is redirected to after the transaction
- `partner_name` **(char)** — Partner Name
- `partner_lang` **(selection)** — Language
  > Opções: `en_US` (English (US)), `pt_BR` (Portuguese (BR) / Português (BR))
- `partner_email` **(char)** — Email
- `partner_address` **(char)** — Address
- `partner_zip` **(char)** — Zip
- `partner_city` **(char)** — City
- `partner_phone` **(char)** — Phone
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `is_donation` **(boolean)** — Is donation

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `primary_payment_method_id` **(many2one)** — Primary Payment Method 🔒 readonly → `payment.method`
- `token_id` **(many2one)** — Payment Token 🔒 readonly → `payment.token`
- `source_transaction_id` **(many2one)** — Source Transaction 🔒 readonly → `payment.transaction`
  > The source transaction of the related child transactions
- `child_transaction_ids` **(one2many)** — Child Transactions 🔒 readonly → `payment.transaction`
  > The child transactions of the transaction.
- `partner_state_id` **(many2one)** — State → `res.country.state`
- `partner_country_id` **(many2one)** — Country → `res.country`
- `payment_id` **(many2one)** — Payment 🔒 readonly → `account.payment`
- `invoice_ids` **(many2many)** — Invoices 🔒 readonly → `account.move`
- `sale_order_ids` **(many2many)** — Sales Orders 🔒 readonly → `sale.order`

## Campos Calculados (readonly)

- `provider_code` **(selection)** — Provider Code 🔒 readonly
  > The technical code of this payment provider.
  > Opções: `none` (No Provider Set), `custom` (Custom), `demo` (Demo), `mercado_pago` (Mercado Pago), `stripe` (Stripe)
- `payment_method_code` **(char)** — Payment Method Code 🔒 readonly
  > The technical code of this payment method.
- `refunds_count` **(integer)** — Refunds Count 🔒 readonly
- `capture_manually` **(boolean)** — Capture Amount Manually 🔒 readonly
  > Capture the amount from Odoo, when the delivery is completed. Use this if you want to charge your customers cards only when you are sure you can ship the goods to them.
- `invoices_count` **(integer)** — Invoices Count 🔒 readonly
- `sale_order_ids_nbr` **(integer)** — # of Sales Orders 🔒 readonly
