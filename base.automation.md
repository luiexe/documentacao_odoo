# Automation Rule — `base.automation`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Automation Rule Name ⚠️ obrigatório
- `model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`
- `trigger` **(selection)** — Trigger ⚠️ obrigatório
  > Opções: `on_stage_set` (Stage is set to), `on_user_set` (User is set), `on_tag_set` (Tag is added), `on_state_set` (State is set to), `on_priority_set` (Priority is set to), `on_archive` (On archived), `on_unarchive` (On unarchived), `on_create` (On create), `on_create_or_write` (On create and edit), `on_write` (On update), `on_unlink` (On deletion), `on_change` (On UI change), `on_time` (Based on date field), `on_time_created` (After creation), `on_time_updated` (After last update), `on_message_received` (On incoming message), `on_message_sent` (On outgoing message), `on_webhook` (On webhook)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(html)** — Description
- `webhook_uuid` **(char)** — Webhook UUID 🔒 readonly
- `record_getter` **(char)** — Record Getter
  > This code will be run to find on which record the automation rule should be run.
- `log_webhook_calls` **(boolean)** — Log Calls
- `active` **(boolean)** — Active
  > When unchecked, the rule is hidden and will not be executed.
- `trg_field_ref` **(many2one_reference)** — Trigger Reference
  > Some triggers need a reference to another field. This field is used to store it.
- `trg_date_range` **(integer)** — Delay
- `trg_date_range_mode` **(selection)** — Delay mode
  > Opções: `after` (After), `before` (Before)
- `trg_date_range_type` **(selection)** — Delay unit
  > Opções: `minutes` (Minutes), `hour` (Hours), `day` (Days), `month` (Months)
- `filter_pre_domain` **(char)** — Before Update Domain
  > If present, this condition must be satisfied before the update of the record. Not checked on record creation.
- `previous_domain` **(char)** — Previous Domain
- `filter_domain` **(char)** — Apply on
  > If present, this condition must be satisfied before executing the automation rule.
- `last_run` **(datetime)** — Last Run 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `action_server_ids` **(one2many)** — Actions → `ir.actions.server`
- `trg_selection_field_id` **(many2one)** — Trigger Field → `ir.model.fields.selection`
  > Some triggers need a reference to a selection field. This field is used to store it.
- `trg_date_id` **(many2one)** — Trigger Date → `ir.model.fields`
  > When should the condition be triggered.                 If present, will be checked by the scheduler. If empty, will be checked at creation and update.
- `trg_date_calendar_id` **(many2one)** — Use Calendar → `resource.calendar`
  > When calculating a day-based timed condition, it is possible to use a calendar to compute the date based on working days.
- `on_change_field_ids` **(many2many)** — On Change Fields Trigger → `ir.model.fields`
  > Fields that trigger the onchange.
- `trigger_field_ids` **(many2many)** — Trigger Fields → `ir.model.fields`
  > The automation rule will be triggered if and only if one of these fields is updated.If empty, all fields are watched.
- `ai_autosort_folder_id` **(many2one)** — Sorted Folder → `documents.document`
- `trg_date_resource_field_id` **(many2one)** — Use employee work schedule → `ir.model.fields`
  > Use the user's working schedule.

## Campos Calculados (readonly)

- `model_name` **(char)** — Model Name 🔒 readonly
- `model_is_mail_thread` **(boolean)** — Has Mail Thread 🔒 readonly
- `url` **(char)** — Url 🔒 readonly
  > Use this URL in the third-party app to call this webhook.
- `trg_field_ref_model_name` **(char)** — Trigger Field Model 🔒 readonly
