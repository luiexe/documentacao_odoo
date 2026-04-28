# Mass Mailing — `mailing.mailing`

**Ordenação padrão:** `calendar_date DESC`

---

## Campos Obrigatórios

- `source_id` **(many2one)** — Source ⚠️ obrigatório → `utm.source`
- `subject` **(char)** — Subject ⚠️ obrigatório
- `schedule_type` **(selection)** — Schedule ⚠️ obrigatório
  > Opções: `now` (Send now), `scheduled` (Send on)
- `state` **(selection)** — Status ⚠️ obrigatório
  > Opções: `draft` (Draft), `in_queue` (In Queue), `sending` (Sending), `done` (Sent)
- `mailing_type` **(selection)** — Mailing Type ⚠️ obrigatório
  > Opções: `mail` (Email)
- `mailing_model_id` **(many2one)** — Recipients Model ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `active` **(boolean)** — Active
- `preview` **(char)** — Preview
  > Catchy preview sentence that encourages recipients to open this email. In most inboxes, this is displayed next to the subject. Keep it empty if you prefer the first characters of your email content to appear instead.
- `email_from` **(char)** — Send From
- `favorite` **(boolean)** — Favorite
- `favorite_date` **(datetime)** — Favorite Date 🔒 readonly
  > When this mailing was added in the favorites
- `sent_date` **(datetime)** — Sent Date
- `schedule_date` **(datetime)** — Scheduled for
- `calendar_date` **(datetime)** — Calendar Date 🔒 readonly
  > Date at which the mailing was or will be sent.
- `body_arch` **(html)** — Body
- `body_html` **(html)** — Body converted to be sent by mail
- `keep_archives` **(boolean)** — Keep Archives
- `color` **(integer)** — Color Index
- `reply_to_mode` **(selection)** — Reply-To Mode
  > Thread: replies go to target document. Email: replies are routed to a given email.
  > Opções: `update` (Recipient Followers), `new` (Specified Email Address)
- `reply_to` **(char)** — Reply To
  > Preferred Reply-To Address
- `mailing_domain` **(char)** — Domain
- `use_exclusion_list` **(boolean)** — Use Exclusion List
  > Prevent sending messages to blacklisted contacts. Disable only when absolutely necessary.
- `ab_testing_enabled` **(boolean)** — Allow A/B Testing
  > If checked, recipients will be mailed only once for the whole campaign. This lets you send different mailings to randomly selected recipients and test the effectiveness of the mailings, without causing duplicate messages.
- `ab_testing_pc` **(integer)** — A/B Testing percentage
  > Percentage of the contacts that will be mailed. Recipients will be chosen randomly.
- `ab_testing_schedule_datetime` **(datetime)** — Send Final On
  > Date that will be used to know when to determine and send the winner mailing
- `ab_testing_winner_selection` **(selection)** — Winner Selection
  > Selection to determine the winner mailing that will be sent.
  > Opções: `manual` (Manual), `opened_ratio` (Highest Open Rate), `clicks_ratio` (Highest Click Rate), `replied_ratio` (Highest Reply Rate), `crm_lead_count` (Leads), `sale_quotation_count` (Quotations), `sale_invoiced_amount` (Revenues)
- `kpi_mail_required` **(boolean)** — KPI mail required
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `use_in_marketing_automation` **(boolean)** — Specific mailing used in marketing campaign
  > Marketing campaigns use mass mailings with some specific behavior; this field is used to indicate its statistics may be suspicious.

## Relacionamentos

- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `campaign_id` **(many2one)** — UTM Campaign → `utm.campaign`
- `medium_id` **(many2one)** — Medium → `utm.medium`
  > UTM Medium: delivery method (email, sms, ...)
- `user_id` **(many2one)** — Responsible → `res.users`
- `mail_server_id` **(many2one)** — Mail Server → `ir.mail_server`
  > Use a specific mail server in priority. Otherwise Odoo relies on the first outgoing mail server available (based on their sequencing) as it does for normal mails.
- `contact_list_ids` **(many2many)** — Mailing Lists → `mailing.list`
- `mailing_filter_id` **(many2one)** — Favorite Filter → `mailing.filter`
- `mailing_trace_ids` **(one2many)** — Emails Statistics → `mailing.trace`
- `marketing_activity_ids` **(one2many)** — Marketing Activities → `marketing.activity`

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
- `is_body_empty` **(boolean)** — Is Body Empty 🔒 readonly
- `mailing_type_description` **(char)** — Mailing Type Description 🔒 readonly
- `mailing_model_real` **(char)** — Recipients Real Model 🔒 readonly
- `mailing_model_name` **(char)** — Recipients Model Name 🔒 readonly
- `mailing_on_mailing_list` **(boolean)** — Based on Mailing Lists 🔒 readonly
- `mail_server_available` **(boolean)** — Mail Server Available 🔒 readonly
  > Technical field used to know if the user has activated the outgoing mail server option in the settings
- `mailing_filter_domain` **(char)** — Favorite filter domain 🔒 readonly
- `mailing_filter_count` **(integer)** — # Favorite Filters 🔒 readonly
- `ab_testing_completed` **(boolean)** — A/B Testing Campaign Finished 🔒 readonly
- `ab_testing_description` **(html)** — A/B Testing Description 🔒 readonly
- `ab_testing_is_winner_mailing` **(boolean)** — Is the Winner of its Campaign 🔒 readonly
- `ab_testing_mailings_count` **(integer)** — A/B Test Mailings # 🔒 readonly
- `is_ab_test_sent` **(boolean)** — Is Ab Test Sent 🔒 readonly
- `total` **(integer)** — Total 🔒 readonly
- `scheduled` **(integer)** — Scheduled 🔒 readonly
- `expected` **(integer)** — Expected 🔒 readonly
- `canceled` **(integer)** — Canceled 🔒 readonly
- `sent` **(integer)** — Sent 🔒 readonly
- `process` **(integer)** — Process 🔒 readonly
- `pending` **(integer)** — Pending 🔒 readonly
- `delivered` **(integer)** — Delivered 🔒 readonly
- `opened` **(integer)** — Opened 🔒 readonly
- `clicked` **(integer)** — Clicked 🔒 readonly
- `replied` **(integer)** — Replied 🔒 readonly
- `bounced` **(integer)** — Bounced 🔒 readonly
- `failed` **(integer)** — Failed 🔒 readonly
- `received_ratio` **(float)** — Received Ratio 🔒 readonly
- `opened_ratio` **(float)** — Opened Ratio 🔒 readonly
- `replied_ratio` **(float)** — Replied Ratio 🔒 readonly
- `bounced_ratio` **(float)** — Bounced Ratio 🔒 readonly
- `clicks_ratio` **(float)** — Number of Clicks 🔒 readonly
- `link_trackers_count` **(integer)** — Link Trackers Count 🔒 readonly
- `next_departure` **(datetime)** — Scheduled date 🔒 readonly
- `next_departure_is_past` **(boolean)** — Next Departure Is Past 🔒 readonly
- `warning_message` **(char)** — Warning Message 🔒 readonly
  > Warning message displayed in the mailing form view
- `use_leads` **(boolean)** — Use Leads 🔒 readonly
- `crm_lead_count` **(integer)** — Leads/Opportunities Count 🔒 readonly
- `sale_quotation_count` **(integer)** — Quotation Count 🔒 readonly
- `sale_invoiced_amount` **(integer)** — Invoiced Amount 🔒 readonly
