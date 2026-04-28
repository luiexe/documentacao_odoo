# Signature Request — `sign.request`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `template_id` **(many2one)** — Template ⚠️ obrigatório → `sign.template`
- `reference` **(char)** — Document Name ⚠️ obrigatório
  > This is how the document will be named in the mail
- `access_token` **(char)** — Security Token ⚠️ obrigatório 🔒 readonly
- `send_channel` **(selection)** — Delivery Method ⚠️ obrigatório
  > Opções: `email` (Email), `whatsapp` (WhatsApp)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `subject` **(char)** — Email Subject
- `reference_doc` **(reference)** — Linked To
  > Opções: `account.account` (Account), `account.return` (Accounting Return), `account.return.type` (Accounting Return Type), `account.analytic.account` (Analytic Account), `hr.applicant` (Applicant), `appointment.type` (Appointment Type), `hr.appraisal.goal` (Appraisal Goal), `approval.request` (Approval Request), `knowledge.article.thread` (Article Discussion Thread), `account.asset` (Asset/Revenue Recognition), `hr.attendance` (Attendance), `base.automation` (Automation Rule), `res.partner.bank` (Bank Accounts), `account.online.link` (Bank Connection), `account.bank.statement` (Bank Statement), `account.bank.statement.line` (Bank Statement Line), `extract.mixin` (Base class to extract data from documents), `extract.mixin.with.words` (Base class to extract data from documents with OCRed words saved), `mrp.bom` (Bill of Material), `blog.blog` (Blog), `blog.post` (Blog Post), `budget.analytic` (Budget), `calendar.event` (Calendar Event), `sale.commission.plan` (Commission Plan), `res.company` (Companies), `res.partner` (Contact), `slide.channel` (Course), `hr.department` (Department), `discuss.channel` (Discussion Channel), `documents.document` (Document), `mrp.eco.type` (ECO Type), `mail.thread.cc` (Email CC management), `mail.thread` (Email Thread), `hr.employee` (Employee), `hr.appraisal` (Employee Appraisal), `mrp.eco` (Engineering Change Order (ECO)), `hr.expense` (Expense), `gamification.badge` (Gamification Badge), `gamification.challenge` (Gamification Challenge), `gamification.badge.user` (Gamification User Badge), `helpdesk.team` (Helpdesk Team), `helpdesk.ticket` (Helpdesk Ticket), `iap.account` (IAP Account), `hr.job` (Job Position), `account.journal` (Journal), `account.move` (Journal Entry), `knowledge.article` (Knowledge Article), `crm.lead` (Lead), `account.loan` (Loan), `stock.lot` (Lot/Serial), `loyalty.card` (Loyalty Coupon), `mail.blacklist` (Mail Blacklist), `mail.thread.blacklist` (Mail Blacklist mixin), `mail.thread.main.attachment` (Mail Main Attachment management), `mailing.contact` (Mailing Contact), `mrp.production` (Manufacturing Order), `mailing.mailing` (Mass Mailing), `mail.tracking.duration.mixin` (Mixin to compute the time a record has spent in each value a many2one field can take), `account.payment` (Payments), `phone.blacklist` (Phone Blacklist), `mail.thread.phone` (Phone Blacklist Mixin), `account.reconcile.model` (Preset to create journal entries during a invoices and payments matching), `product.pricelist` (Pricelist), `product.template` (Product), `product.category` (Product Category), `product.feed` (Product Feed), `product.product` (Product Variant), `project.project` (Project), `project.milestone` (Project Milestone), `project.update` (Project Update), `purchase.order` (Purchase Order), `quality.alert` (Quality Alert), `quality.alert.team` (Quality Alert Team), `quality.check` (Quality Check), `quality.point` (Quality Control Point), `rating.mixin` (Rating Mixin), `sale.order` (Sales Order), `crm.team` (Sales Team), `crm.team.member` (Sales Team Member), `ir.cron` (Scheduled Actions), `stock.scrap` (Scrap), `ir.actions.server` (Server Action), `slide.slide` (Slides), `spreadsheet.cell.thread` (Spreadsheet discussion thread), `studio.approval.rule` (Studio Approval Rule), `survey.survey` (Survey), `survey.user_input` (Survey User Input), `hr.talent.pool` (Talent Pool), `project.task` (Task), `account.tax` (Tax), `stock.picking` (Transfer), `mrp.unbuild` (Unbuild Order), `hr.version` (Version), `whatsapp.account` (WhatsApp Business Account), `whatsapp.template` (WhatsApp Template), `mrp.workcenter` (Work Center), `mrp.routing.workcenter` (Work Center Usage)
- `share_link` **(char)** — Share Link
- `is_shared` **(boolean)** — Share Request Button
- `state` **(selection)** — State
  > Opções: `shared` (Shared), `sent` (To Sign), `signed` (Signed), `canceled` (Cancelled), `expired` (Expired)
- `nb_wait` **(integer)** — Sent Requests 🔒 readonly
- `nb_closed` **(integer)** — Completed Signatures 🔒 readonly
- `nb_total` **(integer)** — Requested Signatures 🔒 readonly
- `active` **(boolean)** — Active
- `color` **(integer)** — Color
- `completion_date` **(date)** — Completion Date 🔒 readonly
- `message` **(html)** — sign.message
- `message_cc` **(html)** — sign.message_cc
- `validity` **(date)** — Valid Until
- `reminder_enabled` **(boolean)** — Reminder Enabled
- `reminder` **(integer)** — Reminder
- `last_reminder` **(date)** — Last reminder
- `certificate_reference` **(boolean)** — Certificate Reference
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `refusal_reason` **(char)** — Refusal reason

## Relacionamentos

- `request_item_ids` **(one2many)** — Signers → `sign.request.item`
- `template_document_ids` **(many2many)** — Documents 🔒 readonly → `sign.document`
- `completed_document_ids` **(one2many)** — Completed Documents Binaries → `sign.completed.document`
- `favorited_ids` **(many2many)** — Favorite of → `res.users`
- `communication_company_id` **(many2one)** — Company used for communication → `res.company`
- `sign_log_ids` **(one2many)** — Logs → `sign.log`
  > Activity logs linked to this request
- `template_tags` **(many2many)** — Tags → `sign.template.tag`
- `cc_partner_ids` **(many2many)** — Copy to 🔒 readonly → `res.partner`
- `attachment_ids` **(many2many)** — Attachments 🔒 readonly → `ir.attachment`
- `completed_document_attachment_ids` **(many2many)** — Completed Documents 🔒 readonly → `ir.attachment`
- `refuser_partner` **(many2one)** — Refuser Partner 🔒 readonly → `res.partner`

## Campos Calculados (readonly)

- `progress` **(char)** — Progress 🔒 readonly
- `start_sign` **(boolean)** — Signature Started 🔒 readonly
  > At least one signer has signed the document.
- `integrity` **(boolean)** — Integrity of the Sign request 🔒 readonly
- `request_item_infos` **(binary)** — Request Item Infos 🔒 readonly
- `last_action_date` **(datetime)** — Last Action Date 🔒 readonly
- `need_my_signature` **(boolean)** — Need My Signature 🔒 readonly
- `signers_name` **(char)** — Signers name 🔒 readonly
- `raw_optional_message` **(char)** — Optional Message 🔒 readonly
