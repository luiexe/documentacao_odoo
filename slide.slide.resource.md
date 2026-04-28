# Additional resource for a particular slide — `slide.slide.resource`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `slide_id` **(many2one)** — Slide ⚠️ obrigatório → `slide.slide`
- `resource_type` **(selection)** — Resource Type ⚠️ obrigatório
  > Opções: `file` (File), `url` (Link)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `data` **(binary)** — Resource
- `file_name` **(char)** — File Name
- `link` **(char)** — Link
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `download_url` **(char)** — Download URL 🔒 readonly
