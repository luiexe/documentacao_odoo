# Link SMS to mailing/sms tracking models — `sms.tracker`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `sms_uuid` **(char)** — SMS uuid ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `mail_notification_id` **(many2one)** — Mail Notification → `mail.notification`
