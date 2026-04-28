# Fiscal Rate — `account.account.fiscal.rate`

**Ordenação padrão:** `date_from desc`

---

## Campos Obrigatórios

- `rate` **(float)** — Fiscal Rate (%) ⚠️ obrigatório
- `date_from` **(date)** — Start Date ⚠️ obrigatório
- `related_account_id` **(many2one)** — Account ⚠️ obrigatório → `account.account`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
