# Bank Account Allocation Line (Wizard) — `hr.bank.account.allocation.wizard.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `wizard_id` **(many2one)** — Wizard ⚠️ obrigatório → `hr.bank.account.allocation.wizard`
- `bank_account_id` **(many2one)** — Bank Account ⚠️ obrigatório 🔒 readonly → `res.partner.bank`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount` **(float)** — Amount
- `amount_type` **(selection)** — Amount Type
  > Opções: `percentage` (Percentage), `fixed` (Fixed)
- `trusted` **(boolean)** — Trusted
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `acc_number` **(char)** — Account Number 🔒 readonly
- `symbol` **(char)** — Symbol 🔒 readonly
