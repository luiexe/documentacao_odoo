# Snailmail Letter — `snailmail.letter`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `model` **(char)** — Model ⚠️ obrigatório
- `res_id` **(integer)** — Document ID ⚠️ obrigatório
- `partner_id` **(many2one)** — Recipient ⚠️ obrigatório → `res.partner`
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `state` **(selection)** — Status ⚠️ obrigatório 🔒 readonly
  > When a letter is created, the status is 'Pending'. If the letter is correctly sent, the status goes in 'Sent', If not, it will got in state 'Error' and the error message will be displayed in the field 'Error Message'.
  > Opções: `pending` (In Queue), `sent` (Sent), `error` (Error), `canceled` (Cancelled)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(boolean)** — Color
- `cover` **(boolean)** — Cover Page
- `duplex` **(boolean)** — Both side
- `error_code` **(selection)** — Error
  > Opções: `MISSING_REQUIRED_FIELDS` (MISSING_REQUIRED_FIELDS), `CREDIT_ERROR` (CREDIT_ERROR), `TRIAL_ERROR` (TRIAL_ERROR), `NO_PRICE_AVAILABLE` (NO_PRICE_AVAILABLE), `FORMAT_ERROR` (FORMAT_ERROR), `UNKNOWN_ERROR` (UNKNOWN_ERROR), `ATTACHMENT_ERROR` (ATTACHMENT_ERROR)
- `info_msg` **(html)** — Information
- `street` **(char)** — Street
- `street2` **(char)** — Street2
- `zip` **(char)** — Zip
- `city` **(char)** — City
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — Sent by → `res.users`
- `report_template` **(many2one)** — Optional report to print and attach → `ir.actions.report`
- `attachment_id` **(many2one)** — Attachment → `ir.attachment`
- `message_id` **(many2one)** — Snailmail Status Message → `mail.message`
- `notification_ids` **(one2many)** — Notifications → `mail.notification`
- `state_id` **(many2one)** — State → `res.country.state`
- `country_id` **(many2one)** — Country → `res.country`

## Campos Calculados (readonly)

- `attachment_datas` **(binary)** — Document 🔒 readonly
- `attachment_fname` **(char)** — Attachment Filename 🔒 readonly
- `reference` **(char)** — Related Record 🔒 readonly
