# Mapping of account codes per company — `account.code.mapping`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code` **(char)** — Code

## Relacionamentos

- `account_id` **(many2one)** — Account 🔒 readonly → `account.account`
- `company_id` **(many2one)** — Company → `res.company`
