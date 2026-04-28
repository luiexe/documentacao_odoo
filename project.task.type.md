# Task Stage — `project.task.type`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `rating_status` **(selection)** — Customer Ratings Status ⚠️ obrigatório
  > Collect feedback from your customers by sending them a rating request when a task enters a certain stage. To do so, define a rating email template on the stage. Rating when changing stage: an email will be automatically sent when a task reaches the stage. Periodic rating: an email will be automatically sent at regular intervals as long as the task remains in the stage.
  > Opções: `stage` (when reaching this stage), `periodic` (on a periodic basis)
- `rating_status_period` **(selection)** — Rating Frequency ⚠️ obrigatório
  > Opções: `daily` (Daily), `weekly` (Weekly), `bimonthly` (Twice a Month), `monthly` (Once a Month), `quarterly` (Quarterly), `yearly` (Yearly)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `color` **(integer)** — Color
- `fold` **(boolean)** — Folded
- `auto_validation_state` **(boolean)** — Automatic Kanban Status
  > Automatically modify the state when the customer replies to the feedback for this stage.  * Good feedback from the customer will update the state to 'Approved' (green bullet).  * Neutral or bad feedback will set the kanban state to 'Changes Requested' (orange bullet). 
- `rotting_threshold_days` **(integer)** — Days to rot
  > Day count before tasks in this stage become stale. Set to 0 to disable         Changing this parameter will not affect the rotting status/date of resources last updated before this change.
- `rating_request_deadline` **(datetime)** — Rating Request Deadline 🔒 readonly
- `rating_active` **(boolean)** — Send a customer rating request
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `project_ids` **(many2many)** — Projects → `project.project`
  > Projects in which this stage is present. If you follow a similar workflow in several projects, you can share this stage among them and get consolidated information this way.
- `mail_template_id` **(many2one)** — Email Template → `mail.template`
  > If set, an email will be automatically sent to the customer when the task reaches this stage.
- `rating_template_id` **(many2one)** — Rating Email Template → `mail.template`
  > If set, a rating request will automatically be sent by email to the customer when the task reaches this stage.  Alternatively, it will be sent at a regular interval as long as the task remains in this stage.
- `user_id` **(many2one)** — Stage Owner 🔒 readonly → `res.users`
- `sms_template_id` **(many2one)** — SMS Template → `sms.template`
  > If set, an SMS Text Message will be automatically sent to the customer when the task reaches this stage.

## Campos Calculados (readonly)

- `show_rating_active` **(boolean)** — Show Rating Active 🔒 readonly
