# Task — `project.task`

**Ordenação padrão:** `priority desc, sequence, date_deadline asc, id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Title ⚠️ obrigatório
- `state` **(selection)** — State ⚠️ obrigatório
  > Opções: `01_in_progress` (In Progress), `02_changes_requested` (Changes Requested), `03_approved` (Approved), `1_done` (Done), `1_canceled` (Cancelled), `04_waiting_normal` (Waiting)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `html_field_history` **(json)** — History data 🔒 readonly
- `rating_last_value` **(float)** — Rating Last Value 🔒 readonly
- `email_cc` **(char)** — Email cc
  > Email addresses that were in the CC of the incoming emails from this task and that are not currently linked to an existing customer.
- `access_token` **(char)** — Security Token
- `active` **(boolean)** — Active
- `description` **(html)** — Description
- `priority` **(selection)** — Priority
  > Opções: `0` (Low priority), `1` (Medium priority), `2` (High priority), `3` (Urgent)
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created On 🔒 readonly
- `write_date` **(datetime)** — Last Updated On 🔒 readonly
- `date_end` **(datetime)** — Ending Date
- `date_assign` **(datetime)** — Assigning Date 🔒 readonly
  > Date on which this task was last assigned (or unassigned). Based on this, you can get statistics on the time it usually takes to assign tasks.
- `date_deadline` **(datetime)** — Deadline
- `date_last_stage_update` **(datetime)** — Last Stage Update 🔒 readonly
  > Date on which the state of your task has last been modified. Based on this information you can identify tasks that are stalling and get statistics on the time it usually takes to move tasks from one stage/state to another.
- `display_in_project` **(boolean)** — Display In Project 🔒 readonly
- `task_properties` **(properties)** — Properties
- `allocated_hours` **(float)** — Allocated Time
- `partner_phone` **(char)** — Contact Number
- `email_from` **(char)** — Email From
- `color` **(integer)** — Color Index
- `working_hours_open` **(float)** — Working Hours to Assign 🔒 readonly
- `working_hours_close` **(float)** — Working Hours to Close 🔒 readonly
- `working_days_open` **(float)** — Working Days to Assign 🔒 readonly
- `working_days_close` **(float)** — Working Days to Close 🔒 readonly
- `recurring_task` **(boolean)** — Recurrent
- `repeat_interval` **(integer)** — Repeat Every
- `repeat_unit` **(selection)** — Repeat Unit
  > Opções: `day` (Days), `week` (Weeks), `month` (Months), `year` (Years)
- `repeat_type` **(selection)** — Until
  > Opções: `forever` (Forever), `until` (Until)
- `repeat_until` **(date)** — End Date
- `is_template` **(boolean)** — Is Template
- `has_template_ancestor` **(boolean)** — Has Template Ancestor 🔒 readonly
- `planned_date_begin` **(datetime)** — Start date
- `planned_date_start` **(datetime)** — Planned Date Start
- `partner_name` **(char)** — Customer Name
- `partner_company_name` **(char)** — Company Name
- `remaining_hours` **(float)** — Time Remaining 🔒 readonly
  > Number of allocated hours minus the number of hours spent.
- `effective_hours` **(float)** — Time Spent 🔒 readonly
- `total_hours_spent` **(float)** — Total Time Spent 🔒 readonly
  > Time spent on this task and its sub-tasks (and their own sub-tasks).
- `progress` **(float)** — Progress 🔒 readonly
- `overtime` **(float)** — Overtime 🔒 readonly
- `subtask_effective_hours` **(float)** — Time Spent on Sub-tasks 🔒 readonly
  > Time spent on the sub-tasks (and their own sub-tasks) of this task.

## Relacionamentos

- `user_timer_id` **(one2many)** — User Timer 🔒 readonly → `timer.timer`
- `stage_id` **(many2one)** — Stage → `project.task.type`
- `tag_ids` **(many2many)** — Tags → `project.tags`
- `project_id` **(many2one)** — Project → `project.project`
- `role_ids` **(many2many)** — Project Roles → `project.role`
  > When you create a project from a template, you can choose which employee takes each role. These employees will be added to the tasks, along with anyone already assigned.
- `user_ids` **(many2many)** — Assignees → `res.users`
- `personal_stage_type_ids` **(many2many)** — Personal Stages → `project.task.type`
- `personal_stage_id` **(many2one)** — Personal Stage State 🔒 readonly → `project.task.stage.personal`
  > The current user's personal stage.
- `personal_stage_type_id` **(many2one)** — Personal Stage → `project.task.type`
  > The current user's personal task stage.
- `partner_id` **(many2one)** — Customer → `res.partner`
- `company_id` **(many2one)** — Company → `res.company`
- `attachment_ids` **(one2many)** — Attachments 🔒 readonly → `ir.attachment`
  > Attachments that don't come from a message
- `displayed_image_id` **(many2one)** — Cover Image → `ir.attachment`
- `parent_id` **(many2one)** — Parent Task → `project.task`
- `child_ids` **(one2many)** — Sub-tasks → `project.task`
- `milestone_id` **(many2one)** — Milestone → `project.milestone`
  > Deliver your services automatically when a milestone is reached by linking it to a sales order item.
- `depend_on_ids` **(many2many)** — Blocked By → `project.task`
- `dependent_ids` **(many2many)** — Block → `project.task`
- `recurrence_id` **(many2one)** — Recurrence → `project.task.recurrence`
- `timesheet_ids` **(one2many)** — Timesheets → `account.analytic.line`
- `user_skill_ids` **(one2many)** — Skills 🔒 readonly → `hr.employee.skill`
- `sale_order_id` **(many2one)** — Sales Order 🔒 readonly → `sale.order`
  > Sales order to which the task is linked.
- `sale_line_id` **(many2one)** — Sales Order Item → `sale.order.line`
  > Sales Order Item to which the time spent on this task will be added in order to be invoiced to your customer. By default the sales order item set on the project will be selected. In the absence of one, the last prepaid sales order item that has time remaining will be used. Remove the sales order item in order to make this task non billable. You can also change or remove the sales order item of each timesheet entry individually.
- `project_sale_order_id` **(many2one)** — Project's sale order 🔒 readonly → `sale.order`
- `timesheet_product_id` **(many2one)** — Timesheet Product 🔒 readonly → `product.product`
  > Service that will be used by default when invoicing the time spent on a task. It can be modified on each task individually by selecting a specific sales order item.
- `last_sol_of_customer` **(many2one)** — Last Sol Of Customer 🔒 readonly → `sale.order.line`
- `calendar_event_id` **(many2one)** — Calendar Event → `calendar.event`
  > Linked appointment of this task

## Campos Calculados (readonly)

- `timer_start` **(datetime)** — Timer Start 🔒 readonly
- `timer_pause` **(datetime)** — Timer Last Pause 🔒 readonly
- `is_timer_running` **(boolean)** — Is Timer Running 🔒 readonly
- `html_field_history_metadata` **(json)** — History metadata 🔒 readonly
- `duration_tracking` **(json)** — Status time 🔒 readonly
  > JSON that maps ids from a many2one field to seconds spent
- `rotting_days` **(integer)** — Days Rotting 🔒 readonly
  > Day count since this resource was last updated
- `is_rotting` **(boolean)** — Rotting 🔒 readonly
- `rating_last_feedback` **(text)** — Rating Last Feedback 🔒 readonly
- `rating_last_image` **(binary)** — Rating Last Image 🔒 readonly
- `rating_count` **(integer)** — Rating count 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `rating_avg_text` **(selection)** — Rating Avg Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `rating_percentage_satisfaction` **(float)** — Rating Satisfaction 🔒 readonly
- `rating_last_text` **(selection)** — Rating Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `stage_id_color` **(integer)** — Stage Color 🔒 readonly
- `is_closed` **(boolean)** — Closed state 🔒 readonly
- `subtask_allocated_hours` **(float)** — Sub-tasks Allocated Time 🔒 readonly
  > Sum of the hours allocated for all the sub-tasks (and their own sub-tasks) linked to this task. Usually less than or equal to the allocated hours of this task.
- `portal_user_names` **(char)** — Portal User Names 🔒 readonly
- `rating_active` **(boolean)** — Stage Rating Status 🔒 readonly
- `subtask_count` **(integer)** — Sub-task Count 🔒 readonly
- `closed_subtask_count` **(integer)** — Closed Sub-tasks Count 🔒 readonly
- `project_privacy_visibility` **(selection)** — Project Visibility 🔒 readonly
  > Project and Task Visibility: - Invited internal users: Can access only the project or tasks they follow. Assignees automatically get access. - Invited internal and portal users: Same as above, extended to portal users. - All internal users: Full access to the project and all its tasks. - All internal and invited portal users: Internal users get full access. Portal users can access only the project or tasks they follow.  Portal Access Levels: - Read-only: Portal users see tasks via their portal but can’t edit them. - Edit (limited): Portal users access kanban/list views and can edit limited fields on followed tasks. - Edit: Same as above, with access to all tasks.  Other Rules: - Internal users can open a task from a direct link, even without project access. - Project admins have access to private projects, even if not followers. 
  > Opções: `followers` (Invited internal users), `invited_users` (Invited internal and portal users), `employees` (All internal users), `portal` ( All internal users and invited portal users)
- `subtask_completion_percentage` **(float)** — Subtask Completion Percentage 🔒 readonly
- `allow_milestones` **(boolean)** — Milestones 🔒 readonly
- `has_late_and_unreached_milestone` **(boolean)** — Has Late And Unreached Milestone 🔒 readonly
- `allow_task_dependencies` **(boolean)** — Task Dependencies 🔒 readonly
- `depend_on_count` **(integer)** — Depending on Tasks 🔒 readonly
- `closed_depend_on_count` **(integer)** — Closed Depending on Tasks 🔒 readonly
- `dependent_tasks_count` **(integer)** — Dependent Tasks 🔒 readonly
- `display_parent_task_button` **(boolean)** — Display Parent Task Button 🔒 readonly
- `current_user_same_company_partner` **(boolean)** — Current User Same Company Partner 🔒 readonly
- `display_follow_button` **(boolean)** — Display Follow Button 🔒 readonly
- `allow_recurring_tasks` **(boolean)** — Recurring Tasks 🔒 readonly
- `recurring_count` **(integer)** — Tasks in Recurrence 🔒 readonly
- `link_preview_name` **(char)** — Link Preview Name 🔒 readonly
- `has_project_template` **(boolean)** — Has Project Template 🔒 readonly
- `display_warning_dependency_in_gantt` **(boolean)** — Display Warning Dependency In Gantt 🔒 readonly
- `planning_overlap` **(html)** — Planning Overlap 🔒 readonly
- `dependency_warning` **(html)** — Dependency Warning 🔒 readonly
- `user_names` **(char)** — User Names 🔒 readonly
- `analytic_account_active` **(boolean)** — Active Analytic Account 🔒 readonly
  > Deactivate the account.
- `allow_timesheets` **(boolean)** — Allow timesheets 🔒 readonly
- `remaining_hours_percentage` **(float)** — Remaining Hours Percentage 🔒 readonly
- `encode_uom_in_days` **(boolean)** — Encode Uom In Days 🔒 readonly
- `timesheet_unit_amount` **(float)** — Timesheet Unit Amount 🔒 readonly
- `display_timesheet_timer` **(boolean)** — Display Timesheet Time 🔒 readonly
- `sale_order_state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
- `task_to_invoice` **(boolean)** — To invoice 🔒 readonly
- `allow_billable` **(boolean)** — Billable 🔒 readonly
- `display_sale_order_button` **(boolean)** — Display Sales Order 🔒 readonly
- `pricing_type` **(selection)** — Pricing 🔒 readonly
  > The task rate is perfect if you would like to bill different services to different customers at different rates. The fixed rate is perfect if you bill a service at a fixed rate per hour or day worked regardless of the employee who performed it. The employee rate is preferable if your employees deliver the same service at a different rate. For instance, junior and senior consultants would deliver the same service (= consultancy), but at a different rate because of their level of seniority.
  > Opções: `task_rate` (Task rate), `fixed_rate` (Project rate), `employee_rate` (Employee rate)
- `is_project_map_empty` **(boolean)** — Is Project map empty 🔒 readonly
- `has_multi_sol` **(boolean)** — Has Multi Sol 🔒 readonly
- `remaining_hours_so` **(float)** — Time Remaining on SO 🔒 readonly
- `remaining_hours_available` **(boolean)** — Remaining Hours Available 🔒 readonly
- `portal_remaining_hours` **(float)** — Portal Remaining Hours 🔒 readonly
  > Total remaining time, can be re-estimated periodically by the assignee of the task.
- `portal_effective_hours` **(float)** — Portal Effective Hours 🔒 readonly
  > Time spent on this task, excluding its sub-tasks.
- `portal_total_hours_spent` **(float)** — Portal Total Hours Spent 🔒 readonly
  > Time spent on this task, including its sub-tasks.
- `portal_subtask_effective_hours` **(float)** — Portal Subtask Effective Hours 🔒 readonly
  > Time spent on the sub-tasks (and their own sub-tasks) of this task.
- `portal_progress` **(float)** — Portal Progress 🔒 readonly
  > Display progress of current task.
