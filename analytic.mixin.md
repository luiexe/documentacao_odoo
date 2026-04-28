# Analytic Mixin — `analytic.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
