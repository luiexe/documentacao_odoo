# Deduplication Record — `data_merge.record`

**Ordenação padrão:** `res_id desc`

---

## Campos Obrigatórios

- `group_id` **(many2one)** — Record Group ⚠️ obrigatório → `data_merge.group`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active 🔒 readonly
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `is_master` **(boolean)** — Is Master
- `is_discarded` **(boolean)** — Is Discarded
- `res_id` **(integer)** — Record ID
- `differences` **(char)** — Differences 🔒 readonly
  > Differences with the master record
- `used_in` **(char)** — Used In 🔒 readonly
  > List of other models referencing this record
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `model_id` **(many2one)** — Deduplication Model 🔒 readonly → `data_merge.model`
- `res_model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `is_deleted` **(boolean)** — Is Deleted 🔒 readonly
- `name` **(char)** — Name 🔒 readonly
- `record_create_date` **(datetime)** — Created On 🔒 readonly
- `record_create_uid` **(char)** — Created By 🔒 readonly
- `record_write_date` **(datetime)** — Updated On 🔒 readonly
- `record_write_uid` **(char)** — Updated By 🔒 readonly
- `field_values` **(char)** — Field Values 🔒 readonly
