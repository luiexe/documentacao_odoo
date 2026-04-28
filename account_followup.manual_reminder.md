# Wizard for sending manual reminders to clients — `account_followup.manual_reminder`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_ids` **(char)** — Document IDs ⚠️ obrigatório
- `res_model` **(char)** — Document Model Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `batch_mode` **(boolean)** — Is Multiple Records
- `phone` **(char)** — Phone
- `header_text_1` **(char)** — Header Free Text
- `free_text_1` **(char)** — Free Text 1
- `free_text_2` **(char)** — Free Text 2
- `free_text_3` **(char)** — Free Text 3
- `free_text_4` **(char)** — Free Text 4
- `free_text_5` **(char)** — Free Text 5
- `free_text_6` **(char)** — Free Text 6
- `free_text_7` **(char)** — Free Text 7
- `free_text_8` **(char)** — Free Text 8
- `free_text_9` **(char)** — Free Text 9
- `free_text_10` **(char)** — Free Text 10
- `button_dynamic_url_1` **(char)** — Button Url 1
- `button_dynamic_url_2` **(char)** — Button Url 2
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `email` **(boolean)** — Email
- `sms` **(boolean)** — Sms
- `sms_body` **(char)** — Sms Body
- `print` **(boolean)** — Print
- `join_invoices` **(boolean)** — Attach Invoices
- `snailmail` **(boolean)** — Snailmail
- `whatsapp` **(boolean)** — Whatsapp

## Relacionamentos

- `attachment_id` **(many2one)** — WhatsApp attachment → `ir.attachment`
- `wa_template_id` **(many2one)** — Template → `whatsapp.template`
- `template_id` **(many2one)** — Mail Template → `mail.template`
- `partner_id` **(many2one)** — Partner → `res.partner`
- `email_recipient_ids` **(many2many)** — Extra Recipients → `res.partner`
- `sms_template_id` **(many2one)** — Sms Template → `sms.template`
- `attachment_ids` **(many2many)** — Attachment → `ir.attachment`

## Campos Calculados (readonly)

- `invalid_phone_number_count` **(integer)** — Invalid Phone Number Count 🔒 readonly
- `preview_whatsapp` **(html)** — Message Preview 🔒 readonly
- `number_of_free_text` **(integer)** — Number of free text 🔒 readonly
- `number_of_free_text_button` **(integer)** — Number of free text Buttons 🔒 readonly
- `is_header_free_text` **(boolean)** — Is Header Free Text 🔒 readonly
- `is_button_dynamic` **(boolean)** — Is Button Dynamic 🔒 readonly
- `is_demo_account` **(boolean)** — Is Demo Account 🔒 readonly
- `render_model` **(char)** — Rendering Model 🔒 readonly
- `body_has_template_value` **(boolean)** — Body content is the same as the template 🔒 readonly
- `is_mail_template_editor` **(boolean)** — Is Editor 🔒 readonly
- `can_edit_body` **(boolean)** — Can Edit Body 🔒 readonly
- `show_send_button` **(boolean)** — Show Send Button 🔒 readonly
- `show_print_button` **(boolean)** — Show Print Button 🔒 readonly
- `snailmail_cost` **(float)** — Stamps 🔒 readonly
