# Loan Compute Wizard — `account.loan.compute.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `loan_id` **(many2one)** — Loan ⚠️ obrigatório → `account.loan`
- `loan_amount` **(monetary)** — Loan Amount ⚠️ obrigatório
- `interest_rate` **(float)** — Interest Rate ⚠️ obrigatório
- `loan_term` **(integer)** — Loan Term ⚠️ obrigatório
- `start_date` **(date)** — Start Date ⚠️ obrigatório
- `first_payment_date` **(date)** — First Payment ⚠️ obrigatório
- `payment_end_of_month` **(selection)** — Payment ⚠️ obrigatório
  > Opções: `end_of_month` (End of Month), `at_anniversary` (At Anniversary)
- `compounding_method` **(selection)** — Compounding Method ⚠️ obrigatório
  > Opções: `30A/360` (30A/360), `30U/360` (30U/360), `30E/360` (30E/360), `30E/360 ISDA` (30E/360 ISDA), `A/360` (A/360), `A/365F` (A/365F), `A/A ISDA` (A/A ISDA), `A/A AFB` (A/A AFB)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `preview` **(text)** — Preview 🔒 readonly
