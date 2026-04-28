# Product Document — `product.document`

**Ordenação padrão:** `sequence, name`

---

## Campos Obrigatórios

- `ir_attachment_id` **(many2one)** — Related attachment ⚠️ obrigatório → `ir.attachment`
- `attached_on_mrp` **(selection)** — MRP : Visible at ⚠️ obrigatório
  > Leave hidden if document only accessible on product form. Select Bill of Materials to visualise this document as a product attachment when this product is in a bill of material.
  > Opções: `hidden` (Hidden), `bom` (Bill of Materials)
- `attached_on_sale` **(selection)** — Sale : Visible at ⚠️ obrigatório
  > Allows you to share the document with your customers within a sale. Leave it empty if you don't want to share this document with sales customer. On quote: the document will be sent to and accessible by customers at any time. e.g. this option can be useful to share Product description files. On order confirmation: the document will be sent to and accessible by customers. e.g. this option can be useful to share User Manual or digital content bought on ecommerce.  Inside quote: The document will be included in the pdf of the quotation and sale order between the header pages and the quote table. 
  > Opções: `hidden` (Hidden), `quotation` (On quote), `sale_order` (On confirmed order), `inside` (Inside quote pdf)
- `name` **(char)** — Name ⚠️ obrigatório
- `type` **(selection)** — Type ⚠️ obrigatório
  > You can either upload a file from your computer or copy/paste an internet link to your file.
  > Opções: `url` (URL), `binary` (File)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `shown_on_product_page` **(boolean)** — Publish on website
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

- `origin_attachment_id` **(many2one)** — Origin Attachment → `ir.attachment`
- `form_field_ids` **(many2many)** — Form Fields Included 🔒 readonly → `sale.pdf.form.field`
- `company_id` **(many2one)** — Company → `res.company`
- `original_id` **(many2one)** — Original (unoptimized, unresized) attachment → `ir.attachment`
- `voice_ids` **(one2many)** — Voice → `discuss.voice.metadata`
- `document_ids` **(one2many)** — Document → `documents.document`
- `website_id` **(many2one)** — Website → `website`
- `theme_template_id` **(many2one)** — Theme Template → `theme.ir.attachment`

## Campos Calculados (readonly)

- `origin_res_model` **(char)** — Origin Model 🔒 readonly
- `origin_res_name` **(char)** — Origin Name 🔒 readonly
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
