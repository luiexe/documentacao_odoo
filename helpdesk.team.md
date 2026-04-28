# Helpdesk Team — `helpdesk.team`

**Ordenação padrão:** `sequence,name`

---

## Campos Obrigatórios

- `alias_id` **(many2one)** — Alias ⚠️ obrigatório → `mail.alias`
- `alias_defaults` **(text)** — Default Values ⚠️ obrigatório 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `name` **(char)** — Helpdesk Team ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `assign_method` **(selection)** — Assignment Method ⚠️ obrigatório
  > New tickets will automatically be assigned to the team members that are available, according to their working hours and their time off.
  > Opções: `randomly` (Each user is assigned an equal number of tickets), `balanced` (Each user has an equal number of open tickets), `tags` (Dispatch tickets based on tags)
- `member_ids` **(many2many)** — Team Members ⚠️ obrigatório → `res.users`
- `privacy_visibility` **(selection)** — Visibility ⚠️ obrigatório
  > People to whom this helpdesk team and its tickets will be visible.  - Invited internal users: internal users can access the team and the tickets they are following. This access can be modified on each ticket individually by adding or removing the user as follower. A user with the helpdesk > administrator access right level can still access this team and its tickets, even if they are not explicitely part of the followers.  - All internal users: all internal users can access the team and all of its tickets without distinction.  - Invited portal users and all internal users: all internal users can access the team and all of its tickets without distinction. Portal users can only access the tickets they are following. This access can be modified on each ticket individually by adding or removing the portal user as follower.
  > Opções: `invited_internal` (Invited internal users (private)), `internal` (All internal users (company)), `portal` (Invited portal users and all internal users (public))
- `alias_model_id` **(many2one)** — Aliased Model ⚠️ obrigatório → `ir.model`
  > The model (Odoo Document Kind) to which this alias corresponds. Any incoming email that does not reply to an existing record will cause the creation of a new record of this model (e.g. a Project Task)
- `alias_contact` **(selection)** — Alias Contact Security ⚠️ obrigatório
  > Policy to post a message on the document using the mailgateway. - everyone: everyone can post - partners: only authenticated partners - followers: only followers of the related document or members of following channels 
  > Opções: `everyone` (Everyone), `partners` (Authenticated Partners), `followers` (Followers only), `employees` (Authenticated Employees)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>
- `description` **(html)** — About Team
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `color` **(integer)** — Color Index
- `ticket_properties` **(properties_definition)** — Ticket Properties
- `auto_assignment` **(boolean)** — Automatic Assignment
- `use_alias` **(boolean)** — Use Alias
- `allow_portal_ticket_closing` **(boolean)** — Closure by Customers
- `use_website_helpdesk_form` **(boolean)** — Website Form
- `use_website_helpdesk_livechat` **(boolean)** — Live Chat
- `use_website_helpdesk_forum` **(boolean)** — Community Forum
- `use_website_helpdesk_slides` **(boolean)** — eLearning
- `use_website_helpdesk_knowledge` **(boolean)** — Knowledge
- `use_helpdesk_timesheet` **(boolean)** — Timesheets
- `use_helpdesk_sale_timesheet` **(boolean)** — Time Billing
- `use_credit_notes` **(boolean)** — Refunds
- `use_coupons` **(boolean)** — Coupons
- `use_giftcards` **(boolean)** — Gift Cards
- `use_fsm` **(boolean)** — Field Service
- `use_product_returns` **(boolean)** — Returns
- `use_product_replacements` **(boolean)** — Replacements
- `use_product_repairs` **(boolean)** — Repairs
- `use_twitter` **(boolean)** — X
- `use_rating` **(boolean)** — Customer Ratings
- `use_sla` **(boolean)** — SLA Policies
- `auto_close_ticket` **(boolean)** — Automatic Closing
- `auto_close_day` **(integer)** — Inactive Period(days)
  > Period of inactivity after which tickets will be automatically closed.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `alias_force_thread_id` **(integer)** — Record Thread ID
  > Optional ID of a thread (record) to which all incoming messages will be attached, even if they did not reply to it. If set, this will disable the creation of new records completely.
- `alias_parent_thread_id` **(integer)** — Parent Record Thread ID
  > ID of the parent record holding the alias (example: project holding the task creation alias)
- `alias_incoming_local` **(boolean)** — Local-part based incoming detection
- `alias_bounced_content` **(html)** — Custom Bounced Message
  > If set, this content will automatically be sent out to unauthorized users instead of the default message.

## Relacionamentos

- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `stage_ids` **(many2many)** — Stages → `helpdesk.stage`
  > Stages the team will use. This team's tickets will only be able to be in these stages.
- `ticket_ids` **(one2many)** — Tickets → `helpdesk.ticket`
- `resource_calendar_id` **(many2one)** — Working Hours → `resource.calendar`
  > Working hours used to determine the deadline of SLA Policies.
- `from_stage_ids` **(many2many)** — In Stages → `helpdesk.stage`
- `to_stage_id` **(many2one)** — Move to Stage → `helpdesk.stage`
- `website_id` **(many2one)** — Website → `website`
- `website_menu_id` **(many2one)** — Website Menu → `website.menu`
- `website_form_view_id` **(many2one)** — Website Form View → `ir.ui.view`
- `website_article_id` **(many2one)** — Article → `knowledge.article`
  > Article on which customers will land by default. The search is limited to this article, unless it is the workspace root, in which case all child articles are included.
- `website_latest_articles` **(many2many)** — Latest Articles 🔒 readonly → `knowledge.article`
- `website_slide_channel_ids` **(many2many)** — Courses → `slide.channel`
  > Customers will see only the content from chosen courses in the help center. If you want all courses to be accessible, just leave the field empty. Alternatively, you can make courses private to restrict this feature to internal users.
- `website_top_channels` **(many2many)** — Most Popular Courses 🔒 readonly → `slide.channel`
- `alias_parent_model_id` **(many2one)** — Parent Model → `ir.model`
  > Parent model holding the alias. The model holding the alias reference is not necessarily the model given by alias_model_id (example: project (parent_model) and task (model))

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `rating_percentage_satisfaction` **(integer)** — Rating Satisfaction 🔒 readonly
  > Percentage of happy ratings
- `rating_count` **(integer)** — # Ratings 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `rating_avg_percentage` **(float)** — Average Rating (%) 🔒 readonly
- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_email` **(char)** — Email Alias 🔒 readonly
- `privacy_visibility_warning` **(char)** — Privacy Visibility Warning 🔒 readonly
- `access_instruction_message` **(char)** — Access Instruction Message 🔒 readonly
- `has_external_mail_server` **(boolean)** — Has External Mail Server 🔒 readonly
- `show_knowledge_base` **(boolean)** — Show Knowledge Base 🔒 readonly
- `unassigned_tickets` **(integer)** — Unassigned Tickets 🔒 readonly
- `open_ticket_count` **(integer)** — # Open Tickets 🔒 readonly
- `sla_policy_count` **(integer)** — # SLA Policy 🔒 readonly
- `ticket_closed` **(integer)** — Ticket Closed 🔒 readonly
- `success_rate` **(float)** — Success Rate 🔒 readonly
- `urgent_ticket` **(integer)** — # Urgent Ticket 🔒 readonly
- `sla_failed` **(integer)** — Failed SLA Ticket 🔒 readonly
- `alias_email_from` **(char)** — Alias Email From 🔒 readonly
- `feature_form_url` **(char)** — URL to Submit Issue 🔒 readonly
- `show_knowledge_base_article` **(boolean)** — Show Knowledge Base Article 🔒 readonly
- `show_knowledge_base_slide_channel` **(boolean)** — Show Knowledge Base Slide Channel 🔒 readonly
- `alias_full_name` **(char)** — Alias Email 🔒 readonly
- `alias_status` **(selection)** — Alias Status 🔒 readonly
  > Alias status assessed on the last message received.
  > Opções: `not_tested` (Not Tested), `valid` (Valid), `invalid` (Invalid)
