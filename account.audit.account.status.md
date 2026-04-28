# Account Audit Account Status — `account.audit.account.status`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `audit_id` **(many2one)** — Audit ⚠️ obrigatório → `account.return`
- `account_id` **(many2one)** — Account ⚠️ obrigatório → `account.account`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `status` **(selection)** — Status
  > Opções: `todo` (To Review), `reviewed` (Reviewed), `supervised` (Supervised), `anomaly` (Anomaly)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
