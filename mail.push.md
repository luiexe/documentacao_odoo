# Push Notifications — `mail.push`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mail_push_device_id` **(many2one)** — devices ⚠️ obrigatório → `mail.push.device`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `payload` **(text)** — Payload
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
