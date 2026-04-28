# Rules for the reconciliation model — `account.reconcile.model.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `sequence` **(integer)** — Sequence ⚠️ obrigatório
- `amount_type` **(selection)** — Amount Type ⚠️ obrigatório
  > Opções: `fixed` (Fixed), `percentage` (Percentage of balance), `percentage_st_line` (Percentage of statement line), `regex` (From label)
- `amount_string` **(char)** — Amount ⚠️ obrigatório
  > Value for the amount of the writeoff line     * Percentage: Percentage of the balance, between 0 and 100.     * Fixed: The fixed value of the writeoff. The amount will count as a debit if it is negative, as a credit if it is positive.     * From Label: There is no need for regex delimiter, only the regex is needed. For instance if you want to extract the amount from R:9672938 10/07 AX 9415126318 T:5L:NA BRT: 3358,07 C: You could enter BRT: ([\d,]+)     If the label is "01870912 0009065 00115" and you need the amount in decimal     format (e.g. 90.65), you can use a regex with capturing groups, for example:         \s+0*(\d+?)(\d{2})(?=\s)     In this case:     • the first group captures the integer part     • the second group captures the decimal part (last two digits)     

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `label` **(char)** — Label
- `amount` **(float)** — Float Amount 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `distribution_analytic_account_ids` **(many2many)** — Distribution Analytic Account 🔒 readonly → `account.analytic.account`
- `model_id` **(many2one)** — Model 🔒 readonly → `account.reconcile.model`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `account_id` **(many2one)** — Account → `account.account`
- `partner_id` **(many2one)** — Partner → `res.partner`
- `tax_ids` **(many2many)** — Taxes → `account.tax`
