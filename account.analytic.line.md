# Analytic Line — `account.analytic.line`

**Ordenação padrão:** `date desc, id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Description ⚠️ obrigatório
- `date` **(date)** — Date ⚠️ obrigatório
- `amount` **(monetary)** — Amount ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `validated_status` **(selection)** — Validated Status ⚠️ obrigatório 🔒 readonly
  > Opções: `draft` (Draft), `validated` (Validated)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `unit_amount` **(float)** — Quantity
- `category` **(selection)** — Category
  > Opções: `other` (Other), `invoice` (Customer Invoice), `vendor_bill` (Vendor Bill), `manufacturing_order` (Manufacturing Order), `picking_entry` (Inventory Transfer)
- `fiscal_year_search` **(boolean)** — Fiscal Year Search
- `analytic_distribution` **(json)** — Analytic Distribution
- `analytic_precision` **(integer)** — Analytic Precision
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `code` **(char)** — Code
- `ref` **(char)** — Ref.
- `validated` **(boolean)** — Validated line 🔒 readonly
- `timesheet_invoice_type` **(selection)** — Billable Type 🔒 readonly
  > Opções: `billable_time` (Billed on Timesheets), `billable_fixed` (Billed at a Fixed price), `billable_milestones` (Billed on Milestones), `billable_manual` (Billed Manually), `non_billable` (Non-Billable), `timesheet_revenues` (Timesheet Revenues), `service_revenues` (Service Revenues), `other_revenues` (Other revenues), `other_costs` (Other costs)
- `is_so_line_edited` **(boolean)** — Is Sales Order Item Manually Edited

## Relacionamentos

- `user_timer_id` **(one2many)** — User Timer 🔒 readonly → `timer.timer`
- `account_id` **(many2one)** — Project → `account.analytic.account`
- `auto_account_id` **(many2one)** — Analytic Account → `account.analytic.account`
- `product_uom_id` **(many2one)** — Unit → `uom.uom`
- `partner_id` **(many2one)** — Partner → `res.partner`
- `user_id` **(many2one)** — User → `res.users`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `product_id` **(many2one)** — Product → `product.product`
- `general_account_id` **(many2one)** — Financial Account → `account.account`
- `journal_id` **(many2one)** — Financial Journal 🔒 readonly → `account.journal`
- `move_line_id` **(many2one)** — Journal Item → `account.move.line`
- `task_id` **(many2one)** — Task → `project.task`
- `parent_task_id` **(many2one)** — Parent Task 🔒 readonly → `project.task`
- `project_id` **(many2one)** — Project → `project.project`
- `employee_id` **(many2one)** — Employee → `hr.employee`
  > Define an 'hourly cost' on the employee to track the cost of their time.
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `manager_id` **(many2one)** — Manager 🔒 readonly → `hr.employee`
- `encoding_uom_id` **(many2one)** — Encoding Uom 🔒 readonly → `uom.uom`
- `milestone_id` **(many2one)** — Milestone 🔒 readonly → `project.milestone`
  > Deliver your services automatically when a milestone is reached by linking it to a sales order item.
- `so_line` **(many2one)** — Sales Order Item → `sale.order.line`
  > Sales order item to which the time spent will be added in order to be invoiced to your customer. Remove the sales order item for the timesheet entry to be non-billable.
- `commercial_partner_id` **(many2one)** — Commercial Partner 🔒 readonly → `res.partner`
- `timesheet_invoice_id` **(many2one)** — Invoice 🔒 readonly → `account.move`
  > Invoice created from the timesheet
- `order_id` **(many2one)** — Order Reference 🔒 readonly → `sale.order`

## Campos Calculados (readonly)

- `timer_start` **(datetime)** — Timer Start 🔒 readonly
- `timer_pause` **(datetime)** — Timer Last Pause 🔒 readonly
- `is_timer_running` **(boolean)** — Is Timer Running 🔒 readonly
- `analytic_coverage` **(float)** — Analytic Coverage 🔒 readonly
- `job_title` **(char)** — Job Title 🔒 readonly
- `readonly_timesheet` **(boolean)** — Readonly Timesheet 🔒 readonly
- `calendar_display_name` **(char)** — Calendar Display Name 🔒 readonly
- `user_can_validate` **(boolean)** — User Can Validate 🔒 readonly
  > Whether or not the current user can validate/reset to draft the record.
- `display_timer` **(boolean)** — Technical field used to display the timer if the encoding unit is 'Hours'. 🔒 readonly
- `is_hatched` **(boolean)** — Is Hatched 🔒 readonly
- `allow_billable` **(boolean)** — Billable 🔒 readonly
- `sale_order_state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
