# WhatsApp Business Account — `whatsapp.account`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `app_uid` **(char)** — App ID ⚠️ obrigatório
- `app_secret` **(char)** — App Secret ⚠️ obrigatório
- `account_uid` **(char)** — Account ID ⚠️ obrigatório
- `phone_uid` **(char)** — Phone Number ID ⚠️ obrigatório
- `token` **(char)** — Access Token ⚠️ obrigatório
- `notify_user_ids` **(many2many)** — Notify User ⚠️ obrigatório → `res.users`
  > Users to notify when a message is received and there is no template send in last 15 days

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `active` **(boolean)** — Active
- `phone_number` **(char)** — Phone Number 🔒 readonly
  > The phone number used in the Whatsapp Business Account.
- `webhook_verify_token` **(char)** — Webhook Verify Token 🔒 readonly
- `debug_logging` **(boolean)** — Debug logging
  > Log requests in order to ease debugging
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `allowed_company_ids` **(many2many)** — Allowed Company → `res.company`

## Campos Calculados (readonly)

- `callback_url` **(char)** — Callback URL 🔒 readonly
- `templates_count` **(integer)** — Message Count 🔒 readonly
