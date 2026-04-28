# Deduplication Model — `data_merge.model`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `res_model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `domain` **(char)** — Domain
  > Records eligible for the deduplication process
- `removal_mode` **(selection)** — Duplicate Removal
  > Opções: `archive` (Archive), `delete` (Delete)
- `merge_mode` **(selection)** — Merge Mode
  > Opções: `manual` (Manual), `automatic` (Automatic)
- `mix_by_company` **(boolean)** — Cross-Company
  > When enabled, duplicates across different companies will be suggested
- `notify_frequency` **(integer)** — Notify
- `notify_frequency_period` **(selection)** — Notify Frequency Period
  > Opções: `days` (Days), `weeks` (Weeks), `months` (Months)
- `last_notification` **(datetime)** — Last Notification 🔒 readonly
- `merge_threshold` **(integer)** — Similarity Threshold
  > Records with a similarity percentage above this threshold will be automatically merged
- `create_threshold` **(integer)** — Suggestion Threshold
  > Duplicates with a similarity below this threshold will not be suggested
- `is_contextual_merge_action` **(boolean)** — Merge action attached
  > If True, this record is used for contextual menu action "Merge" on the target model.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `rule_ids` **(one2many)** — Deduplication Rules → `data_merge.rule`
  > Suggest to merge records matching at least one of these rules
- `notify_user_ids` **(many2many)** — Notify Users → `res.users`
  > List of users to notify when there are new records to merge

## Campos Calculados (readonly)

- `custom_merge_method` **(boolean)** — Custom Merge Method 🔒 readonly
- `records_to_merge_count` **(integer)** — Records To Merge Count 🔒 readonly
