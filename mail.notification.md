# Message Notifications — `mail.notification`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mail_message_id` **(many2one)** — Message ⚠️ obrigatório → `mail.message`
- `notification_type` **(selection)** — Notification Type ⚠️ obrigatório
  > Opções: `inbox` (Inbox), `email` (Email), `sms` (SMS), `snail` (Snailmail)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `mail_email_address` **(char)** — Mail Email Address
  > Recipient email address
- `notification_status` **(selection)** — Status
  > Opções: `ready` (Ready to Send), `process` (Processing), `pending` (Sent), `sent` (Delivered), `bounce` (Bounced), `exception` (Exception), `canceled` (Cancelled)
- `is_read` **(boolean)** — Is Read
- `read_date` **(datetime)** — Read Date
- `failure_type` **(selection)** — Failure type
  > Opções: `unknown` (Unknown error), `mail_bounce` (Bounce), `mail_spam` (Detected As Spam), `mail_email_invalid` (Invalid email address), `mail_email_missing` (Missing email address), `mail_from_invalid` (Invalid from address), `mail_from_missing` (Missing from address), `mail_smtp` (Connection failed (outgoing mail server problem)), `mail_bl` (Blacklisted Address), `mail_optout` (Opted Out), `mail_dup` (Duplicated Email), `sms_number_missing` (Missing Number), `sms_number_format` (Wrong Number Format), `sms_credit` (Insufficient Credit), `sms_country_not_supported` (Country Not Supported), `sms_registration_needed` (Country-specific Registration Required), `sms_server` (Server Error), `sms_acc` (Unregistered Account), `sms_expired` (Expired), `sms_invalid_destination` (Invalid Destination), `sms_not_allowed` (Not Allowed), `sms_not_delivered` (Not Delivered), `sms_rejected` (Rejected), `sn_credit` (Snailmail Credit Error), `sn_trial` (Snailmail Trial Error), `sn_price` (Snailmail No Price Available), `sn_fields` (Snailmail Missing Required Fields), `sn_format` (Snailmail Format Error), `sn_error` (Snailmail Unknown Error)
- `failure_reason` **(text)** — Failure reason
- `sms_id_int` **(integer)** — SMS ID
- `sms_number` **(char)** — SMS Number

## Relacionamentos

- `author_id` **(many2one)** — Author → `res.partner`
- `mail_mail_id` **(many2one)** — Mail → `mail.mail`
  > Optional mail_mail ID. Used mainly to optimize searches.
- `res_partner_id` **(many2one)** — Recipient → `res.partner`
- `sms_id` **(many2one)** — SMS 🔒 readonly → `sms.sms`
- `sms_tracker_ids` **(one2many)** — SMS Trackers → `sms.tracker`
- `letter_id` **(many2one)** — Snailmail Letter → `snailmail.letter`
