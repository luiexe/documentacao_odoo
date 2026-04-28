# Timesheets Analysis Report — `timesheets.analysis.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Description 🔒 readonly
- `date` **(date)** — Date 🔒 readonly
- `amount` **(monetary)** — Amount 🔒 readonly
- `unit_amount` **(float)** — Time Spent 🔒 readonly
- `validated` **(boolean)** — Validated line 🔒 readonly
- `validated_status` **(selection)** — Validated Status 🔒 readonly
  > Opções: `draft` (Draft), `validated` (Validated)
- `timesheet_invoice_type` **(selection)** — Billable Type 🔒 readonly
  > Opções: `billable_time` (Billed on Timesheets), `billable_fixed` (Billed at a Fixed price), `billable_milestones` (Billed on Milestones), `billable_manual` (Billed Manually), `non_billable` (Non-Billable), `timesheet_revenues` (Timesheet Revenues), `service_revenues` (Service Revenues), `other_revenues` (Other revenues), `other_costs` (Other costs)
- `timesheet_revenues` **(monetary)** — Timesheet Revenues 🔒 readonly
  > Number of hours spent multiplied by the unit price per hour/day.
- `margin` **(monetary)** — Margin 🔒 readonly
  > Timesheets revenues minus the costs
- `billable_time` **(float)** — Billable Time 🔒 readonly
  > Number of hours/days linked to a SOL.
- `non_billable_time` **(float)** — Non-billable Time 🔒 readonly
  > Number of hours/days not linked to a SOL.

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `user_id` **(many2one)** — User 🔒 readonly → `res.users`
- `project_id` **(many2one)** — Project 🔒 readonly → `project.project`
- `task_id` **(many2one)** — Task 🔒 readonly → `project.task`
- `parent_task_id` **(many2one)** — Parent Task 🔒 readonly → `project.task`
- `manager_id` **(many2one)** — Manager 🔒 readonly → `hr.employee`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
- `milestone_id` **(many2one)** — Milestone 🔒 readonly → `project.milestone`
  > Deliver your services automatically when a milestone is reached by linking it to a sales order item.
- `order_id` **(many2one)** — Sales Order 🔒 readonly → `sale.order`
- `so_line` **(many2one)** — Sales Order Item 🔒 readonly → `sale.order.line`
- `timesheet_invoice_id` **(many2one)** — Invoice 🔒 readonly → `account.move`
  > Invoice created from the timesheet

## Campos Calculados (readonly)

- `has_department_manager_access` **(boolean)** — Has Department Manager Access 🔒 readonly
- `is_timer_running` **(boolean)** — Is Timer Running 🔒 readonly
