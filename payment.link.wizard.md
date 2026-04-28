# Generate Sales Payment Link — `payment.link.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_model` **(char)** — Related Document Model ⚠️ obrigatório
- `res_id` **(integer)** — Related Document ID ⚠️ obrigatório
- `amount` **(monetary)** — Amount ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `amount_max` **(monetary)** — Amount Max
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `open_installments` **(json)** — Open Installments
- `has_eligible_epd` **(boolean)** — Has Eligible Epd
- `discount_date` **(date)** — Discount Date
- `amount_paid` **(monetary)** — Already Paid 🔒 readonly
- `prepayment_amount` **(monetary)** — Prepayment Amount

## Relacionamentos

- `currency_id` **(many2one)** — Currency → `res.currency`
- `partner_id` **(many2one)** — Partner → `res.partner`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `partner_email` **(char)** — Email 🔒 readonly
- `link` **(char)** — Payment Link 🔒 readonly
- `warning_message` **(char)** — Warning Message 🔒 readonly
- `can_send_whatsapp` **(boolean)** — Can Send WhatsApp 🔒 readonly
- `invoice_amount_due` **(monetary)** — Amount Due 🔒 readonly
- `open_installments_preview` **(html)** — Open Installments Preview 🔒 readonly
- `display_open_installments` **(boolean)** — Display Open Installments 🔒 readonly
- `epd_info` **(char)** — Early Payment Discount Information 🔒 readonly
- `confirmation_message` **(char)** — Confirmation Message 🔒 readonly
