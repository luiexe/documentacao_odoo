# Marketing Trace — `marketing.trace`

**Ordenação padrão:** `schedule_date DESC, id ASC`

---

## Campos Obrigatórios

- `participant_id` **(many2one)** — Participant ⚠️ obrigatório → `marketing.participant`
- `activity_id` **(many2one)** — Activity ⚠️ obrigatório → `marketing.activity`
- `state` **(selection)** — State ⚠️ obrigatório
  > Opções: `scheduled` (Scheduled), `processed` (Processed), `rejected` (Rejected), `canceled` (Cancelled), `error` (Error)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_id` **(integer)** — Document ID
- `is_test` **(boolean)** — Test Trace 🔒 readonly
- `schedule_date` **(datetime)** — Schedule Date
- `state_msg` **(char)** — Error message
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Parent → `marketing.trace`
- `child_ids` **(one2many)** — Direct child traces → `marketing.trace`
- `mailing_trace_ids` **(one2many)** — Mass mailing statistics → `mailing.trace`
- `whatsapp_message_id` **(many2one)** — Marketing Template → `whatsapp.message`

## Campos Calculados (readonly)

- `activity_type` **(selection)** — Activity Type 🔒 readonly
  > Opções: `email` (Email), `action` (Server Action), `whatsapp` (Whatsapp Message)
- `trigger_type` **(selection)** — Trigger Type 🔒 readonly
  > Opções: `begin` (beginning of workflow), `activity` (another activity), `mail_open` (Mail: opened), `mail_not_open` (Mail: not opened), `mail_reply` (Mail: replied), `mail_not_reply` (Mail: not replied), `mail_click` (Mail: clicked), `mail_not_click` (Mail: not clicked), `mail_bounce` (Mail: bounced), `whatsapp_click` (Whatsapp: click), `whatsapp_not_click` (Whatsapp: not click), `whatsapp_read` (Whatsapp: opened), `whatsapp_not_read` (Whatsapp: not opened), `whatsapp_replied` (Whatsapp: replied), `whatsapp_not_replied` (Whatsapp: not replied), `whatsapp_bounced` (Whatsapp: message bounced)
- `mailing_trace_status` **(selection)** — Status 🔒 readonly
  > Opções: `outgoing` (Outgoing), `process` (Processing), `pending` (Sent), `sent` (Delivered), `open` (Opened), `reply` (Replied), `bounce` (Bounced), `error` (Exception), `cancel` (Cancelled)
- `links_click_datetime` **(datetime)** — Links Click Datetime 🔒 readonly
