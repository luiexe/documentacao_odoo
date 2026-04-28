# Payment Capture Wizard — `payment.capture.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount_to_capture` **(monetary)** — Amount To Capture
- `void_remaining_amount` **(boolean)** — Void Remaining Amount
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `transaction_ids` **(many2many)** — Transaction 🔒 readonly → `payment.transaction`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `authorized_amount` **(monetary)** — Authorized Amount 🔒 readonly
- `captured_amount` **(monetary)** — Already Captured 🔒 readonly
- `voided_amount` **(monetary)** — Already Voided 🔒 readonly
- `available_amount` **(monetary)** — Maximum Capture Allowed 🔒 readonly
- `is_amount_to_capture_valid` **(boolean)** — Is Amount To Capture Valid 🔒 readonly
- `support_partial_capture` **(boolean)** — Support Partial Capture 🔒 readonly
  > Whether each of the transactions' provider supports the partial capture.
- `has_draft_children` **(boolean)** — Has Draft Children 🔒 readonly
- `has_remaining_amount` **(boolean)** — Has Remaining Amount 🔒 readonly
