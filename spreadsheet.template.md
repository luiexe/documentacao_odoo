# Spreadsheet Template — `spreadsheet.template`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `spreadsheet_binary_data` **(binary)** — Spreadsheet file
- `spreadsheet_data` **(text)** — Spreadsheet Data
- `thumbnail` **(binary)** — Thumbnail
- `spreadsheet_snapshot` **(binary)** — Spreadsheet Snapshot
- `display_thumbnail` **(binary)** — Display Thumbnail
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `spreadsheet_revision_ids` **(one2many)** — Spreadsheet Revision → `spreadsheet.revision`

## Campos Calculados (readonly)

- `spreadsheet_file_name` **(char)** — Spreadsheet File Name 🔒 readonly
- `current_revision_uuid` **(char)** — Current Revision Uuid 🔒 readonly
- `file_name` **(char)** — File Name 🔒 readonly
