# Sign Tempate Preview — `sign.template.preview`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Template → `sign.template`
- `document_id` **(many2one)** — Document → `sign.document`

## Campos Calculados (readonly)

- `pdf_data` **(binary)** — Pdf Data 🔒 readonly
