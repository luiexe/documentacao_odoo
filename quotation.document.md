# Quotation's Headers & Footers — `quotation.document`

**Ordenação padrão:** `document_type desc, sequence, name`

---

## Campos Obrigatórios

- `ir_attachment_id` **(many2one)** — Related attachment ⚠️ obrigatório → `ir.attachment`
- `document_type` **(selection)** — Document Type ⚠️ obrigatório
  > Opções: `header` (Header), `footer` (Footer)
- `name` **(char)** — Name ⚠️ obrigatório
- `type` **(selection)** — Type ⚠️ obrigatório
  > You can either upload a file from your computer or copy/paste an internet link to your file.
  > Opções: `url` (URL), `binary` (File)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If unchecked, it will allow you to hide the header or footer without removing it.
- `sequence` **(integer)** — Sequence
- `add_by_default` **(boolean)** — Add By Default
  > If checked, this header or footer will be added by default on new quotes.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
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
- `thumbnail` **(binary)** — Thumbnail
- `key` **(char)** — Key

## Relacionamentos

- `quotation_template_ids` **(many2many)** — Quotation Templates → `sale.order.template`
- `form_field_ids` **(many2many)** — Form Fields Included 🔒 readonly → `sale.pdf.form.field`
- `company_id` **(many2one)** — Company → `res.company`
- `original_id` **(many2one)** — Original (unoptimized, unresized) attachment → `ir.attachment`
- `voice_ids` **(one2many)** — Voice → `discuss.voice.metadata`
- `document_ids` **(one2many)** — Document → `documents.document`
- `website_id` **(many2one)** — Website → `website`
- `theme_template_id` **(many2one)** — Theme Template → `theme.ir.attachment`

## Campos Calculados (readonly)

- `res_name` **(char)** — Resource Name 🔒 readonly
- `file_size` **(integer)** — File Size 🔒 readonly
- `checksum` **(char)** — Checksum/SHA1 🔒 readonly
- `mimetype` **(char)** — Mime Type 🔒 readonly
- `index_content` **(text)** — Indexed Content 🔒 readonly
- `local_url` **(char)** — Attachment URL 🔒 readonly
- `image_src` **(char)** — Image Src 🔒 readonly
- `image_width` **(integer)** — Image Width 🔒 readonly
- `image_height` **(integer)** — Image Height 🔒 readonly
- `has_thumbnail` **(boolean)** — Has Thumbnail 🔒 readonly
