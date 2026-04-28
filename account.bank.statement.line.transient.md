# Transient model for bank statement line — `account.bank.statement.line.transient`

**Ordenação padrão:** `date asc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `date` **(date)** — Date
- `amount` **(monetary)** — Amount 🔒 readonly
- `online_transaction_identifier` **(char)** — Online Transaction Identifier 🔒 readonly
- `payment_ref` **(char)** — Payment Ref 🔒 readonly
- `account_number` **(char)** — Account Number 🔒 readonly
- `partner_name` **(char)** — Partner Name 🔒 readonly
- `transaction_details` **(json)** — Transaction Details 🔒 readonly
- `state` **(selection)** — State 🔒 readonly
  > Opções: `pending` (Pending), `posted` (Posted)
- `amount_currency` **(monetary)** — Amount in Currency
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `journal_id` **(many2one)** — Journal 🔒 readonly → `account.journal`
- `online_account_id` **(many2one)** — Account Online Account 🔒 readonly → `account.online.account`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company → `res.company`
- `foreign_currency_id` **(many2one)** — Foreign Currency → `res.currency`
