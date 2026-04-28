# Activity Plan — `mail.activity.plan`

**Ordenação padrão:** `id DESC`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `res_model_id` **(many2one)** — Applies to ⚠️ obrigatório → `ir.model`
- `res_model` **(selection)** — Model ⚠️ obrigatório
  > Specify a model if the activity should be specific to a model and not available when managing activities for other models.
  > Opções: `account.account` (Account), `account.return` (Accounting Return), `hr.applicant` (Applicant), `appointment.type` (Appointment Type), `hr.appraisal.goal` (Appraisal Goal), `approval.request` (Approval Request), `account.asset` (Asset/Revenue Recognition), `base.automation` (Automation Rule), `res.partner.bank` (Bank Accounts), `account.online.link` (Bank Connection), `mrp.bom` (Bill of Material), `budget.analytic` (Budget), `res.partner` (Contact), `slide.channel` (Course), `hr.department` (Department), `documents.document` (Document), `hr.employee` (Employee), `hr.appraisal` (Employee Appraisal), `mrp.eco` (Engineering Change Order (ECO)), `hr.expense` (Expense), `helpdesk.ticket` (Helpdesk Ticket), `hr.job` (Job Position), `account.journal` (Journal), `account.move` (Journal Entry), `knowledge.article` (Knowledge Article), `crm.lead` (Lead), `stock.lot` (Lot/Serial), `mrp.production` (Manufacturing Order), `mailing.mailing` (Mass Mailing), `account.payment` (Payments), `product.pricelist` (Pricelist), `product.template` (Product), `product.product` (Product Variant), `project.project` (Project), `project.update` (Project Update), `purchase.order` (Purchase Order), `quality.alert` (Quality Alert), `quality.check` (Quality Check), `sale.order` (Sales Order), `ir.cron` (Scheduled Actions), `ir.actions.server` (Server Action), `sign.request` (Signature Request), `survey.survey` (Survey), `survey.user_input` (Survey User Input), `project.task` (Task), `stock.picking` (Transfer), `mrp.unbuild` (Unbuild Order), `hr.version` (Version), `mrp.routing.workcenter` (Work Center Usage), `mail.activity.mixin` (Activity Mixin)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `template_ids` **(one2many)** — Activities → `mail.activity.plan.template`
- `department_id` **(many2one)** — Department → `hr.department`

## Campos Calculados (readonly)

- `steps_count` **(integer)** — Steps Count 🔒 readonly
- `has_user_on_demand` **(boolean)** — Has on demand responsible 🔒 readonly
- `department_assignable` **(boolean)** — Department Assignable 🔒 readonly
