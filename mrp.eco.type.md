# ECO Type — `mrp.eco.type`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `alias_id` **(many2one)** — Alias ⚠️ obrigatório → `mail.alias`
- `alias_defaults` **(text)** — Default Values ⚠️ obrigatório 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `name` **(char)** — Name ⚠️ obrigatório
- `alias_model_id` **(many2one)** — Aliased Model ⚠️ obrigatório → `ir.model`
  > The model (Odoo Document Kind) to which this alias corresponds. Any incoming email that does not reply to an existing record will cause the creation of a new record of this model (e.g. a Project Task)
- `alias_contact` **(selection)** — Alias Contact Security ⚠️ obrigatório
  > Policy to post a message on the document using the mailgateway. - everyone: everyone can post - partners: only authenticated partners - followers: only followers of the related document or members of following channels 
  > Opções: `everyone` (Everyone), `partners` (Authenticated Partners), `followers` (Followers only), `employees` (Authenticated Employees)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>
- `sequence` **(integer)** — Sequence
- `color` **(integer)** — Color
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
- `stage_ids` **(many2many)** — Stages → `mrp.eco.stage`
- `alias_parent_model_id` **(many2one)** — Parent Model → `ir.model`
  > Parent model holding the alias. The model holding the alias reference is not necessarily the model given by alias_model_id (example: project (parent_model) and task (model))

## Campos Calculados (readonly)

- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_email` **(char)** — Email Alias 🔒 readonly
- `nb_ecos` **(integer)** — ECOs 🔒 readonly
- `nb_approvals` **(integer)** — Waiting Approvals 🔒 readonly
- `nb_approvals_my` **(integer)** — Waiting my Approvals 🔒 readonly
- `nb_validation` **(integer)** — To Apply 🔒 readonly
- `alias_full_name` **(char)** — Alias Email 🔒 readonly
- `alias_status` **(selection)** — Alias Status 🔒 readonly
  > Alias status assessed on the last message received.
  > Opções: `not_tested` (Not Tested), `valid` (Valid), `invalid` (Invalid)
