# Studio Export Models — `studio.export.model`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `model_name` **(char)** — Model Name 🔒 readonly
- `domain` **(text)** — Domain
- `is_demo_data` **(boolean)** — Demo
  > If set, the exported records will be considered as demo data during the import.
- `updatable` **(boolean)** — Updatable
  > Defines if the records would be updated during a module update.
- `include_attachment` **(boolean)** — Attachments
  > If set, attachments related to the exported records will be included.         This does not include the attachments uploaded in binary fields such as pictures, files, etc.         Include the corresponding fields in the export to get them.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `excluded_fields` **(many2many)** — Fields to exclude → `ir.model.fields`

## Campos Calculados (readonly)

- `records_count` **(char)** — Records 🔒 readonly
