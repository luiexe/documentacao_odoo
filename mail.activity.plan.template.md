# Activity plan template — `mail.activity.plan.template`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `plan_id` **(many2one)** — Plan ⚠️ obrigatório → `mail.activity.plan`
- `delay_unit` **(selection)** — Delay units ⚠️ obrigatório
  > Unit of delay
  > Opções: `days` (days), `weeks` (weeks), `months` (months)
- `delay_from` **(selection)** — Trigger ⚠️ obrigatório
  > Opções: `before_plan_date` (Before Plan Date), `after_plan_date` (After Plan Date)
- `responsible_type` **(selection)** — Assignment ⚠️ obrigatório
  > Opções: `on_demand` (Ask at launch), `other` (Default user), `coach` (Coach), `manager` (Manager), `employee` (Employee)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `delay_count` **(integer)** — Interval
  > Number of days/week/month before executing the action after or before the scheduled plan date.
- `summary` **(char)** — Summary
- `note` **(html)** — Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `responsible_id` **(many2one)** — Assigned to → `res.users`
- `next_activity_ids` **(many2many)** — Next Activities → `mail.activity.type`
- `sign_template_id` **(many2one)** — Document to sign → `sign.template`
- `employee_role_id` **(many2one)** — Employee Role → `sign.item.role`
  > Employee's role on the templates to sign. The same role must be present in all the templates
- `sign_template_responsible_ids` **(many2many)** — Sign Template Responsible 🔒 readonly → `sign.item.role`

## Campos Calculados (readonly)

- `res_model` **(selection)** — Model 🔒 readonly
  > Specify a model if the activity should be specific to a model and not available when managing activities for other models.
  > Opções: `account.account` (Account), `account.return` (Accounting Return), `hr.applicant` (Applicant), `appointment.type` (Appointment Type), `hr.appraisal.goal` (Appraisal Goal), `approval.request` (Approval Request), `account.asset` (Asset/Revenue Recognition), `base.automation` (Automation Rule), `res.partner.bank` (Bank Accounts), `account.online.link` (Bank Connection), `mrp.bom` (Bill of Material), `budget.analytic` (Budget), `res.partner` (Contact), `slide.channel` (Course), `hr.department` (Department), `documents.document` (Document), `hr.employee` (Employee), `hr.appraisal` (Employee Appraisal), `mrp.eco` (Engineering Change Order (ECO)), `hr.expense` (Expense), `helpdesk.ticket` (Helpdesk Ticket), `hr.job` (Job Position), `account.journal` (Journal), `account.move` (Journal Entry), `knowledge.article` (Knowledge Article), `crm.lead` (Lead), `stock.lot` (Lot/Serial), `mrp.production` (Manufacturing Order), `mailing.mailing` (Mass Mailing), `account.payment` (Payments), `product.pricelist` (Pricelist), `product.template` (Product), `product.product` (Product Variant), `project.project` (Project), `project.update` (Project Update), `purchase.order` (Purchase Order), `quality.alert` (Quality Alert), `quality.check` (Quality Check), `sale.order` (Sales Order), `ir.cron` (Scheduled Actions), `ir.actions.server` (Server Action), `sign.request` (Signature Request), `survey.survey` (Survey), `survey.user_input` (Survey User Input), `project.task` (Task), `stock.picking` (Transfer), `mrp.unbuild` (Unbuild Order), `hr.version` (Version), `mrp.routing.workcenter` (Work Center Usage), `mail.activity.mixin` (Activity Mixin)
- `icon` **(char)** — Icon 🔒 readonly
  > Font awesome icon e.g. fa-tasks
- `responsible_count` **(integer)** — Responsible Count 🔒 readonly
- `is_signature_request` **(boolean)** — Is Signature Request 🔒 readonly
