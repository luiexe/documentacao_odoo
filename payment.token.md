# Payment Token — `payment.token`

**Ordenação padrão:** `partner_id, id desc`

---

## Campos Obrigatórios

- `provider_id` **(many2one)** — Provider ⚠️ obrigatório → `payment.provider`
- `payment_method_id` **(many2one)** — Payment Method ⚠️ obrigatório 🔒 readonly → `payment.method`
- `partner_id` **(many2one)** — Partner ⚠️ obrigatório → `res.partner`
- `provider_ref` **(char)** — Provider Reference ⚠️ obrigatório
  > The provider reference of the token of the transaction.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `payment_details` **(char)** — Payment Details
  > The clear part of the payment method's payment details.
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `demo_simulated_state` **(selection)** — Simulated State
  > The state in which transactions created from this token should be set.
  > Opções: `pending` (Pending), `done` (Confirmed), `cancel` (Canceled), `error` (Error)
- `mercado_pago_customer_id` **(char)** — Mercado Pago Customer 🔒 readonly
- `stripe_payment_method` **(char)** — Stripe Payment Method ID 🔒 readonly
- `stripe_mandate` **(char)** — Stripe Mandate 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `transaction_ids` **(one2many)** — Payment Transactions → `payment.transaction`

## Campos Calculados (readonly)

- `provider_code` **(selection)** — Provider Code 🔒 readonly
  > The technical code of this payment provider.
  > Opções: `none` (No Provider Set), `custom` (Custom), `demo` (Demo), `mercado_pago` (Mercado Pago), `stripe` (Stripe)
- `payment_method_code` **(char)** — Payment Method Code 🔒 readonly
  > The technical code of this payment method.
