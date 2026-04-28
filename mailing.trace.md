# Mailing Statistics — `mailing.trace`

**Ordenação padrão:** `create_date DESC`

---

## Campos Obrigatórios

- `trace_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `mail` (Email)
- `model` **(char)** — Document model ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `is_test_trace` **(boolean)** — Generated for testing
- `mail_mail_id_int` **(integer)** — Mail ID (tech)
  > ID of the related mail_mail. This field is an integer field because the related mail_mail can be deleted separately from its statistics. However the ID is needed for several action and controllers.
- `email` **(char)** — Email
  > Normalized email address
- `message_id` **(char)** — Message-ID
- `res_id` **(many2one_reference)** — Document ID
- `sent_datetime` **(datetime)** — Sent On
- `open_datetime` **(datetime)** — Opened On
- `reply_datetime` **(datetime)** — Replied On
- `trace_status` **(selection)** — Status
  > Opções: `outgoing` (Outgoing), `process` (Processing), `pending` (Sent), `sent` (Delivered), `open` (Opened), `reply` (Replied), `bounce` (Bounced), `error` (Exception), `cancel` (Cancelled)
- `failure_type` **(selection)** — Failure type
  > Opções: `unknown` (Unknown error), `mail_bounce` (Bounce), `mail_spam` (Detected As Spam), `mail_email_invalid` (Invalid email address), `mail_email_missing` (Missing email address), `mail_from_invalid` (Invalid from address), `mail_from_missing` (Missing from address), `mail_smtp` (Connection failed (outgoing mail server problem)), `mail_bl` (Blacklisted Address), `mail_dup` (Duplicated Email), `mail_optout` (Opted Out)
- `failure_reason` **(text)** — Failure reason 🔒 readonly
- `links_click_datetime` **(datetime)** — Clicked On
  > Stores last click datetime in case of multi clicks.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `mail_mail_id` **(many2one)** — Mail → `mail.mail`
- `medium_id` **(many2one)** — Medium 🔒 readonly → `utm.medium`
  > UTM Medium: delivery method (email, sms, ...)
- `source_id` **(many2one)** — Source 🔒 readonly → `utm.source`
- `mass_mailing_id` **(many2one)** — Mailing → `mailing.mailing`
- `campaign_id` **(many2one)** — Campaign 🔒 readonly → `utm.campaign`
- `links_click_ids` **(one2many)** — Links click → `link.tracker.click`
- `marketing_trace_id` **(many2one)** — Marketing Trace → `marketing.trace`
