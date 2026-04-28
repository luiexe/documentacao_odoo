# Activity Type — `mail.activity.type`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `delay_unit` **(selection)** — Delay units ⚠️ obrigatório
  > Unit of delay
  > Opções: `days` (days), `weeks` (weeks), `months` (months)
- `delay_from` **(selection)** — Delay Type ⚠️ obrigatório
  > Type of delay
  > Opções: `current_date` (after previous activity completion date), `previous_activity` (after previous activity deadline)
- `chaining_type` **(selection)** — Chaining Type ⚠️ obrigatório
  > Opções: `suggest` (Suggest Next Activity), `trigger` (Trigger Next Activity)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `summary` **(char)** — Default Summary
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
- `delay_count` **(integer)** — Schedule
  > Number of days/week/month before executing the action. It allows to plan the action deadline.
- `icon` **(char)** — Icon
  > Font awesome icon e.g. fa-tasks
- `decoration_type` **(selection)** — Decoration Type
  > Change the background color of the related activities of this type.
  > Opções: `warning` (Alert), `danger` (Error)
- `res_model` **(selection)** — Model
  > Specify a model if the activity should be specific to a model and not available when managing activities for other models.
  > Opções: `account.account` (Account), `account.return` (Accounting Return), `account.return.type` (Accounting Return Type), `account.analytic.account` (Analytic Account), `hr.applicant` (Applicant), `appointment.type` (Appointment Type), `hr.appraisal.goal` (Appraisal Goal), `approval.request` (Approval Request), `knowledge.article.thread` (Article Discussion Thread), `account.asset` (Asset/Revenue Recognition), `hr.attendance` (Attendance), `base.automation` (Automation Rule), `res.partner.bank` (Bank Accounts), `account.online.link` (Bank Connection), `account.bank.statement` (Bank Statement), `account.bank.statement.line` (Bank Statement Line), `extract.mixin` (Base class to extract data from documents), `extract.mixin.with.words` (Base class to extract data from documents with OCRed words saved), `mrp.bom` (Bill of Material), `blog.blog` (Blog), `blog.post` (Blog Post), `budget.analytic` (Budget), `calendar.event` (Calendar Event), `sale.commission.plan` (Commission Plan), `res.company` (Companies), `res.partner` (Contact), `slide.channel` (Course), `hr.department` (Department), `discuss.channel` (Discussion Channel), `documents.document` (Document), `mrp.eco.type` (ECO Type), `mail.thread.cc` (Email CC management), `mail.thread` (Email Thread), `hr.employee` (Employee), `hr.appraisal` (Employee Appraisal), `mrp.eco` (Engineering Change Order (ECO)), `hr.expense` (Expense), `gamification.badge` (Gamification Badge), `gamification.challenge` (Gamification Challenge), `gamification.badge.user` (Gamification User Badge), `helpdesk.team` (Helpdesk Team), `helpdesk.ticket` (Helpdesk Ticket), `iap.account` (IAP Account), `hr.job` (Job Position), `account.journal` (Journal), `account.move` (Journal Entry), `knowledge.article` (Knowledge Article), `crm.lead` (Lead), `account.loan` (Loan), `stock.lot` (Lot/Serial), `loyalty.card` (Loyalty Coupon), `mail.blacklist` (Mail Blacklist), `mail.thread.blacklist` (Mail Blacklist mixin), `mail.thread.main.attachment` (Mail Main Attachment management), `mailing.contact` (Mailing Contact), `mrp.production` (Manufacturing Order), `mailing.mailing` (Mass Mailing), `mail.tracking.duration.mixin` (Mixin to compute the time a record has spent in each value a many2one field can take), `account.payment` (Payments), `phone.blacklist` (Phone Blacklist), `mail.thread.phone` (Phone Blacklist Mixin), `account.reconcile.model` (Preset to create journal entries during a invoices and payments matching), `product.pricelist` (Pricelist), `product.template` (Product), `product.category` (Product Category), `product.feed` (Product Feed), `product.product` (Product Variant), `project.project` (Project), `project.milestone` (Project Milestone), `project.update` (Project Update), `purchase.order` (Purchase Order), `quality.alert` (Quality Alert), `quality.alert.team` (Quality Alert Team), `quality.check` (Quality Check), `quality.point` (Quality Control Point), `rating.mixin` (Rating Mixin), `sale.order` (Sales Order), `crm.team` (Sales Team), `crm.team.member` (Sales Team Member), `ir.cron` (Scheduled Actions), `stock.scrap` (Scrap), `ir.actions.server` (Server Action), `sign.request` (Signature Request), `slide.slide` (Slides), `spreadsheet.cell.thread` (Spreadsheet discussion thread), `studio.approval.rule` (Studio Approval Rule), `survey.survey` (Survey), `survey.user_input` (Survey User Input), `hr.talent.pool` (Talent Pool), `project.task` (Task), `account.tax` (Tax), `stock.picking` (Transfer), `mrp.unbuild` (Unbuild Order), `hr.version` (Version), `whatsapp.account` (WhatsApp Business Account), `whatsapp.template` (WhatsApp Template), `mrp.workcenter` (Work Center), `mrp.routing.workcenter` (Work Center Usage)
- `category` **(selection)** — Action
  > Actions may trigger specific behavior like opening calendar view or automatically mark as done when a document is uploaded
  > Opções: `default` (None), `upload_file` (Upload Document), `phonecall` (Phonecall), `meeting` (Meeting), `sign_request` (Signature)
- `default_note` **(html)** — Default Note
- `res_model_change` **(boolean)** — Model has change
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `dashboard_visibility` **(selection)** — Dashboard Visibility
  > Whether this type of activity should be displayed on Odoo.com dashboard. None: never display this type of activity Own Activities: users will see only their own activities of this type on their dashboard All Activities: users will see the all the activities of this type on their dashboard, whatever their owner
  > Opções: `none` (None), `own` (Own Activities), `all` (All Activities)

## Relacionamentos

- `triggered_next_type_id` **(many2one)** — Trigger → `mail.activity.type`
  > Automatically schedule this activity once the current one is marked as done.
- `suggested_next_type_ids` **(many2many)** — Suggest → `mail.activity.type`
  > Suggest these activities once the current one is marked as done.
- `previous_type_ids` **(many2many)** — Preceding Activities → `mail.activity.type`
- `mail_template_ids` **(many2many)** — Email templates → `mail.template`
- `default_user_id` **(many2one)** — Default User → `res.users`
- `default_sign_template_id` **(many2one)** — Default Signature Template → `sign.template`
- `tag_ids` **(many2many)** — Tag → `documents.tag`
- `folder_id` **(many2one)** — Folder → `documents.document`
  > By defining a folder, the upload activities will generate a document

## Campos Calculados (readonly)

- `delay_label` **(char)** — Delay Label 🔒 readonly
- `initial_res_model` **(selection)** — Initial model 🔒 readonly
  > Technical field to keep track of the model at the start of editing to support UX related behaviour
  > Opções: `account.account` (Account), `account.return` (Accounting Return), `account.return.type` (Accounting Return Type), `account.analytic.account` (Analytic Account), `hr.applicant` (Applicant), `appointment.type` (Appointment Type), `hr.appraisal.goal` (Appraisal Goal), `approval.request` (Approval Request), `knowledge.article.thread` (Article Discussion Thread), `account.asset` (Asset/Revenue Recognition), `hr.attendance` (Attendance), `base.automation` (Automation Rule), `res.partner.bank` (Bank Accounts), `account.online.link` (Bank Connection), `account.bank.statement` (Bank Statement), `account.bank.statement.line` (Bank Statement Line), `extract.mixin` (Base class to extract data from documents), `extract.mixin.with.words` (Base class to extract data from documents with OCRed words saved), `mrp.bom` (Bill of Material), `blog.blog` (Blog), `blog.post` (Blog Post), `budget.analytic` (Budget), `calendar.event` (Calendar Event), `sale.commission.plan` (Commission Plan), `res.company` (Companies), `res.partner` (Contact), `slide.channel` (Course), `hr.department` (Department), `discuss.channel` (Discussion Channel), `documents.document` (Document), `mrp.eco.type` (ECO Type), `mail.thread.cc` (Email CC management), `mail.thread` (Email Thread), `hr.employee` (Employee), `hr.appraisal` (Employee Appraisal), `mrp.eco` (Engineering Change Order (ECO)), `hr.expense` (Expense), `gamification.badge` (Gamification Badge), `gamification.challenge` (Gamification Challenge), `gamification.badge.user` (Gamification User Badge), `helpdesk.team` (Helpdesk Team), `helpdesk.ticket` (Helpdesk Ticket), `iap.account` (IAP Account), `hr.job` (Job Position), `account.journal` (Journal), `account.move` (Journal Entry), `knowledge.article` (Knowledge Article), `crm.lead` (Lead), `account.loan` (Loan), `stock.lot` (Lot/Serial), `loyalty.card` (Loyalty Coupon), `mail.blacklist` (Mail Blacklist), `mail.thread.blacklist` (Mail Blacklist mixin), `mail.thread.main.attachment` (Mail Main Attachment management), `mailing.contact` (Mailing Contact), `mrp.production` (Manufacturing Order), `mailing.mailing` (Mass Mailing), `mail.tracking.duration.mixin` (Mixin to compute the time a record has spent in each value a many2one field can take), `account.payment` (Payments), `phone.blacklist` (Phone Blacklist), `mail.thread.phone` (Phone Blacklist Mixin), `account.reconcile.model` (Preset to create journal entries during a invoices and payments matching), `product.pricelist` (Pricelist), `product.template` (Product), `product.category` (Product Category), `product.feed` (Product Feed), `product.product` (Product Variant), `project.project` (Project), `project.milestone` (Project Milestone), `project.update` (Project Update), `purchase.order` (Purchase Order), `quality.alert` (Quality Alert), `quality.alert.team` (Quality Alert Team), `quality.check` (Quality Check), `quality.point` (Quality Control Point), `rating.mixin` (Rating Mixin), `sale.order` (Sales Order), `crm.team` (Sales Team), `crm.team.member` (Sales Team Member), `ir.cron` (Scheduled Actions), `stock.scrap` (Scrap), `ir.actions.server` (Server Action), `sign.request` (Signature Request), `slide.slide` (Slides), `spreadsheet.cell.thread` (Spreadsheet discussion thread), `studio.approval.rule` (Studio Approval Rule), `survey.survey` (Survey), `survey.user_input` (Survey User Input), `hr.talent.pool` (Talent Pool), `project.task` (Task), `account.tax` (Tax), `stock.picking` (Transfer), `mrp.unbuild` (Unbuild Order), `hr.version` (Version), `whatsapp.account` (WhatsApp Business Account), `whatsapp.template` (WhatsApp Template), `mrp.workcenter` (Work Center), `mrp.routing.workcenter` (Work Center Usage)
