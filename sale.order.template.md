# Quotation Template — `sale.order.template`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Quotation Template ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If unchecked, it will allow you to hide the quotation template without removing it.
- `note` **(html)** — Terms and conditions
- `sequence` **(integer)** — Sequence
- `number_of_days` **(integer)** — Quotation Duration
  > Number of days for the validity date computation of the quotation
- `require_signature` **(boolean)** — Online Signature
  > Request a online signature to the customer in order to confirm orders automatically.
- `require_payment` **(boolean)** — Online Payment
  > Request an online payment to the customer in order to confirm orders automatically.
- `prepayment_percent` **(float)** — Prepayment percentage
  > The percentage of the amount needed to be paid to confirm quotations.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `mail_template_id` **(many2one)** — Confirmation Mail → `mail.template`
  > This e-mail template will be sent on confirmation. Leave empty to send nothing.
- `sale_order_template_line_ids` **(one2many)** — Lines → `sale.order.template.line`
- `journal_id` **(many2one)** — Invoicing Journal → `account.journal`
  > If set, SO with this template will invoice in this journal; otherwise the sales journal with the lowest sequence is used.
- `quotation_document_ids` **(many2many)** — Headers and footers → `quotation.document`
- `spreadsheet_template_id` **(many2one)** — Quote calculator → `sale.order.spreadsheet`
