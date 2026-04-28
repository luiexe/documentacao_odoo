# Lead — `crm.lead`

**Ordenação padrão:** `priority desc, id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Opportunity ⚠️ obrigatório
- `type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `lead` (Lead), `opportunity` (Opportunity)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `phone_sanitized` **(char)** — Sanitized Number 🔒 readonly
  > Field used to store sanitized phone number. Helps speeding up searches and comparisons.
- `phone_mobile_search` **(char)** — Phone Number
- `email_normalized` **(char)** — Normalized Email 🔒 readonly
  > This field is used to search on email address as the primary email field can contain more than strictly an email address.
- `message_bounce` **(integer)** — Bounce
  > Counter of the number of bounced emails for this contact
- `email_cc` **(char)** — Email cc
- `lead_properties` **(properties)** — Properties
- `referred` **(char)** — Referred By
- `description` **(html)** — Notes
- `active` **(boolean)** — Active
- `priority` **(selection)** — Priority
  > Opções: `0` (Low), `1` (Medium), `2` (High), `3` (Very High)
- `color` **(integer)** — Color Index
- `expected_revenue` **(monetary)** — Expected Revenue
- `prorated_revenue` **(monetary)** — Prorated Revenue 🔒 readonly
- `recurring_revenue` **(monetary)** — Recurring Revenues
- `recurring_revenue_monthly` **(monetary)** — Expected MRR 🔒 readonly
- `recurring_revenue_monthly_prorated` **(monetary)** — Prorated MRR 🔒 readonly
- `recurring_revenue_prorated` **(monetary)** — Prorated Recurring Revenues 🔒 readonly
- `date_closed` **(datetime)** — Closed Date 🔒 readonly
- `date_automation_last` **(datetime)** — Last Action 🔒 readonly
- `date_open` **(datetime)** — Assignment Date 🔒 readonly
- `day_open` **(float)** — Days to Assign 🔒 readonly
- `day_close` **(float)** — Days to Close 🔒 readonly
- `date_last_stage_update` **(datetime)** — Last Stage Update 🔒 readonly
- `date_conversion` **(datetime)** — Conversion Date 🔒 readonly
- `date_deadline` **(date)** — Expected Closing
  > Estimate of the date on which the opportunity will be won.
- `contact_name` **(char)** — Contact Name
- `partner_name` **(char)** — Company Name
  > The name of the future partner company that will be created while converting the lead into opportunity
- `function` **(char)** — Job Position
- `email_from` **(char)** — Email
- `email_domain_criterion` **(char)** — Email Domain Criterion 🔒 readonly
- `phone` **(char)** — Phone
- `phone_state` **(selection)** — Phone Quality 🔒 readonly
  > Opções: `correct` (Correct), `incorrect` (Incorrect)
- `email_state` **(selection)** — Email Quality 🔒 readonly
  > Opções: `correct` (Correct), `incorrect` (Incorrect)
- `website` **(char)** — Website
  > Website of the contact
- `street` **(char)** — Street
- `street2` **(char)** — Street2
- `zip` **(char)** — Zip
- `city` **(char)** — City
- `probability` **(float)** — Probability
- `automated_probability` **(float)** — Automated Probability 🔒 readonly
- `won_status` **(selection)** — Won/Lost 🔒 readonly
  > Opções: `won` (Won), `lost` (Lost), `pending` (Pending)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `days_to_convert` **(float)** — Days To Convert 🔒 readonly
- `days_exceeding_closing` **(float)** — Exceeded Closing Days 🔒 readonly
- `reveal_id` **(char)** — Reveal ID
- `iap_enrich_done` **(boolean)** — Enrichment done
  > Whether IAP service for lead enrichment based on email has been performed on this lead.

## Relacionamentos

- `campaign_id` **(many2one)** — Campaign → `utm.campaign`
  > This is a name that helps you keep track of your different campaign efforts, e.g. Fall_Drive, Christmas_Special
- `source_id` **(many2one)** — Source → `utm.source`
  > This is the source of the link, e.g. Search Engine, another domain, or name of email list
- `medium_id` **(many2one)** — Medium → `utm.medium`
  > This is the method of delivery, e.g. Postcard, Email, or Banner Ad
- `user_id` **(many2one)** — Salesperson → `res.users`
- `user_company_ids` **(many2many)** — User Company 🔒 readonly → `res.company`
  > UX: Limit to lead company or all if no company
- `team_id` **(many2one)** — Sales Team → `crm.team`
- `company_id` **(many2one)** — Company → `res.company`
- `stage_id` **(many2one)** — Stage → `crm.stage`
- `tag_ids` **(many2many)** — Tags → `crm.tag`
  > Classify and analyze your lead/opportunity categories like: Training, Service
- `recurring_plan` **(many2one)** — Recurring Plan → `crm.recurring.plan`
- `company_currency` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `commercial_partner_id` **(many2one)** — Customer Company → `res.partner`
- `partner_id` **(many2one)** — Contact → `res.partner`
  > Linked partner (optional). Usually created when converting the lead. You can find a partner by its Name, TIN, Email or Internal Reference.
- `lang_id` **(many2one)** — Language → `res.lang`
- `state_id` **(many2one)** — State → `res.country.state`
- `country_id` **(many2one)** — Country → `res.country`
- `lost_reason_id` **(many2one)** — Lost Reason → `crm.lost.reason`
- `calendar_event_ids` **(one2many)** — Meetings → `calendar.event`
- `duplicate_lead_ids` **(many2many)** — Potential Duplicate Lead 🔒 readonly → `crm.lead`
- `origin_survey_id` **(many2one)** — Survey → `survey.survey`
- `visitor_ids` **(many2many)** — Web Visitors → `website.visitor`
- `lead_mining_request_id` **(many2one)** — Lead Mining Request → `crm.iap.lead.mining.request`
- `order_ids` **(one2many)** — Orders → `sale.order`

## Campos Calculados (readonly)

- `duration_tracking` **(json)** — Status time 🔒 readonly
  > JSON that maps ids from a many2one field to seconds spent
- `rotting_days` **(integer)** — Days Rotting 🔒 readonly
  > Day count since this resource was last updated
- `is_rotting` **(boolean)** — Rotting 🔒 readonly
- `phone_sanitized_blacklisted` **(boolean)** — Phone Blacklisted 🔒 readonly
  > If the sanitized phone number is on the blacklist, the contact won't receive mass mailing sms anymore, from any list
- `phone_blacklisted` **(boolean)** — Blacklisted Phone is Phone 🔒 readonly
  > Indicates if a blacklisted sanitized phone number is a phone number. Helps distinguish which number is blacklisted             when there is both a mobile and phone field in a model.
- `is_blacklisted` **(boolean)** — Blacklist 🔒 readonly
  > If the email address is on the blacklist, the contact won't receive mass mailing anymore, from any list
- `stage_id_color` **(integer)** — Stage Color 🔒 readonly
- `partner_is_blacklisted` **(boolean)** — Partner is blacklisted 🔒 readonly
  > If the email address is on the blacklist, the contact won't receive mass mailing anymore, from any list
- `lang_code` **(char)** — Locale Code 🔒 readonly
  > This field is used to set/get locales for user
- `lang_active_count` **(integer)** — Lang Active Count 🔒 readonly
- `is_automated_probability` **(boolean)** — Is automated probability? 🔒 readonly
- `duplicate_lead_count` **(integer)** — Potential Duplicate Lead Count 🔒 readonly
- `meeting_display_date` **(date)** — Meeting Display Date 🔒 readonly
- `meeting_display_label` **(char)** — Meeting Display Label 🔒 readonly
- `partner_email_update` **(boolean)** — Partner Email will Update 🔒 readonly
- `partner_phone_update` **(boolean)** — Partner Phone will Update 🔒 readonly
- `is_partner_visible` **(boolean)** — Is Partner Visible 🔒 readonly
- `visitor_page_count` **(integer)** — # Page Views 🔒 readonly
- `show_enrich_button` **(boolean)** — Allow manual enrich 🔒 readonly
- `sale_amount_total` **(monetary)** — Sum of Orders 🔒 readonly
  > Untaxed Total of Confirmed Orders
- `quotation_count` **(integer)** — Number of Quotations 🔒 readonly
- `sale_order_count` **(integer)** — Number of Sale Orders 🔒 readonly
