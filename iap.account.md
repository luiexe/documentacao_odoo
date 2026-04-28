# IAP Account — `iap.account`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `service_id` **(many2one)** — Service ⚠️ obrigatório → `iap.service`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `service_locked` **(boolean)** — Service Locked
- `account_token` **(char)** — Account Token
  > Account token is your authentication key for this service. Do not share it.
- `balance` **(char)** — Balance 🔒 readonly
- `warning_threshold` **(float)** — Email Alert Threshold
- `state` **(selection)** — State 🔒 readonly
  > Opções: `banned` (Banned), `registered` (Registered), `unregistered` (Unregistered)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `sender_name` **(char)** — Sender Name 🔒 readonly
  > This is the name that will be displayed as the sender of the SMS.

## Relacionamentos

- `company_ids` **(many2many)** — Company → `res.company`
- `warning_user_ids` **(many2many)** — Email Alert Recipients → `res.users`

## Campos Calculados (readonly)

- `service_name` **(char)** — Technical Name 🔒 readonly
- `description` **(char)** — Description 🔒 readonly
