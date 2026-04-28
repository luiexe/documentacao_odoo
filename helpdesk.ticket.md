# Helpdesk Ticket — `helpdesk.ticket`

**Ordenação padrão:** `priority desc, id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Subject ⚠️ obrigatório
- `kanban_state` **(selection)** — Kanban State ⚠️ obrigatório
  > Opções: `normal` (In progress), `done` (Ready), `blocked` (Blocked)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `rating_last_value` **(float)** — Rating Last Value 🔒 readonly
- `email_cc` **(char)** — Email cc
- `access_token` **(char)** — Security Token
- `description` **(html)** — Description
- `active` **(boolean)** — Active
- `color` **(integer)** — Color Index
- `properties` **(properties)** — Properties
- `partner_name` **(char)** — Customer Name
- `partner_email` **(char)** — Customer Email
- `partner_phone` **(char)** — Customer Phone
- `closed_by_partner` **(boolean)** — Closed by Partner 🔒 readonly
- `priority` **(selection)** — Priority
  > Opções: `0` (Low priority), `1` (Medium priority), `2` (High priority), `3` (Urgent)
- `date_last_stage_update` **(datetime)** — Last Stage Update 🔒 readonly
- `ticket_ref` **(char)** — Ticket IDs Sequence 🔒 readonly
- `assign_date` **(datetime)** — First assignment date
- `assign_hours` **(float)** — Time to first assignment (hours) 🔒 readonly
- `close_date` **(datetime)** — Close date
- `close_hours` **(float)** — Time to close (hours) 🔒 readonly
- `sla_reached_late` **(boolean)** — Has SLA reached late 🔒 readonly
- `sla_reached` **(boolean)** — Has SLA reached 🔒 readonly
- `sla_deadline` **(datetime)** — SLA Deadline 🔒 readonly
- `sla_deadline_hours` **(float)** — Working Hours until SLA Deadline 🔒 readonly
- `first_response_hours` **(float)** — Hours to First Response
- `avg_response_hours` **(float)** — Average Hours to Respond
- `oldest_unanswered_customer_message_date` **(datetime)** — Oldest Unanswered Customer Message Date
- `answered_customer_message_count` **(integer)** — # Exchanges
- `total_response_hours` **(float)** — Total Exchange Time in Hours
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `partner_company_name` **(char)** — Company Name

## Relacionamentos

- `campaign_id` **(many2one)** — Campaign → `utm.campaign`
  > This is a name that helps you keep track of your different campaign efforts, e.g. Fall_Drive, Christmas_Special
- `source_id` **(many2one)** — Source → `utm.source`
  > This is the source of the link, e.g. Search Engine, another domain, or name of email list
- `medium_id` **(many2one)** — Medium → `utm.medium`
  > This is the method of delivery, e.g. Postcard, Email, or Banner Ad
- `team_id` **(many2one)** — Helpdesk Team → `helpdesk.team`
- `tag_ids` **(many2many)** — Tags → `helpdesk.tag`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `domain_user_ids` **(many2many)** — Domain User 🔒 readonly → `res.users`
- `user_id` **(many2one)** — Assigned to → `res.users`
- `partner_id` **(many2one)** — Customer → `res.partner`
- `partner_ticket_ids` **(many2many)** — Partner Tickets 🔒 readonly → `helpdesk.ticket`
- `commercial_partner_id` **(many2one)** — Commercial Entity 🔒 readonly → `res.partner`
- `stage_id` **(many2one)** — Stage → `helpdesk.stage`
- `sla_ids` **(many2many)** — SLAs → `helpdesk.sla`
- `sla_status_ids` **(one2many)** — SLA Status → `helpdesk.sla.status`
- `sale_order_id` **(many2one)** — Ref. Sales Order → `sale.order`

## Campos Calculados (readonly)

- `duration_tracking` **(json)** — Status time 🔒 readonly
  > JSON that maps ids from a many2one field to seconds spent
- `rotting_days` **(integer)** — Days Rotting 🔒 readonly
  > Day count since this resource was last updated
- `is_rotting` **(boolean)** — Rotting 🔒 readonly
- `rating_last_feedback` **(text)** — Rating Last Feedback 🔒 readonly
- `rating_last_image` **(binary)** — Rating Last Image 🔒 readonly
- `rating_count` **(integer)** — Rating count 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `rating_avg_text` **(selection)** — Rating Avg Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `rating_percentage_satisfaction` **(float)** — Rating Satisfaction 🔒 readonly
- `rating_last_text` **(selection)** — Rating Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `use_sla` **(boolean)** — SLA Policies 🔒 readonly
- `team_privacy_visibility` **(selection)** — Visibility 🔒 readonly
  > People to whom this helpdesk team and its tickets will be visible.  - Invited internal users: internal users can access the team and the tickets they are following. This access can be modified on each ticket individually by adding or removing the user as follower. A user with the helpdesk > administrator access right level can still access this team and its tickets, even if they are not explicitely part of the followers.  - All internal users: all internal users can access the team and all of its tickets without distinction.  - Invited portal users and all internal users: all internal users can access the team and all of its tickets without distinction. Portal users can only access the tickets they are following. This access can be modified on each ticket individually by adding or removing the portal user as follower.
  > Opções: `invited_internal` (Invited internal users (private)), `internal` (All internal users (company)), `portal` (Invited portal users and all internal users (public))
- `kanban_state_label` **(char)** — Kanban State Label 🔒 readonly
- `legend_blocked` **(char)** — Kanban Blocked Explanation 🔒 readonly
- `legend_done` **(char)** — Kanban Valid Explanation 🔒 readonly
- `legend_normal` **(char)** — Kanban Ongoing Explanation 🔒 readonly
- `partner_ticket_count` **(integer)** — Number of other tickets from the same partner 🔒 readonly
- `partner_open_ticket_count` **(integer)** — Number of other open tickets from the same partner 🔒 readonly
- `stage_id_color` **(integer)** — Stage Color 🔒 readonly
- `fold` **(boolean)** — Folded 🔒 readonly
  > Tickets in a folded stage are considered as closed.
- `open_hours` **(integer)** — Open Time (hours) 🔒 readonly
- `sla_fail` **(boolean)** — Failed SLA Policy 🔒 readonly
- `sla_success` **(boolean)** — Success SLA Policy 🔒 readonly
- `use_credit_notes` **(boolean)** — Refunds 🔒 readonly
- `use_coupons` **(boolean)** — Use Coupons 🔒 readonly
- `use_giftcards` **(boolean)** — Use Gift Cards 🔒 readonly
- `use_product_returns` **(boolean)** — Returns 🔒 readonly
- `use_product_replacements` **(boolean)** — Replacements 🔒 readonly
- `use_product_repairs` **(boolean)** — Repairs 🔒 readonly
- `use_rating` **(boolean)** — Customer Ratings 🔒 readonly
- `is_partner_email_update` **(boolean)** — Is Partner Email Update 🔒 readonly
- `is_partner_phone_update` **(boolean)** — Is Partner Phone Update 🔒 readonly
- `display_extra_info` **(boolean)** — Display Extra Info 🔒 readonly
- `sale_order_state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Quotation), `sent` (Quotation Sent), `sale` (Sales Order), `cancel` (Cancelled)
