# Cleaning Model — `data_cleaning.model`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `res_model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`
- `cleaning_mode` **(selection)** — Cleaning Mode ⚠️ obrigatório
  > Opções: `manual` (Manual), `automatic` (Automatic)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `notify_frequency` **(integer)** — Notify
- `notify_frequency_period` **(selection)** — Notify Frequency Period
  > Opções: `days` (Days), `weeks` (Weeks), `months` (Months)
- `last_notification` **(datetime)** — Last Notification 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `rule_ids` **(one2many)** — Rules → `data_cleaning.rule`
- `notify_user_ids` **(many2many)** — Notify Users → `res.users`
  > List of users to notify when there are new records to clean

## Campos Calculados (readonly)

- `records_to_clean_count` **(integer)** — Records To Clean 🔒 readonly
