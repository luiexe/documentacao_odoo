# Generic Payment Wizard with QR Code — `qr.code.payment.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `return_id` **(many2one)** — Return ⚠️ obrigatório → `account.return`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount_to_pay` **(monetary)** — Amount To Pay
- `is_recoverable` **(boolean)** — Is Recoverable
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `partner_id` **(many2one)** — Account Holder 🔒 readonly → `res.partner`
- `partner_bank_id` **(many2one)** — Partner Bank → `res.partner.bank`
- `currency_id` **(many2one)** — Amount To Pay Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `acc_number` **(char)** — IBAN 🔒 readonly
- `communication` **(char)** — Communication 🔒 readonly
- `qr_code` **(html)** — Qr Code 🔒 readonly
