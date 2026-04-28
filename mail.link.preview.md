# Store link preview data — `mail.link.preview`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `source_url` **(char)** — URL ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `og_type` **(char)** — Type
- `og_title` **(char)** — Title
- `og_site_name` **(char)** — Site name
- `og_image` **(char)** — Image
- `og_description` **(text)** — Description
- `og_mimetype` **(char)** — MIME type
- `image_mimetype` **(char)** — Image MIME type
- `create_date` **(datetime)** — Create Date
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `message_link_preview_ids` **(one2many)** — Message Link Preview → `mail.message.link.preview`
