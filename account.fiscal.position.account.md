# Accounts Mapping of Fiscal Position — `account.fiscal.position.account`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `position_id` **(many2one)** — Fiscal Position ⚠️ obrigatório → `account.fiscal.position`
- `account_src_id` **(many2one)** — Account on Product ⚠️ obrigatório → `account.account`
- `account_dest_id` **(many2one)** — Account to Use Instead ⚠️ obrigatório → `account.account`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
