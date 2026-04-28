# Payment Refund Wizard — `payment.refund.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount_to_refund` **(monetary)** — Refund Amount
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `payment_id` **(many2one)** — Payment 🔒 readonly → `account.payment`
- `transaction_id` **(many2one)** — Payment Transaction 🔒 readonly → `payment.transaction`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `payment_amount` **(monetary)** — Payment Amount 🔒 readonly
- `refunded_amount` **(monetary)** — Refunded Amount 🔒 readonly
- `amount_available_for_refund` **(monetary)** — Maximum Refund Allowed 🔒 readonly
- `support_refund` **(selection)** — Refund 🔒 readonly
  > Opções: `none` (Unsupported), `full_only` (Full Only), `partial` (Partial)
- `has_pending_refund` **(boolean)** — Has a pending refund 🔒 readonly
