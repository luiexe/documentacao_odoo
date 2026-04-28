# Account Move Send Wizard — `account.move.send.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `move_id` **(many2one)** — Move ⚠️ obrigatório → `account.move`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `sending_methods` **(json)** — Sending Methods
- `sending_method_checkboxes` **(json)** — Sending Method Checkboxes
- `extra_edis` **(json)** — Extra Edis
- `extra_edi_checkboxes` **(json)** — Extra Edi Checkboxes
- `mail_attachments_widget` **(json)** — Mail Attachments Widget
- `model` **(char)** — Related Document Model
- `res_ids` **(text)** — Related Document IDs
- `template_name` **(char)** — Template Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Mail Template → `mail.template`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `pdf_report_id` **(many2one)** — Invoice report → `ir.actions.report`
- `available_pdf_report_ids` **(one2many)** — Available Pdf Report 🔒 readonly → `ir.actions.report`
- `mail_partner_ids` **(many2many)** — To → `res.partner`

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `body_has_template_value` **(boolean)** — Body content is the same as the template 🔒 readonly
- `is_mail_template_editor` **(boolean)** — Is Editor 🔒 readonly
- `can_edit_body` **(boolean)** — Can Edit Body 🔒 readonly
- `alerts` **(json)** — Alerts 🔒 readonly
- `display_attachments_widget` **(boolean)** — Display Attachments Widget 🔒 readonly
- `invoice_edi_format` **(selection)** — Invoice Edi Format 🔒 readonly
  > Opções: `facturx` (France (FacturX)), `ubl_bis3` (EU Standard (Peppol Bis 3.0)), `zugferd` (Germany (ZUGFeRD)), `xrechnung` (Germany (XRechnung)), `nlcius` (Netherlands (NLCIUS)), `ubl_a_nz` (Australia (BIS Billing 3.0 A-NZ)), `ubl_sg` (Singapore (BIS Billing 3.0 SG))
- `display_pdf_report_id` **(boolean)** — Display Pdf Report 🔒 readonly
- `attachments_not_supported` **(json)** — Attachments Not Supported 🔒 readonly
