# Project — `project.project`

**Ordenação padrão:** `sequence, name, id`

---

## Campos Obrigatórios

- `alias_id` **(many2one)** — Alias ⚠️ obrigatório → `mail.alias`
  > Internal email associated with this project. Incoming emails are automatically synchronized with Tasks (or optionally Issues if the Issue Tracker module is installed).
- `alias_defaults` **(text)** — Default Values ⚠️ obrigatório 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `name` **(char)** — Name ⚠️ obrigatório
- `privacy_visibility` **(selection)** — Visibility ⚠️ obrigatório
  > Project and Task Visibility: - Invited internal users: Can access only the project or tasks they follow. Assignees automatically get access. - Invited internal and portal users: Same as above, extended to portal users. - All internal users: Full access to the project and all its tasks. - All internal and invited portal users: Internal users get full access. Portal users can access only the project or tasks they follow.  Portal Access Levels: - Read-only: Portal users see tasks via their portal but can’t edit them. - Edit (limited): Portal users access kanban/list views and can edit limited fields on followed tasks. - Edit: Same as above, with access to all tasks.  Other Rules: - Internal users can open a task from a direct link, even without project access. - Project admins have access to private projects, even if not followers. 
  > Opções: `followers` (Invited internal users), `invited_users` (Invited internal and portal users), `employees` (All internal users), `portal` ( All internal users and invited portal users)
- `last_update_status` **(selection)** — Last Update Status ⚠️ obrigatório
  > Opções: `on_track` (On Track), `at_risk` (At Risk), `off_track` (Off Track), `on_hold` (On Hold), `to_define` (Set Status), `done` (Complete)
- `billing_type` **(selection)** — Billing Type ⚠️ obrigatório
  > Opções: `not_billable` (not billable), `manually` (billed manually)
- `alias_model_id` **(many2one)** — Aliased Model ⚠️ obrigatório → `ir.model`
  > The model (Odoo Document Kind) to which this alias corresponds. Any incoming email that does not reply to an existing record will cause the creation of a new record of this model (e.g. a Project Task)
- `alias_contact` **(selection)** — Alias Contact Security ⚠️ obrigatório
  > Policy to post a message on the document using the mailgateway. - everyone: everyone can post - partners: only authenticated partners - followers: only followers of the related document or members of following channels 
  > Opções: `everyone` (Everyone), `partners` (Authenticated Partners), `followers` (Followers only), `employees` (Authenticated Employees)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>
- `access_token` **(char)** — Security Token
- `description` **(html)** — Description
  > Description to provide more information and context about this project
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `is_favorite` **(boolean)** — Show Project on Dashboard
- `label_tasks` **(char)** — Use Tasks as
  > Name used to refer to the tasks of your project e.g. tasks, tickets, sprints, etc...
- `color` **(integer)** — Color Index
- `date_start` **(date)** — Start Date
- `date` **(date)** — Expiration Date
  > Date on which this project ends. The timeframe defined on the project is taken into account when viewing its planning.
- `allow_task_dependencies` **(boolean)** — Task Dependencies
- `allow_milestones` **(boolean)** — Milestones
- `allow_recurring_tasks` **(boolean)** — Recurring Tasks
- `task_properties_definition` **(properties_definition)** — Task Properties
- `is_template` **(boolean)** — Is Template
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `allow_timesheets` **(boolean)** — Timesheets
- `allocated_hours` **(float)** — Allocated Time
- `allow_billable` **(boolean)** — Billable
- `alias_force_thread_id` **(integer)** — Record Thread ID
  > Optional ID of a thread (record) to which all incoming messages will be attached, even if they did not reply to it. If set, this will disable the creation of new records completely.
- `alias_parent_thread_id` **(integer)** — Parent Record Thread ID
  > ID of the parent record holding the alias (example: project holding the task creation alias)
- `alias_incoming_local` **(boolean)** — Local-part based incoming detection
- `alias_bounced_content` **(html)** — Custom Bounced Message
  > If set, this content will automatically be sent out to unauthorized users instead of the default message.

## Relacionamentos

- `account_id` **(many2one)** — Project → `account.analytic.account`
- `auto_account_id` **(many2one)** — Analytic Account → `account.analytic.account`
- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `partner_id` **(many2one)** — Customer → `res.partner`
- `company_id` **(many2one)** — Company → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `favorite_user_ids` **(many2many)** — Members → `res.users`
- `tasks` **(one2many)** — Task Activities → `project.task`
- `resource_calendar_id` **(many2one)** — Working Time 🔒 readonly → `resource.calendar`
- `type_ids` **(many2many)** — Tasks Stages → `project.task.type`
- `task_ids` **(one2many)** — Tasks → `project.task`
- `user_id` **(many2one)** — Project Manager → `res.users`
- `tag_ids` **(many2many)** — Tags → `project.tags`
- `collaborator_ids` **(one2many)** — Collaborators → `project.collaborator`
- `update_ids` **(one2many)** — Update → `project.update`
- `last_update_id` **(many2one)** — Last Update → `project.update`
- `milestone_ids` **(one2many)** — Milestone → `project.milestone`
- `next_milestone_id` **(many2one)** — Next Milestone 🔒 readonly → `project.milestone`
- `documents_folder_id` **(many2one)** — Documents Folder → `documents.document`
  > Folder in which all of the documents of this project will be categorized.
- `document_ids` **(one2many)** — Document 🔒 readonly → `documents.document`
- `timesheet_ids` **(one2many)** — Associated Timesheets → `account.analytic.line`
- `timesheet_encode_uom_id` **(many2one)** — Timesheet Encode Uom 🔒 readonly → `uom.uom`
- `sale_line_id` **(many2one)** — Sales Order Item → `sale.order.line`
  > Sales order item that will be selected by default on the tasks and timesheets of this project, except if the employee set on the timesheets is explicitely linked to another sales order item on the project. It can be modified on each task and timesheet entry individually if necessary.
- `sale_order_id` **(many2one)** — Order Reference 🔒 readonly → `sale.order`
- `reinvoiced_sale_order_id` **(many2one)** — Sales Order → `sale.order`
  > Products added to stock pickings, whose operation type is configured to generate analytic costs, will be re-invoiced in this sales order if they are set up for it.
- `sale_line_employee_ids` **(one2many)** — Sale line/Employee map → `project.sale.line.employee.map`
  > Sales order item that will be selected by default on the timesheets of the corresponding employee. It bypasses the sales order item defined on the project and the task, and can be modified on each timesheet entry if necessary. In other words, it defines the rate at which an employee's time is billed based on their expertise, skills or experience, for instance. If you would like to bill the same service at a different rate, you need to create two separate sales order items as each sales order item can only have a single unit price at a time. You can also define the hourly company cost of your employees for their timesheets on this project specifically. It will bypass the timesheet cost set on the employee.
- `timesheet_product_id` **(many2one)** — Timesheet Product → `product.product`
  > Service that will be used by default when invoicing the time spent on a task. It can be modified on each task individually by selecting a specific sales order item.
- `alias_parent_model_id` **(many2one)** — Parent Model → `ir.model`
  > Parent model holding the alias. The model holding the alias reference is not necessarily the model given by alias_model_id (example: project (parent_model) and task (model))

## Campos Calculados (readonly)

- `rotting_days` **(integer)** — Days Rotting 🔒 readonly
  > Day count since this resource was last updated
- `is_rotting` **(boolean)** — Rotting 🔒 readonly
- `rating_percentage_satisfaction` **(integer)** — Rating Satisfaction 🔒 readonly
  > Percentage of happy ratings
- `rating_count` **(integer)** — # Ratings 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `rating_avg_percentage` **(float)** — Average Rating (%) 🔒 readonly
- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_email` **(char)** — Email Alias 🔒 readonly
- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `analytic_account_balance` **(monetary)** — Balance 🔒 readonly
- `task_count` **(integer)** — Task Count 🔒 readonly
- `open_task_count` **(integer)** — Open Task Count 🔒 readonly
- `privacy_visibility_warning` **(char)** — Privacy Visibility Warning 🔒 readonly
- `access_instruction_message` **(char)** — Access Instruction Message 🔒 readonly
- `closed_task_count` **(integer)** — Closed Task Count 🔒 readonly
- `task_completion_percentage` **(float)** — Task Completion Percentage 🔒 readonly
- `collaborator_count` **(integer)** — # Collaborators 🔒 readonly
- `stage_id_color` **(integer)** — Stage Color 🔒 readonly
- `update_count` **(integer)** — Update Count 🔒 readonly
- `last_update_color` **(integer)** — Last Update Color 🔒 readonly
- `milestone_count` **(integer)** — Milestone Count 🔒 readonly
- `milestone_count_reached` **(integer)** — Milestone Count Reached 🔒 readonly
- `is_milestone_exceeded` **(boolean)** — Is Milestone Exceeded 🔒 readonly
- `milestone_progress` **(integer)** — Milestones Reached 🔒 readonly
- `can_mark_milestone_as_done` **(boolean)** — Can Mark Milestone As Done 🔒 readonly
- `is_milestone_deadline_exceeded` **(boolean)** — Is Milestone Deadline Exceeded 🔒 readonly
- `show_ratings` **(boolean)** — Show Ratings 🔒 readonly
- `document_count` **(integer)** — Document Count 🔒 readonly
- `analytic_account_active` **(boolean)** — Active Account 🔒 readonly
  > Deactivate the account.
- `total_timesheet_time` **(float)** — Total amount of time (in the proper unit) recorded in the project, rounded to the unit. 🔒 readonly
- `encode_uom_in_days` **(boolean)** — Encode Uom In Days 🔒 readonly
- `is_internal_project` **(boolean)** — Is Internal Project 🔒 readonly
- `remaining_hours` **(float)** — Time Remaining 🔒 readonly
- `is_project_overtime` **(boolean)** — Project in Overtime 🔒 readonly
- `effective_hours` **(float)** — Time Spent 🔒 readonly
- `bom_count` **(integer)** — Bom Count 🔒 readonly
- `production_count` **(integer)** — Production Count 🔒 readonly
- `purchase_orders_count` **(integer)** — # Purchase Orders 🔒 readonly
- `total_budget_amount` **(monetary)** — Total planned amount 🔒 readonly
- `total_budget_progress` **(float)** — Budget Spent 🔒 readonly
- `has_any_so_to_invoice` **(boolean)** — Has SO to Invoice 🔒 readonly
- `sale_order_line_count` **(integer)** — Sale Order Line Count 🔒 readonly
- `sale_order_count` **(integer)** — Sale Order Count 🔒 readonly
- `has_any_so_with_nothing_to_invoice` **(boolean)** — Has a SO with an invoice status of No 🔒 readonly
- `display_sales_stat_buttons` **(boolean)** — Display Sales Stat Buttons 🔒 readonly
- `sale_order_state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
- `pricing_type` **(selection)** — Pricing 🔒 readonly
  > The task rate is perfect if you would like to bill different services to different customers at different rates. The fixed rate is perfect if you bill a service at a fixed rate per hour or day worked regardless of the employee who performed it. The employee rate is preferable if your employees deliver the same service at a different rate. For instance, junior and senior consultants would deliver the same service (= consultancy), but at a different rate because of their level of seniority.
  > Opções: `task_rate` (Task rate), `fixed_rate` (Project rate), `employee_rate` (Employee rate)
- `warning_employee_rate` **(boolean)** — Warning Employee Rate 🔒 readonly
- `alias_full_name` **(char)** — Alias Email 🔒 readonly
- `alias_status` **(selection)** — Alias Status 🔒 readonly
  > Alias status assessed on the last message received.
  > Opções: `not_tested` (Not Tested), `valid` (Valid), `invalid` (Invalid)
