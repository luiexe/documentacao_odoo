# Loan Line — `account.loan.line`

**Ordenação padrão:** `date, id`

---

## Campos Obrigatórios

- `loan_id` **(many2one)** — Loan ⚠️ obrigatório → `account.loan`
- `date` **(date)** — Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `principal` **(monetary)** — Principal
- `interest` **(monetary)** — Interest
- `payment` **(monetary)** — Payment 🔒 readonly
- `long_term_theoretical_balance` **(monetary)** — Long-Term 🔒 readonly
- `short_term_theoretical_balance` **(monetary)** — Short-Term 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `loan_asset_group_id` **(many2one)** — Asset Group 🔒 readonly → `account.asset.group`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `generated_move_ids` **(one2many)** — Generated Entries 🔒 readonly → `account.move`
  > Entries that we generated from this loan line

## Campos Calculados (readonly)

- `sequence` **(integer)** — # 🔒 readonly
- `loan_name` **(char)** — Name 🔒 readonly
- `loan_state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Draft), `running` (Running), `closed` (Closed), `cancelled` (Cancelled)
- `loan_date` **(date)** — Loan Date 🔒 readonly
- `active` **(boolean)** — Active 🔒 readonly
- `outstanding_balance` **(monetary)** — Outstanding Balance 🔒 readonly
- `is_payment_move_posted` **(boolean)** — Is Payment Move Posted 🔒 readonly
