# Outgoing SMS — `sms.sms`

**Ordenação padrão:** `id DESC`

---

## Campos Obrigatórios

- `state` **(selection)** — SMS Status ⚠️ obrigatório 🔒 readonly
  > Opções: `outgoing` (In Queue), `process` (Processing), `pending` (Sent), `sent` (Delivered), `error` (Error), `canceled` (Cancelled)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `uuid` **(char)** — UUID 🔒 readonly
  > Alternate way to identify a SMS record, used for delivery reports
- `number` **(char)** — Number
- `body` **(text)** — Body
- `failure_type` **(selection)** — Failure Type
  > Opções: `unknown` (Unknown error), `sms_number_missing` (Missing Number), `sms_number_format` (Wrong Number Format), `sms_country_not_supported` (Country Not Supported), `sms_registration_needed` (Country-specific Registration Required), `sms_credit` (Insufficient Credit), `sms_server` (Server Error), `sms_acc` (Unregistered Account), `sms_blacklist` (Blacklisted), `sms_duplicate` (Duplicate), `sms_optout` (Opted Out)
- `to_delete` **(boolean)** — Marked for deletion
  > Will automatically be deleted, while notifications will not be deleted in any case.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Customer → `res.partner`
- `mail_message_id` **(many2one)** — Mail Message → `mail.message`
- `sms_tracker_id` **(many2one)** — SMS trackers 🔒 readonly → `sms.tracker`
