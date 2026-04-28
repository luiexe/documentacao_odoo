# Email composition wizard — `mail.compose.message`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `message_type` **(selection)** — Type ⚠️ obrigatório
  > Message type: email for email message, notification for system message, comment for other messages such as user replies
  > Opções: `auto_comment` (Automated Targeted Notification), `comment` (Comment), `notification` (System notification)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `subject` **(char)** — Subject
- `body` **(html)** — Contents
- `email_layout_xmlid` **(char)** — Email Notification Layout
- `email_add_signature` **(boolean)** — Add signature
- `email_from` **(char)** — From
  > Email address of the sender. This field is set when no matching partner is found and replaces the author_id field in the chatter.
- `composition_mode` **(selection)** — Composition mode
  > Opções: `comment` (Post on a document), `mass_mail` (Email Mass Mailing)
- `composition_comment_option` **(selection)** — Comment Options
  > Opções: `reply_all` (Reply-All), `forward` (Forward)
- `model` **(char)** — Related Document Model
- `res_ids` **(text)** — Related Document IDs
- `res_domain` **(text)** — Active domain
- `reply_to` **(char)** — Reply To
  > Reply email address. Setting the reply_to bypasses the automatic thread creation.
- `reply_to_force_new` **(boolean)** — Considers answers as new thread
  > Manage answers as new incoming emails instead of replies going to the same thread.
- `reply_to_mode` **(selection)** — Replies
  > Original Discussion: Answers go in the original document discussion thread.   Another Email Address: Answers go to the email address mentioned in the tracking message-id instead of original document discussion thread.   This has an impact on the generated message-id.
  > Opções: `update` (Store email and replies in the chatter of each record), `new` (Collect replies on a specific email address)
- `auto_delete` **(boolean)** — Delete Emails
  > This option permanently removes any track of email after it's been sent, including from the Technical menu in the Settings, in order to preserve storage space of your Odoo database.
- `auto_delete_keep_log` **(boolean)** — Keep Message Copy
  > Keep a copy of the email content if emails are removed (mass mailing only)
- `force_send` **(boolean)** — Send mailing or notifications directly
- `notify_author` **(boolean)** — Notify Author
- `notify_author_mention` **(boolean)** — Notify Author Mention
- `notify_skip_followers` **(boolean)** — Notify Skip Followers
- `scheduled_date` **(char)** — Scheduled Date
  > In comment mode: if set, postpone notifications sending. In mass mail mode: if sent, send emails after that date. This date is considered as being in UTC timezone.
- `use_exclusion_list` **(boolean)** — Use Exclusion List
  > Prevent sending messages to blacklisted contacts. Disable only when absolutely necessary.
- `template_name` **(char)** — Template Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `mass_mailing_name` **(char)** — Mass Mailing Name
  > If set, a mass mailing will be created so that you can track its results in the Email Marketing app.
- `account_reports_annotation_date` **(date)** — Annotated For

## Relacionamentos

- `template_id` **(many2one)** — Use template → `mail.template`
- `parent_id` **(many2one)** — Parent Message → `mail.message`
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `author_id` **(many2one)** — Author → `res.partner`
  > Author of the message. If not set, email_from may hold an email address that did not match any partner.
- `res_domain_user_id` **(many2one)** — Responsible → `res.users`
  > Used as context used to evaluate composer domain
- `record_alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `record_company_id` **(many2one)** — Company → `res.company`
- `subtype_id` **(many2one)** — Subtype → `mail.message.subtype`
- `mail_activity_type_id` **(many2one)** — Mail Activity Type → `mail.activity.type`
- `partner_ids` **(many2many)** — Additional Contacts → `res.partner`
- `mail_server_id` **(many2one)** — Outgoing mail server → `ir.mail_server`
- `mass_mailing_id` **(many2one)** — Mass Mailing → `mailing.mailing`
- `campaign_id` **(many2one)** — Mass Mailing Campaign → `utm.campaign`
- `mailing_list_ids` **(many2many)** — Mailing List → `mailing.list`
- `marketing_activity_id` **(many2one)** — Marketing Activity → `marketing.activity`

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `body_has_template_value` **(boolean)** — Body content is the same as the template 🔒 readonly
- `is_mail_template_editor` **(boolean)** — Is Editor 🔒 readonly
- `can_edit_body` **(boolean)** — Can Edit Body 🔒 readonly
- `composition_batch` **(boolean)** — Batch composition 🔒 readonly
- `model_is_thread` **(boolean)** — Thread-Enabled 🔒 readonly
- `subtype_is_log` **(boolean)** — Is a log 🔒 readonly
- `partner_ids_all_have_email` **(boolean)** — Partner Ids All Have Email 🔒 readonly
- `notified_bcc_contains_share` **(boolean)** — Is an external partner follower of the document? 🔒 readonly
