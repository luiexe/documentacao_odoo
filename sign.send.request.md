# Sign send request — `sign.send.request`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `reference_doc` **(reference)** — Linked to 🔒 readonly
  > Opções: `account.account` (Account), `account.return` (Accounting Return), `account.return.type` (Accounting Return Type), `account.analytic.account` (Analytic Account), `hr.applicant` (Applicant), `appointment.type` (Appointment Type), `hr.appraisal.goal` (Appraisal Goal), `approval.request` (Approval Request), `knowledge.article.thread` (Article Discussion Thread), `account.asset` (Asset/Revenue Recognition), `hr.attendance` (Attendance), `base.automation` (Automation Rule), `res.partner.bank` (Bank Accounts), `account.online.link` (Bank Connection), `account.bank.statement` (Bank Statement), `account.bank.statement.line` (Bank Statement Line), `extract.mixin` (Base class to extract data from documents), `extract.mixin.with.words` (Base class to extract data from documents with OCRed words saved), `mrp.bom` (Bill of Material), `blog.blog` (Blog), `blog.post` (Blog Post), `budget.analytic` (Budget), `calendar.event` (Calendar Event), `sale.commission.plan` (Commission Plan), `res.company` (Companies), `res.partner` (Contact), `slide.channel` (Course), `hr.department` (Department), `discuss.channel` (Discussion Channel), `documents.document` (Document), `mrp.eco.type` (ECO Type), `mail.thread.cc` (Email CC management), `mail.thread` (Email Thread), `hr.employee` (Employee), `hr.appraisal` (Employee Appraisal), `mrp.eco` (Engineering Change Order (ECO)), `hr.expense` (Expense), `gamification.badge` (Gamification Badge), `gamification.challenge` (Gamification Challenge), `gamification.badge.user` (Gamification User Badge), `helpdesk.team` (Helpdesk Team), `helpdesk.ticket` (Helpdesk Ticket), `iap.account` (IAP Account), `hr.job` (Job Position), `account.journal` (Journal), `account.move` (Journal Entry), `knowledge.article` (Knowledge Article), `crm.lead` (Lead), `account.loan` (Loan), `stock.lot` (Lot/Serial), `loyalty.card` (Loyalty Coupon), `mail.blacklist` (Mail Blacklist), `mail.thread.blacklist` (Mail Blacklist mixin), `mail.thread.main.attachment` (Mail Main Attachment management), `mailing.contact` (Mailing Contact), `mrp.production` (Manufacturing Order), `mailing.mailing` (Mass Mailing), `mail.tracking.duration.mixin` (Mixin to compute the time a record has spent in each value a many2one field can take), `account.payment` (Payments), `phone.blacklist` (Phone Blacklist), `mail.thread.phone` (Phone Blacklist Mixin), `account.reconcile.model` (Preset to create journal entries during a invoices and payments matching), `product.pricelist` (Pricelist), `product.template` (Product), `product.category` (Product Category), `product.feed` (Product Feed), `product.product` (Product Variant), `project.project` (Project), `project.milestone` (Project Milestone), `project.update` (Project Update), `purchase.order` (Purchase Order), `quality.alert` (Quality Alert), `quality.alert.team` (Quality Alert Team), `quality.check` (Quality Check), `quality.point` (Quality Control Point), `rating.mixin` (Rating Mixin), `sale.order` (Sales Order), `crm.team` (Sales Team), `crm.team.member` (Sales Team Member), `ir.cron` (Scheduled Actions), `stock.scrap` (Scrap), `ir.actions.server` (Server Action), `slide.slide` (Slides), `spreadsheet.cell.thread` (Spreadsheet discussion thread), `studio.approval.rule` (Studio Approval Rule), `survey.survey` (Survey), `survey.user_input` (Survey User Input), `hr.talent.pool` (Talent Pool), `project.task` (Task), `account.tax` (Tax), `stock.picking` (Transfer), `mrp.unbuild` (Unbuild Order), `hr.version` (Version), `whatsapp.account` (WhatsApp Business Account), `whatsapp.template` (WhatsApp Template), `mrp.workcenter` (Work Center), `mrp.routing.workcenter` (Work Center Usage)
- `has_default_template` **(boolean)** — Has Default Template
- `set_sign_order` **(boolean)** — Signing Order
  > Specify the order for each signer. The signature request only gets sent to                                     the next signers in the sequence when all signers from the previous level have                                     signed the document.                                     
- `subject` **(char)** — Subject
- `body` **(html)** — body
  > Message to be sent to signers of the specified document
- `message_cc` **(html)** — CC Message
  > Message to be sent to contacts in copy of the signed document
- `filename` **(char)** — Filename 🔒 readonly
- `validity` **(date)** — Valid Until
  > Leave empty for requests without expiration.
- `reminder_enabled` **(boolean)** — Reminder Enabled
- `reminder` **(integer)** — Reminder
- `certificate_reference` **(boolean)** — Certificate Reference
  > If checked, the unique certificate reference will be added on the final signed document.
- `model` **(char)** — Related Document Model
- `res_ids` **(text)** — Related Document IDs
- `scheduled_date` **(char)** — Scheduled Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `activity_id` **(many2one)** — Linked Activity 🔒 readonly → `mail.activity`
- `available_template_ids` **(many2many)** — Available Template 🔒 readonly → `sign.template`
- `template_id` **(many2one)** — Sign Template → `sign.template`
- `signer_ids` **(one2many)** — Signers 🔒 readonly → `sign.send.request.signer`
- `signer_id` **(many2one)** — Send To → `res.partner`
- `cc_partner_ids` **(many2many)** — Copy to → `res.partner`
  > Contacts in copy will be notified by email once the document is either fully signed or refused.
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`

## Campos Calculados (readonly)

- `signers_count` **(integer)** — Signers Count 🔒 readonly
- `is_user_signer` **(boolean)** — Is User Signer 🔒 readonly
- `only_autofill_readonly` **(boolean)** — Only Autofill 🔒 readonly
- `display_download_button` **(boolean)** — Display Download Button 🔒 readonly
- `is_whatsapp_feature_enabled` **(boolean)** — Is Whatsapp Feature Enabled 🔒 readonly
