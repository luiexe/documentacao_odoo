# Follow-up Criteria — `account_followup.followup.line`

**Ordenação padrão:** `delay asc`

---

## Campos Obrigatórios

- `name` **(char)** — Description ⚠️ obrigatório
- `delay` **(integer)** — Due Days ⚠️ obrigatório
  > The number of days after the due date of the invoice to wait before sending the reminder. Can be negative if you want to send the reminder before the invoice due date.
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `activity_default_responsible_type` **(selection)** — Responsible ⚠️ obrigatório
  > Determine who will be assigned to the activity: - Follow-up Responsible (default) - Salesperson: Sales Person defined on the invoice - Account Manager: Sales Person defined on the customer
  > Opções: `followup` (Follow-up Responsible), `salesperson` (Salesperson), `account_manager` (Account Manager)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `send_email` **(boolean)** — Email
- `join_invoices` **(boolean)** — Attach Invoices
- `send_sms` **(boolean)** — SMS
- `create_activity` **(boolean)** — Schedule Activity
- `activity_note` **(text)** — Note
- `auto_execute` **(boolean)** — Automatic
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `send_letter` **(boolean)** — Letter
- `send_whatsapp` **(boolean)** — WhatsApp

## Relacionamentos

- `mail_template_id` **(many2one)** — Mail Template → `mail.template`
- `additional_follower_ids` **(many2many)** — Add followers → `res.users`
  > If set, those users will be added as followers on the partner and receive notifications about any email reply made by the partner on the reminder email.
- `sms_template_id` **(many2one)** — Sms Template → `sms.template`
- `whatsapp_template_id` **(many2one)** — Whatsapp Template → `whatsapp.template`
