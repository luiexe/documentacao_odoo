# WhatsApp Messages — `whatsapp.message`

**Ordenação padrão:** `id desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `mobile_number` **(char)** — Sent To
- `mobile_number_formatted` **(char)** — Mobile Number Formatted
- `message_type` **(selection)** — Message Type
  > Opções: `outbound` (Outbound), `inbound` (Inbound)
- `state` **(selection)** — State
  > Opções: `outgoing` (In Queue), `sent` (Sent), `delivered` (Delivered), `read` (Read), `replied` (Replied), `received` (Received), `error` (Failed), `bounced` (Bounced), `cancel` (Cancelled)
- `failure_type` **(selection)** — Failure Type
  > Opções: `account` (Account Error), `blacklisted` (Blacklisted Phone Number), `network` (Network Error), `outdated_channel` (The channel is no longer active), `phone_invalid` (Wrong Number Format), `template` (Template Quality Rating Too Low), `unknown` (Unknown Error), `whatsapp_recoverable` (Identified Error), `whatsapp_unrecoverable` (Other Technical Error)
- `failure_reason` **(char)** — Failure Reason
  > Usually an error message from Whatsapp
- `free_text_json` **(json)** — Free Text Template Parameters
- `msg_uid` **(char)** — WhatsApp Message ID
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `links_click_datetime` **(datetime)** — Clicked On
  > Stores last click datetime in case of multi clicks.

## Relacionamentos

- `wa_template_id` **(many2one)** — Wa Template → `whatsapp.template`
- `wa_account_id` **(many2one)** — WhatsApp Business Account → `whatsapp.account`
- `parent_id` **(many2one)** — Response To → `whatsapp.message`
- `mail_message_id` **(many2one)** — Mail Message → `mail.message`
- `marketing_trace_ids` **(one2many)** — Marketing Trace → `marketing.trace`

## Campos Calculados (readonly)

- `body` **(html)** — Body 🔒 readonly
