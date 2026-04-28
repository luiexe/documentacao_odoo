# Activity schedule plan Wizard — `mail.activity.schedule`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_model` **(char)** — Model
- `res_ids` **(text)** — Document IDs
- `plan_date` **(date)** — Plan Date
- `date_deadline` **(date)** — Due Date
- `summary` **(char)** — Summary
- `note` **(html)** — Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `res_model_id` **(many2one)** — Applies to → `ir.model`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `plan_available_ids` **(many2many)** — Plan Available 🔒 readonly → `mail.activity.plan`
- `plan_id` **(many2one)** — Plan → `mail.activity.plan`
- `plan_schedule_line_ids` **(one2many)** — Schedule Lines 🔒 readonly → `mail.activity.schedule.line`
- `plan_on_demand_user_id` **(many2one)** — Assigned To → `res.users`
  > Choose assignation for activities with on demand assignation.
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`

## Campos Calculados (readonly)

- `is_batch_mode` **(boolean)** — Use in batch 🔒 readonly
- `error` **(html)** — Error 🔒 readonly
- `has_error` **(boolean)** — Has Error 🔒 readonly
- `warning` **(html)** — Warning 🔒 readonly
- `has_warning` **(boolean)** — Has Warning 🔒 readonly
- `plan_has_user_on_demand` **(boolean)** — Has on demand responsible 🔒 readonly
- `activity_category` **(selection)** — Action 🔒 readonly
  > Actions may trigger specific behavior like opening calendar view or automatically mark as done when a document is uploaded
  > Opções: `default` (None), `upload_file` (Upload Document), `phonecall` (Phonecall), `meeting` (Meeting), `sign_request` (Signature)
- `chaining_type` **(selection)** — Chaining Type 🔒 readonly
  > Opções: `suggest` (Suggest Next Activity), `trigger` (Trigger Next Activity)
- `plan_department_filterable` **(boolean)** — Plan Department Filterable 🔒 readonly
