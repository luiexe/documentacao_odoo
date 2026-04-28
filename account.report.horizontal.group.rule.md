# Horizontal group rule for reports — `account.report.horizontal.group.rule`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `horizontal_group_id` **(many2one)** — Horizontal Group ⚠️ obrigatório → `account.report.horizontal.group`
- `domain` **(char)** — Domain ⚠️ obrigatório
- `field_name` **(selection)** — Field ⚠️ obrigatório
  > Opções: `distribution_analytic_account_ids` (Distribution Analytic Account), `move_id` (Journal Entry), `journal_id` (Journal), `journal_group_id` (Ledger), `company_id` (Company), `company_currency_id` (Company Currency), `account_id` (Account), `search_account_id` (Search Account), `currency_id` (Currency), `partner_id` (Partner), `reconcile_model_id` (Reconciliation Model), `payment_id` (Originator Payment), `statement_line_id` (Originator Statement Line), `statement_id` (Statement), `commercial_partner_country` (Commercial Partner Country), `tax_ids` (Taxes), `group_tax_id` (Originator Group of Taxes), `tax_line_id` (Originator Tax), `tax_group_id` (Originator tax group), `tax_repartition_line_id` (Originator Tax Distribution Line), `tax_tag_ids` (Tags), `full_reconcile_id` (Matching), `reconciled_lines_ids` (Reconciled Lines), `reconciled_lines_excluding_exchange_diff_ids` (Reconciled Lines Excluding Exchange Diff), `account_root_id` (Account Root), `product_category_id` (Product Category), `parent_id` (Parent Section Line), `product_id` (Product), `allowed_uom_ids` (Allowed Uom), `product_uom_id` (Unit), `create_uid` (Created by), `write_uid` (Last Updated by), `expense_id` (Expense), `purchase_line_id` (Purchase Order Line), `purchase_order_id` (Purchase Order), `cogs_origin_id` (Cogs Origin), `l10n_latam_document_type_id` (Document Type), `sale_line_ids` (Sales Order Lines), `followup_line_id` (Follow-up Level), `asset_ids` (Related Assets), `l10n_br_goods_operation_type_id` (Override Operation Type)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `res_model_name` **(char)** — Model 🔒 readonly
