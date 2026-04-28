# Deduplication Rule — `data_merge.rule`

**Ordenação padrão:** `sequence, field_id`

---

## Campos Obrigatórios

- `model_id` **(many2one)** — Deduplication Model ⚠️ obrigatório → `data_merge.model`
- `field_id` **(many2one)** — Unique ID Field ⚠️ obrigatório → `ir.model.fields`
- `match_mode` **(selection)** — Merge If ⚠️ obrigatório
  > Opções: `exact` (Exact Match), `accent` (Case/Accent Insensitive Match)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `res_model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
