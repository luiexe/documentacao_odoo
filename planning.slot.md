# Planning Shift — `planning.slot`

**Ordenação padrão:** `start_datetime desc, id desc`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `access_token` **(char)** — Access Token ⚠️ obrigatório 🔒 readonly
- `repeat_unit` **(selection)** — Repeat Unit ⚠️ obrigatório
  > Opções: `day` (Days), `week` (Weeks), `month` (Months), `year` (Years)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(text)** — Note
- `was_copied` **(boolean)** — This Shift Was Copied From Previous Week 🔒 readonly
- `start_datetime` **(datetime)** — Start Date
- `end_datetime` **(datetime)** — End Date
- `request_to_switch` **(boolean)** — Has there been a request to switch on this shift slot? 🔒 readonly
- `allocated_hours` **(float)** — Allocated Time
- `allocated_percentage` **(float)** — Allocated Time %
- `publication_warning` **(boolean)** — Modified Since Last Publication 🔒 readonly
  > If checked, it means that the shift contains has changed since its last publish.
- `state` **(selection)** — Status
  > Opções: `draft` (Draft), `published` (Published)
- `template_creation` **(boolean)** — Save as Template
- `template_reset` **(boolean)** — Template Reset
- `repeat` **(boolean)** — Repeat
  > To avoid polluting your database and performance issues, shifts are only created for the next 6 months. They are then gradually created as time passes by in order to always get shifts 6 months ahead. This value can be modified from the settings of Planning, in debug mode.
- `repeat_interval` **(integer)** — Repeat every
- `repeat_type` **(selection)** — Repeat Type
  > Opções: `forever` (Forever), `until` (Until), `x_times` (Number of Occurrences)
- `repeat_until` **(date)** — Repeat Until
- `repeat_number` **(integer)** — Repetitions
- `recurrence_update` **(selection)** — Recurrence Update
  > Opções: `this` (This shift), `subsequent` (This and following shifts), `all` (All shifts)
- `slot_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `resource_id` **(many2one)** — Resource → `resource.resource`
- `resource_roles` **(many2many)** — Roles 🔒 readonly → `planning.role`
- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `work_location_id` **(many2one)** — Work Location 🔒 readonly → `hr.work.location`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `user_id` **(many2one)** — User 🔒 readonly → `res.users`
  > Related user name for the resource to manage its access.
- `manager_id` **(many2one)** — Manager 🔒 readonly → `hr.employee`
- `role_id` **(many2one)** — Role → `planning.role`
  > Define the roles your resources will perform (e.g. Chef, Bartender, Waiter). Create open shifts based on the roles needed for a mission, then assign those shifts to available resources.
- `conflicting_slot_ids` **(many2many)** — Conflicting Slot 🔒 readonly → `planning.slot`
- `template_autocomplete_ids` **(many2many)** — Template Autocomplete 🔒 readonly → `planning.slot.template`
- `template_id` **(many2one)** — Shift Templates → `planning.slot.template`
- `previous_template_id` **(many2one)** — Previous Template → `planning.slot.template`
- `recurrency_id` **(many2one)** — Recurrency 🔒 readonly → `planning.recurrency`
- `employee_skill_ids` **(one2many)** — Skills 🔒 readonly → `hr.employee.skill`
- `sale_line_id` **(many2one)** — Sales Order Item → `sale.order.line`
  > Sales order item for which this shift will be performed. When sales orders are automatically planned, the remaining hours of the sales order item, as well as the role defined on the service, are taken into account.
- `sale_order_id` **(many2one)** — Sales Order 🔒 readonly → `sale.order`
- `partner_id` **(many2one)** — Customer 🔒 readonly → `res.partner`
- `role_product_ids` **(one2many)** — Services 🔒 readonly → `product.template`

## Campos Calculados (readonly)

- `resource_type` **(selection)** — Type 🔒 readonly
  > Opções: `user` (Human), `material` (Material)
- `resource_color` **(integer)** — Resource color 🔒 readonly
- `work_email` **(char)** — Work Email 🔒 readonly
- `job_title` **(char)** — Job Title 🔒 readonly
- `color` **(integer)** — Color 🔒 readonly
- `allow_self_unassign` **(boolean)** — Let Employee Unassign Themselves 🔒 readonly
- `self_unassign_days_before` **(integer)** — Days before shift for unassignment 🔒 readonly
  > Deadline in days for shift unassignment
- `unassign_deadline` **(datetime)** — Deadline for unassignment 🔒 readonly
- `is_unassign_deadline_passed` **(boolean)** — Is Unassign Deadline Passed 🔒 readonly
- `overlap_slot_count` **(integer)** — Overlap Slot Count 🔒 readonly
- `is_past` **(boolean)** — Is This Shift In The Past? 🔒 readonly
- `is_users_role` **(boolean)** — Is the shifts role one of the current user roles 🔒 readonly
- `allocation_type` **(selection)** — Allocation Type 🔒 readonly
  > Opções: `planning` (Planning), `forecast` (Forecast)
- `duration` **(float)** — Duration 🔒 readonly
- `allow_template_creation` **(boolean)** — Allow Template Creation 🔒 readonly
- `confirm_delete` **(boolean)** — Confirm Delete 🔒 readonly
- `is_hatched` **(boolean)** — Is Hatched 🔒 readonly
- `sale_order_state` **(selection)** — Sales Order State 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
- `sale_line_plannable` **(boolean)** — Plan Services 🔒 readonly
  > If enabled, a shift will automatically be generated for the selected role when confirming the Sales Order.                 With the 'auto plan' feature, only employees with this role will be automatically assigned shifts for Sales Orders containing this service.                 The system will consider employee availability and the remaining time to be planned.                 You can also manually schedule open shifts for your Sales Order or assign them to any employee you prefer.
