# Recycling Model — `data_recycle.model`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `res_model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`
- `recycle_mode` **(selection)** — Recycle Mode ⚠️ obrigatório
  > Opções: `manual` (Manual), `automatic` (Automatic)
- `recycle_action` **(selection)** — Recycle Action ⚠️ obrigatório
  > Opções: `archive` (Archive), `unlink` (Delete)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `domain` **(char)** — Filter
- `time_field_delta` **(integer)** — Delta
- `time_field_delta_unit` **(selection)** — Delta Unit
  > Opções: `days` (Days), `weeks` (Weeks), `months` (Months), `years` (Years)
- `include_archived` **(boolean)** — Include Archived
- `notify_frequency` **(integer)** — Notify
- `notify_frequency_period` **(selection)** — Notify Frequency Period
  > Opções: `days` (Days), `weeks` (Weeks), `months` (Months)
- `last_notification` **(datetime)** — Last Notification 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `recycle_record_ids` **(one2many)** — Recycle Record → `data_recycle.record`
- `time_field_id` **(many2one)** — Time Field → `ir.model.fields`
- `notify_user_ids` **(many2many)** — Notify Users → `res.users`
  > List of users to notify when there are new records to recycle

## Campos Calculados (readonly)

- `records_to_recycle_count` **(integer)** — Records To Recycle 🔒 readonly
