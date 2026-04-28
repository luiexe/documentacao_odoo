# Sales Team — `crm.team`

**Ordenação padrão:** `sequence ASC, create_date DESC, id DESC`

---

## Campos Obrigatórios

- `name` **(char)** — Sales Team ⚠️ obrigatório
- `alias_id` **(many2one)** — Alias ⚠️ obrigatório → `mail.alias`
  > The email address associated with this channel. New emails received will automatically create new leads assigned to the channel.
- `alias_defaults` **(text)** — Default Values ⚠️ obrigatório 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `alias_model_id` **(many2one)** — Aliased Model ⚠️ obrigatório → `ir.model`
  > The model (Odoo Document Kind) to which this alias corresponds. Any incoming email that does not reply to an existing record will cause the creation of a new record of this model (e.g. a Project Task)
- `alias_contact` **(selection)** — Alias Contact Security ⚠️ obrigatório
  > Policy to post a message on the document using the mailgateway. - everyone: everyone can post - partners: only authenticated partners - followers: only followers of the related document or members of following channels 
  > Opções: `everyone` (Everyone), `partners` (Authenticated Partners), `followers` (Followers only), `employees` (Authenticated Employees)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
  > If the active field is set to false, it will allow you to hide the Sales Team without removing it.
- `color` **(integer)** — Color Index
  > The color of the channel
- `is_favorite` **(boolean)** — Show on dashboard
  > Favorite teams to display them in the dashboard and access them easily.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>
- `use_leads` **(boolean)** — Leads
  > Check this box to filter and qualify incoming requests as leads before converting them into opportunities and assigning them to a salesperson.
- `use_opportunities` **(boolean)** — Pipeline
  > Check this box to manage a presales process with opportunities.
- `assignment_optout` **(boolean)** — Skip auto assignment
- `assignment_domain` **(char)** — Assignment Domain
  > Additional filter domain when fetching unassigned leads to allocate to the team.
- `lead_properties_definition` **(properties_definition)** — Lead Properties
- `invoiced_target` **(float)** — Invoicing Target
  > Revenue Target for the current month (untaxed total of paid invoices).
- `alias_force_thread_id` **(integer)** — Record Thread ID
  > Optional ID of a thread (record) to which all incoming messages will be attached, even if they did not reply to it. If set, this will disable the creation of new records completely.
- `alias_parent_thread_id` **(integer)** — Parent Record Thread ID
  > ID of the parent record holding the alias (example: project holding the task creation alias)
- `alias_incoming_local` **(boolean)** — Local-part based incoming detection
- `alias_bounced_content` **(html)** — Custom Bounced Message
  > If set, this content will automatically be sent out to unauthorized users instead of the default message.

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `user_id` **(many2one)** — Team Leader → `res.users`
- `member_ids` **(many2many)** — Salespersons → `res.users`
  > Users assigned to this team.
- `member_company_ids` **(many2many)** — Member Company 🔒 readonly → `res.company`
  > UX: Limit to team company or all if no company
- `crm_team_member_ids` **(one2many)** — Sales Team Members → `crm.team.member`
  > Add members to automatically assign their documents to this sales team.
- `crm_team_member_all_ids` **(one2many)** — Sales Team Members (incl. inactive) → `crm.team.member`
- `favorite_user_ids` **(many2many)** — Favorite Members → `res.users`
- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `origin_survey_ids` **(one2many)** — Survey opportunities related to the sales team → `survey.survey`
- `commission_plan_ids` **(many2many)** — Commission Plan → `sale.commission.plan`
  > Default commission plan for team members.
- `website_ids` **(one2many)** — Websites → `website`
- `alias_parent_model_id` **(many2one)** — Parent Model → `ir.model`
  > Parent model holding the alias. The model holding the alias reference is not necessarily the model given by alias_model_id (example: project (parent_model) and task (model))

## Campos Calculados (readonly)

- `is_membership_multi` **(boolean)** — Multiple Memberships Allowed 🔒 readonly
  > If True, users may belong to several sales teams. Otherwise membership is limited to a single sales team.
- `member_warning` **(text)** — Membership Issue Warning 🔒 readonly
- `dashboard_button_name` **(char)** — Dashboard Button 🔒 readonly
- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_email` **(char)** — Email Alias 🔒 readonly
- `assignment_enabled` **(boolean)** — Lead Assign 🔒 readonly
- `assignment_auto_enabled` **(boolean)** — Auto Assignment 🔒 readonly
- `assignment_max` **(integer)** — Lead Average Capacity 🔒 readonly
  > Monthly average leads capacity for all salesmen belonging to the team
- `lead_unassigned_count` **(integer)** — # Unassigned Leads 🔒 readonly
- `lead_all_assigned_month_count` **(integer)** — # Leads/Opps assigned this month 🔒 readonly
  > Number of leads and opportunities assigned this last month.
- `lead_all_assigned_month_exceeded` **(boolean)** — Exceed monthly lead assignement 🔒 readonly
  > True if the monthly lead assignment count is greater than the maximum assignment limit, false otherwise.
- `invoiced` **(float)** — Invoiced This Month 🔒 readonly
  > Invoice revenue for the current month. This is the amount the sales channel has invoiced this month. It is used to compute the progression ratio of the current and target revenue on the kanban view.
- `sale_order_count` **(integer)** — # Sale Orders 🔒 readonly
- `abandoned_carts_amount` **(integer)** — Amount of Abandoned Carts 🔒 readonly
- `abandoned_carts_count` **(integer)** — Number of Abandoned Carts 🔒 readonly
- `alias_full_name` **(char)** — Alias Email 🔒 readonly
- `alias_status` **(selection)** — Alias Status 🔒 readonly
  > Alias status assessed on the last message received.
  > Opções: `not_tested` (Not Tested), `valid` (Valid), `invalid` (Invalid)
