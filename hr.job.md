# Job Position — `hr.job`

**Ordenação padrão:** `sequence, name asc`

---

## Campos Obrigatórios

- `name` **(char)** — Job Position ⚠️ obrigatório
- `alias_defaults` **(text)** — Default Values ⚠️ obrigatório 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `alias_model_id` **(many2one)** — Aliased Model ⚠️ obrigatório → `ir.model`
  > The model (Odoo Document Kind) to which this alias corresponds. Any incoming email that does not reply to an existing record will cause the creation of a new record of this model (e.g. a Project Task)
- `alias_contact` **(selection)** — Alias Contact Security ⚠️ obrigatório
  > Policy to post a message on the document using the mailgateway. - everyone: everyone can post - partners: only authenticated partners - followers: only followers of the related document or members of following channels 
  > Opções: `everyone` (Everyone), `partners` (Authenticated Partners), `followers` (Followers only), `employees` (Authenticated Employees)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
  > Set if the application is published on the website of the company.
- `is_published` **(boolean)** — Is Published
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `no_of_recruitment` **(integer)** — Target
  > Number of new employees you expect to recruit.
- `description` **(html)** — Job Description
- `requirements` **(text)** — Requirements
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>
- `color` **(integer)** — Color Index
- `is_favorite` **(boolean)** — Is Favorite
- `website_description` **(html)** — Website description
- `job_details` **(html)** — Process Details
  > Complementary information that will appear on the job submission page
- `published_date` **(date)** — Published Date 🔒 readonly
- `alias_force_thread_id` **(integer)** — Record Thread ID
  > Optional ID of a thread (record) to which all incoming messages will be attached, even if they did not reply to it. If set, this will disable the creation of new records completely.
- `alias_parent_thread_id` **(integer)** — Parent Record Thread ID
  > ID of the parent record holding the alias (example: project holding the task creation alias)
- `alias_incoming_local` **(boolean)** — Local-part based incoming detection
- `alias_bounced_content` **(html)** — Custom Bounced Message
  > If set, this content will automatically be sent out to unauthorized users instead of the default message.

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `employee_ids` **(one2many)** — Employees → `hr.employee`
- `user_id` **(many2one)** — Recruiter → `res.users`
  > The Recruiter will be the default value for all Applicants in this job             position. The Recruiter is automatically added to all meetings with the Applicant.
- `allowed_user_ids` **(many2many)** — Allowed User 🔒 readonly → `res.users`
- `department_id` **(many2one)** — Department → `hr.department`
- `company_id` **(many2one)** — Company → `res.company`
- `contract_type_id` **(many2one)** — Employment Type → `hr.contract.type`
- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `address_id` **(many2one)** — Job Location → `res.partner`
  > Select the location where the applicant will work. Addresses listed here are defined on the company's contact information.
- `manager_id` **(many2one)** — Department Manager 🔒 readonly → `hr.employee`
- `favorite_user_ids` **(many2many)** — Favorite User → `res.users`
- `job_skill_ids` **(one2many)** — Skills → `hr.job.skill`
- `current_job_skill_ids` **(one2many)** — Current Job Skill → `hr.job.skill`
- `skill_ids` **(many2many)** — Skill 🔒 readonly → `hr.skill`
- `alias_parent_model_id` **(many2one)** — Parent Model → `ir.model`
  > Parent model holding the alias. The model holding the alias reference is not necessarily the model given by alias_model_id (example: project (parent_model) and task (model))

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `expected_employees` **(integer)** — Total Forecasted Employees 🔒 readonly
  > Expected number of employees for this job position after new recruitment.
- `no_of_employee` **(integer)** — Current Number of Employees 🔒 readonly
  > Number of employees currently occupying this job position.
- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_email` **(char)** — Email Alias 🔒 readonly
- `employee_count` **(integer)** — Employee Count 🔒 readonly
- `full_url` **(char)** — job URL 🔒 readonly
- `alias_full_name` **(char)** — Alias Email 🔒 readonly
- `alias_status` **(selection)** — Alias Status 🔒 readonly
  > Alias status assessed on the last message received.
  > Opções: `not_tested` (Not Tested), `valid` (Valid), `invalid` (Invalid)
