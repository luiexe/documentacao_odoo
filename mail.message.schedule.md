# Scheduled Messages — `mail.message.schedule`

**Ordenação padrão:** `scheduled_datetime DESC, id DESC`

---

## Campos Obrigatórios

- `mail_message_id` **(many2one)** — Message ⚠️ obrigatório → `mail.message`
- `scheduled_datetime` **(datetime)** — Scheduled Send Date ⚠️ obrigatório
  > Datetime at which notification should be sent.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `notification_parameters` **(text)** — Notification Parameter
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
