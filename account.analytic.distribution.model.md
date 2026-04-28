# Analytic Distribution Model — `account.analytic.distribution.model`

**Ordenação padrão:** `sequence, id desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `account_prefix` **(char)** — Accounts Prefix
  > This analytic distribution will apply to all financial accounts sharing the prefix specified.

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `partner_id` **(many2one)** — Partner → `res.partner`
  > Select a partner for which the analytic distribution will be used (e.g. create new customer invoice or Sales order if we select this partner, it will automatically take this as an analytic account)
- `partner_category_id` **(many2one)** — Partner Category → `res.partner.category`
  > Select a partner category for which the analytic distribution will be used (e.g. create new customer invoice or Sales order if we select this partner, it will automatically take this as an analytic account)
- `company_id` **(many2one)** — Company → `res.company`
  > Select a company for which the analytic distribution will be used (e.g. create new customer invoice or Sales order if we select this company, it will automatically take this as an analytic account)
- `product_id` **(many2one)** — Product → `product.product`
  > Select a product for which the analytic distribution will be used (e.g. create new customer invoice or Sales order if we select this product, it will automatically take this as an analytic account)
- `product_categ_id` **(many2one)** — Product Category → `product.category`
  > Select a product category which will use analytic account specified in analytic default (e.g. create new customer invoice or Sales order if we select this product, it will automatically take this as an analytic account)

## Campos Calculados (readonly)

- `prefix_placeholder` **(char)** — Prefix Placeholder 🔒 readonly
