# Marketing Participant — `marketing.participant`

**Ordenação padrão:** `id ASC`

---

## Campos Obrigatórios

- `campaign_id` **(many2one)** — Campaign ⚠️ obrigatório → `marketing.campaign`
- `state` **(selection)** — State ⚠️ obrigatório
  > Removed means the related record does not exist anymore.
  > Opções: `running` (Running), `completed` (Completed), `unlinked` (Removed)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `model_name` **(char)** — Record model 🔒 readonly
- `res_id` **(integer)** — Record ID
- `resource_ref` **(reference)** — Record
  > Opções: `account.account` (Account), `account.return` (Accounting Return), `account.return.type` (Accounting Return Type), `account.analytic.account` (Analytic Account), `hr.applicant` (Applicant), `appointment.type` (Appointment Type), `hr.appraisal.goal` (Appraisal Goal), `approval.request` (Approval Request), `knowledge.article.thread` (Article Discussion Thread), `account.asset` (Asset/Revenue Recognition), `hr.attendance` (Attendance), `base.automation` (Automation Rule), `res.partner.bank` (Bank Accounts), `account.online.link` (Bank Connection), `account.bank.statement` (Bank Statement), `account.bank.statement.line` (Bank Statement Line), `extract.mixin` (Base class to extract data from documents), `extract.mixin.with.words` (Base class to extract data from documents with OCRed words saved), `mrp.bom` (Bill of Material), `blog.blog` (Blog), `blog.post` (Blog Post), `budget.analytic` (Budget), `calendar.event` (Calendar Event), `sale.commission.plan` (Commission Plan), `res.company` (Companies), `res.partner` (Contact), `slide.channel` (Course), `hr.department` (Department), `discuss.channel` (Discussion Channel), `documents.document` (Document), `mrp.eco.type` (ECO Type), `mail.thread.cc` (Email CC management), `mail.thread` (Email Thread), `hr.employee` (Employee), `hr.appraisal` (Employee Appraisal), `mrp.eco` (Engineering Change Order (ECO)), `hr.expense` (Expense), `gamification.badge` (Gamification Badge), `gamification.challenge` (Gamification Challenge), `gamification.badge.user` (Gamification User Badge), `helpdesk.team` (Helpdesk Team), `helpdesk.ticket` (Helpdesk Ticket), `iap.account` (IAP Account), `hr.job` (Job Position), `account.journal` (Journal), `account.move` (Journal Entry), `knowledge.article` (Knowledge Article), `crm.lead` (Lead), `account.loan` (Loan), `stock.lot` (Lot/Serial), `loyalty.card` (Loyalty Coupon), `mail.blacklist` (Mail Blacklist), `mail.thread.blacklist` (Mail Blacklist mixin), `mail.thread.main.attachment` (Mail Main Attachment management), `mailing.contact` (Mailing Contact), `mrp.production` (Manufacturing Order), `mailing.mailing` (Mass Mailing), `mail.tracking.duration.mixin` (Mixin to compute the time a record has spent in each value a many2one field can take), `account.payment` (Payments), `phone.blacklist` (Phone Blacklist), `mail.thread.phone` (Phone Blacklist Mixin), `account.reconcile.model` (Preset to create journal entries during a invoices and payments matching), `product.pricelist` (Pricelist), `product.template` (Product), `product.category` (Product Category), `product.feed` (Product Feed), `product.product` (Product Variant), `project.project` (Project), `project.milestone` (Project Milestone), `project.update` (Project Update), `purchase.order` (Purchase Order), `quality.alert` (Quality Alert), `quality.alert.team` (Quality Alert Team), `quality.check` (Quality Check), `quality.point` (Quality Control Point), `rating.mixin` (Rating Mixin), `sale.order` (Sales Order), `crm.team` (Sales Team), `crm.team.member` (Sales Team Member), `ir.cron` (Scheduled Actions), `stock.scrap` (Scrap), `ir.actions.server` (Server Action), `sign.request` (Signature Request), `slide.slide` (Slides), `spreadsheet.cell.thread` (Spreadsheet discussion thread), `studio.approval.rule` (Studio Approval Rule), `survey.survey` (Survey), `survey.user_input` (Survey User Input), `hr.talent.pool` (Talent Pool), `project.task` (Task), `account.tax` (Tax), `stock.picking` (Transfer), `mrp.unbuild` (Unbuild Order), `hr.version` (Version), `whatsapp.account` (WhatsApp Business Account), `whatsapp.template` (WhatsApp Template), `mrp.workcenter` (Work Center), `mrp.routing.workcenter` (Work Center Usage)
- `is_test` **(boolean)** — Test Record
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
- `trace_ids` **(one2many)** — Actions → `marketing.trace`
