# Models — `ir.model`

**Ordenação padrão:** `is_mail_thread DESC, name ASC`

---

## Campos Obrigatórios

- `name` **(char)** — Model Description ⚠️ obrigatório
- `model` **(char)** — Model ⚠️ obrigatório
- `order` **(char)** — Order ⚠️ obrigatório
  > SQL expression for ordering records in the model; e.g. "x_sequence asc, id desc"
- `field_id` **(one2many)** — Fields ⚠️ obrigatório → `ir.model.fields`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `info` **(text)** — Information
- `state` **(selection)** — Type 🔒 readonly
  > Opções: `manual` (Custom Object), `base` (Base Object)
- `transient` **(boolean)** — Transient Model
- `fold_name` **(char)** — Fold Field
  > In a Kanban view where columns are records of this model, the value of this (boolean) field determines which column should be folded by default.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `is_mail_thread` **(boolean)** — Has Mail Thread
- `is_mail_activity` **(boolean)** — Has Mail Activity
- `is_mail_blacklist` **(boolean)** — Has Mail Blacklist
- `website_form_access` **(boolean)** — Allowed to use in forms
  > Enable the form builder feature for this model.
- `website_form_label` **(char)** — Label for form action
  > Form action label. Ex: crm.lead could be 'Send an e-mail' and project.issue could be 'Create an Issue'.
- `website_form_key` **(char)** — Website Form Key
  > Used in FormBuilder Registry

## Relacionamentos

- `inherited_model_ids` **(many2many)** — Inherited models 🔒 readonly → `ir.model`
  > The list of models that extends the current model.
- `access_ids` **(one2many)** — Access → `ir.model.access`
- `rule_ids` **(one2many)** — Record Rules → `ir.rule`
- `view_ids` **(one2many)** — Views 🔒 readonly → `ir.ui.view`
- `ref_merge_ir_act_server_id` **(many2one)** — Merge Server Action 🔒 readonly → `ir.actions.server`
  > Contextual menu action that redirects to the deduplicate view of data_merge.
- `website_form_default_field_id` **(many2one)** — Field for custom form data → `ir.model.fields`
  > Specify the field which will contain meta and custom form fields datas.

## Campos Calculados (readonly)

- `abstract` **(boolean)** — Abstract Model 🔒 readonly
  > Whether this model is abstract
- `modules` **(char)** — In Apps 🔒 readonly
  > List of modules in which the object is defined or inherited
- `count` **(integer)** — Count (Incl. Archived) 🔒 readonly
  > Total number of records in this model
- `hide_merge_action` **(boolean)** — Hide merge action button 🔒 readonly
  > If the model already has a custom merge method, the class attribute `_merge_disabled` is set to true on              that model and the generic data merge action should not be available on that model.
- `is_merge_enabled` **(boolean)** — Can Be Merged 🔒 readonly
  > If True, the generic data merge tool is available in the contextual menu of this model.
- `is_mail_thread_sms` **(boolean)** — Mail Thread SMS 🔒 readonly
  > Whether this model supports messages and notifications through SMS
- `is_mailing_enabled` **(boolean)** — Mailing Enabled 🔒 readonly
  > Whether this model supports marketing mailing capabilities (notably email and SMS).
