# Accounting Return — `account.return`

**Ordenação padrão:** `date_deadline, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `date_from` **(date)** — Date From ⚠️ obrigatório
- `date_to` **(date)** — Date To ⚠️ obrigatório
- `type_id` **(many2one)** — Return Type ⚠️ obrigatório → `account.return.type`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `audit_status` **(selection)** — Audit Status ⚠️ obrigatório
  > Opções: `ongoing` (Ongoing), `done` (Done), `paused` (Paused)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `state` **(char)** — State
- `generic_state_tax_report` **(selection)** — Generic State
  > The state of the return for generic tax report flows
  > Opções: `new` (New), `reviewed` (Review), `submitted` (Submit), `paid` (Pay)
- `generic_state_only_pay` **(selection)** — Generic State Only Pay
  > The state of the return for report flows when only payment is needed
  > Opções: `new` (New), `paid` (Pay)
- `generic_state_review_submit` **(selection)** — Generic State Review Submit
  > The state of the return for report flows when review and submission are needed
  > Opções: `new` (New), `reviewed` (Review), `submitted` (Submit)
- `generic_state_review` **(selection)** — Generic State Review
  > The default state for audit and custom generated return types
  > Opções: `new` (New), `reviewed` (Review)
- `is_completed` **(boolean)** — Is Completed
- `date_deadline` **(date)** — Deadline 🔒 readonly
- `date_lock` **(date)** — Lock Date
- `date_submission` **(date)** — Submission Date
- `manually_created` **(boolean)** — Manually Created
- `total_amount_to_pay` **(monetary)** — Total Amount To Pay
- `period_amount_to_pay` **(monetary)** — Period Amount To Pay
- `report_opened_once` **(boolean)** — Report Opened Once
  > Has the report been opened once
- `skipped_check_cycles` **(char)** — Skipped Check Cycles
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `tax_unit_id` **(many2one)** — Tax Unit → `account.tax.unit`
- `company_ids` **(many2many)** — Companies 🔒 readonly → `res.company`
- `closing_move_ids` **(one2many)** — Closing Move → `account.move`
- `attachment_ids` **(many2many)** — Attachment → `ir.attachment`
- `check_ids` **(one2many)** — Checks → `account.return.check`
- `amount_to_pay_currency_id` **(many2one)** — Amount To Pay Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `next_state` **(char)** — Next State 🔒 readonly
- `type_external_id` **(char)** — Type External 🔒 readonly
- `check_count` **(integer)** — Checks Count 🔒 readonly
- `unresolved_check_count` **(integer)** — Issues 🔒 readonly
- `resolved_check_count` **(integer)** — Passed 🔒 readonly
- `show_amount_to_pay` **(boolean)** — Show Amount To Pay 🔒 readonly
- `days_to_deadline` **(integer)** — Days To Deadline 🔒 readonly
- `is_report_set` **(boolean)** — Is Report Set 🔒 readonly
- `has_move_entries` **(boolean)** — Has Move Entries 🔒 readonly
- `report_name` **(char)** — Report Name 🔒 readonly
- `show_companies` **(boolean)** — Show Companies 🔒 readonly
- `is_main_company_active` **(boolean)** — Is Main Company Active 🔒 readonly
- `return_type_category` **(selection)** — Type 🔒 readonly
  > Opções: `account_return` (Tax Return), `audit` (Audit)
- `visible_states` **(json)** — Visible States 🔒 readonly
- `show_submit_button` **(boolean)** — Show Submit Button 🔒 readonly
- `is_tax_return` **(boolean)** — Is a Tax Return Return Type 🔒 readonly
- `is_ec_sales_list_return` **(boolean)** — Is an EC Sales List Return Type 🔒 readonly

## Campos de Auditoria

- `audit_account_status_ids` **(one2many)** — Account Status → `account.audit.account.status`
- `audit_balances_count` **(integer)** — Balances Count 🔒 readonly
- `audit_balances_completed_count` **(integer)** — Completed Balances Count 🔒 readonly
