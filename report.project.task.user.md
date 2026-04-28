# Tasks Analysis — `report.project.task.user`

**Ordenação padrão:** `name desc, project_id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Task Title 🔒 readonly
- `create_date` **(datetime)** — Create Date 🔒 readonly
- `date_assign` **(datetime)** — Assignment Date 🔒 readonly
- `date_end` **(datetime)** — Ending Date 🔒 readonly
- `date_deadline` **(datetime)** — Deadline 🔒 readonly
- `date_last_stage_update` **(datetime)** — Last Stage Update 🔒 readonly
- `display_in_project` **(boolean)** — Display In Project
- `working_days_close` **(float)** — Working Days to Close 🔒 readonly
- `working_days_open` **(float)** — Working Days to Assign 🔒 readonly
- `delay_endings_days` **(float)** — Days to Deadline 🔒 readonly
- `nbr` **(integer)** — # of Tasks 🔒 readonly
- `working_hours_open` **(float)** — Working Hours to Assign 🔒 readonly
- `working_hours_close` **(float)** — Working Hours to Close 🔒 readonly
- `rating_last_value` **(float)** — Last Rating (1-5) 🔒 readonly
- `rating_avg` **(float)** — Average Rating (1-5) 🔒 readonly
- `priority` **(selection)** — Priority 🔒 readonly
  > Opções: `0` (Low priority), `1` (Medium priority), `2` (High priority), `3` (Urgent)
- `state` **(selection)** — State 🔒 readonly
  > Opções: `01_in_progress` (In Progress), `1_done` (Done), `04_waiting_normal` (Waiting), `03_approved` (Approved), `1_canceled` (Cancelled), `02_changes_requested` (Changes Requested)
- `is_closed` **(boolean)** — Closed state 🔒 readonly
- `description` **(text)** — Description 🔒 readonly
- `is_template` **(boolean)** — Is Template 🔒 readonly
- `has_template_ancestor` **(boolean)** — Has Template Ancestor 🔒 readonly
- `planned_date_begin` **(datetime)** — Start date 🔒 readonly
- `allocated_hours` **(float)** — Allocated Time 🔒 readonly
- `effective_hours` **(float)** — Time Spent 🔒 readonly
- `remaining_hours` **(float)** — Time Remaining 🔒 readonly
- `remaining_hours_percentage` **(float)** — Time Remaining Percentage 🔒 readonly
- `progress` **(float)** — Progress 🔒 readonly
- `overtime` **(float)** — Overtime 🔒 readonly
- `remaining_hours_so` **(float)** — Time Remaining on SO 🔒 readonly

## Relacionamentos

- `user_ids` **(many2many)** — Assignees 🔒 readonly → `res.users`
- `project_id` **(many2one)** — Project 🔒 readonly → `project.project`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `stage_id` **(many2one)** — Stage 🔒 readonly → `project.task.type`
- `task_id` **(many2one)** — Task 🔒 readonly → `project.task`
- `tag_ids` **(many2many)** — Tags 🔒 readonly → `project.tags`
- `parent_id` **(many2one)** — Parent Task 🔒 readonly → `project.task`
- `personal_stage_type_ids` **(many2many)** — Personal Stage 🔒 readonly → `project.task.type`
- `milestone_id` **(many2one)** — Milestone 🔒 readonly → `project.milestone`
- `dependent_ids` **(many2many)** — Block 🔒 readonly → `project.task`
- `user_skill_ids` **(one2many)** — Skills 🔒 readonly → `hr.employee.skill`
- `sale_line_id` **(many2one)** — Sales Order Item 🔒 readonly → `sale.order.line`
- `sale_order_id` **(many2one)** — Sales Order 🔒 readonly → `sale.order`
