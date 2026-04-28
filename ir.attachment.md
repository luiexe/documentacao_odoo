# Attachment — `ir.attachment`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `type` **(selection)** — Type ⚠️ obrigatório
  > You can either upload a file from your computer or copy/paste an internet link to your file.
  > Opções: `url` (URL), `binary` (File)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
- `res_model` **(char)** — Resource Model
- `res_field` **(char)** — Resource Field
- `res_id` **(many2one_reference)** — Resource ID
- `url` **(char)** — Url
- `public` **(boolean)** — Is public document
- `access_token` **(char)** — Access Token
- `raw` **(binary)** — File Content (raw)
- `datas` **(binary)** — File Content (base64)
- `db_datas` **(binary)** — Database Data
- `store_fname` **(char)** — Stored Filename
- `file_size` **(integer)** — File Size 🔒 readonly
- `checksum` **(char)** — Checksum/SHA1 🔒 readonly
- `mimetype` **(char)** — Mime Type 🔒 readonly
- `index_content` **(text)** — Indexed Content 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `thumbnail` **(binary)** — Thumbnail
- `key` **(char)** — Key

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `original_id` **(many2one)** — Original (unoptimized, unresized) attachment → `ir.attachment`
- `voice_ids` **(one2many)** — Voice → `discuss.voice.metadata`
- `document_ids` **(one2many)** — Document → `documents.document`
- `website_id` **(many2one)** — Website → `website`
- `theme_template_id` **(many2one)** — Theme Template → `theme.ir.attachment`

## Campos Calculados (readonly)

- `res_name` **(char)** — Resource Name 🔒 readonly
- `local_url` **(char)** — Attachment URL 🔒 readonly
- `image_src` **(char)** — Image Src 🔒 readonly
- `image_width` **(integer)** — Image Width 🔒 readonly
- `image_height` **(integer)** — Image Height 🔒 readonly
- `has_thumbnail` **(boolean)** — Has Thumbnail 🔒 readonly
