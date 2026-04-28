# Deduplication Group — `data_merge.group`

**Ordenação padrão:** `similarity desc`

---

## Campos Obrigatórios

- `model_id` **(many2one)** — Deduplication Model ⚠️ obrigatório → `data_merge.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `similarity` **(float)** — Similarity % 🔒 readonly
  > Similarity coefficient based on the amount of text fields exactly in common.
- `divergent_fields` **(char)** — Divergent Fields 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `res_model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
- `record_ids` **(one2many)** — Record → `data_merge.record`
