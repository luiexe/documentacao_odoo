# Email Aliases — `mail.alias`

**Ordenação padrão:** `alias_model_id, alias_name`

---

## Campos Obrigatórios

- `alias_model_id` **(many2one)** — Aliased Model ⚠️ obrigatório → `ir.model`
  > The model (Odoo Document Kind) to which this alias corresponds. Any incoming email that does not reply to an existing record will cause the creation of a new record of this model (e.g. a Project Task)
- `alias_defaults` **(text)** — Default Values ⚠️ obrigatório
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `alias_contact` **(selection)** — Alias Contact Security ⚠️ obrigatório
  > Policy to post a message on the document using the mailgateway. - everyone: everyone can post - partners: only authenticated partners - followers: only followers of the related document or members of following channels 
  > Opções: `everyone` (Everyone), `partners` (Authenticated Partners), `followers` (Followers only), `employees` (Authenticated Employees)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>
- `alias_full_name` **(char)** — Alias Email 🔒 readonly
- `alias_force_thread_id` **(integer)** — Record Thread ID
  > Optional ID of a thread (record) to which all incoming messages will be attached, even if they did not reply to it. If set, this will disable the creation of new records completely.
- `alias_parent_thread_id` **(integer)** — Parent Record Thread ID
  > ID of the parent record holding the alias (example: project holding the task creation alias)
- `alias_incoming_local` **(boolean)** — Local-part based incoming detection
- `alias_bounced_content` **(html)** — Custom Bounced Message
  > If set, this content will automatically be sent out to unauthorized users instead of the default message.
- `alias_status` **(selection)** — Alias Status 🔒 readonly
  > Alias status assessed on the last message received.
  > Opções: `not_tested` (Not Tested), `valid` (Valid), `invalid` (Invalid)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `alias_parent_model_id` **(many2one)** — Parent Model → `ir.model`
  > Parent model holding the alias. The model holding the alias reference is not necessarily the model given by alias_model_id (example: project (parent_model) and task (model))

## Campos Calculados (readonly)

- `alias_domain` **(char)** — Alias domain name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
