# Event Alarm — `calendar.alarm`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `alarm_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `notification` (Notification), `email` (Email), `sms` (SMS Text Message), `whatsapp` (WhatsApp Message)
- `duration` **(integer)** — Remind Before ⚠️ obrigatório
- `interval` **(selection)** — Unit ⚠️ obrigatório
  > Opções: `minutes` (Minutes), `hours` (Hours), `days` (Days)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `duration_minutes` **(integer)** — Duration in minutes 🔒 readonly
- `body` **(text)** — Additional Message
  > Additional message that would be sent with the notification for the reminder
- `notify_responsible` **(boolean)** — Notify Responsible
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `default_for_new_appointment_type` **(boolean)** — New Appointments Default
  > Use as default for new Appointment Types

## Relacionamentos

- `mail_template_id` **(many2one)** — Email Template → `mail.template`
  > Template used to render mail reminder content.
- `sms_template_id` **(many2one)** — SMS Template → `sms.template`
  > Template used to render SMS reminder content.
- `wa_template_id` **(many2one)** — WhatsApp Template → `whatsapp.template`
  > Template used to render WhatsApp reminder content.
