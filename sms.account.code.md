# SMS Account Verification Code Wizard — `sms.account.code`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `account_id` **(many2one)** — Account ⚠️ obrigatório → `iap.account`
- `verification_code` **(char)** — Verification Code ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
