# Payment Methods — `account.payment.method.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `payment_method_id` **(many2one)** — Payment Method ⚠️ obrigatório → `account.payment.method`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `payment_account_id` **(many2one)** — Payment Account → `account.account`
- `journal_id` **(many2one)** — Journal → `account.journal`
- `default_account_id` **(many2one)** — Default Account 🔒 readonly → `account.account`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
  > Company related to this journal
- `available_payment_method_ids` **(many2many)** — Available Payment Method 🔒 readonly → `account.payment.method`
- `payment_provider_id` **(many2one)** — Payment Provider → `payment.provider`

## Campos Calculados (readonly)

- `code` **(char)** — Code 🔒 readonly
- `payment_type` **(selection)** — Payment Type 🔒 readonly
  > Opções: `inbound` (Inbound), `outbound` (Outbound)
- `payment_provider_state` **(selection)** — State 🔒 readonly
  > In test mode, a fake payment is processed through a test payment interface. This mode is advised when setting up the provider.
  > Opções: `disabled` (Disabled), `enabled` (Enabled), `test` (Test Mode)
