# Document — `documents.document`

**Ordenação padrão:** `sequence, id desc`

---

## Campos Obrigatórios

- `type` **(selection)** — Type ⚠️ obrigatório 🔒 readonly
  > Opções: `url` (URL), `binary` (File), `folder` (Folder)
- `document_token` **(char)** — Document Token ⚠️ obrigatório
- `access_via_link` **(selection)** — Link Access Rights ⚠️ obrigatório
  > Opções: `view` (Viewer), `edit` (Editor), `none` (None)
- `access_internal` **(selection)** — Internal Users Rights ⚠️ obrigatório
  > Opções: `view` (Viewer), `edit` (Editor), `none` (None)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `spreadsheet_binary_data` **(binary)** — Spreadsheet file
- `spreadsheet_data` **(text)** — Spreadsheet Data
- `thumbnail` **(binary)** — Thumbnail
- `spreadsheet_snapshot` **(binary)** — Spreadsheet Snapshot
- `display_thumbnail` **(binary)** — Display Thumbnail
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>
- `email_cc` **(char)** — Email cc
- `attachment_name` **(char)** — Attachment Name
- `attachment_type` **(selection)** — Attachment Type
  > You can either upload a file from your computer or copy/paste an internet link to your file.
  > Opções: `url` (URL), `binary` (File)
- `is_editable_attachment` **(boolean)** — Is Editable Attachment
  > True if we can edit the link attachment.
- `is_multipage` **(boolean)** — Is considered multipage
- `datas` **(binary)** — File Content (base64)
- `raw` **(binary)** — File Content (raw)
- `file_extension` **(char)** — File Extension
- `file_size` **(integer)** — File Size 🔒 readonly
- `res_model` **(char)** — Resource Model
- `res_id` **(many2one_reference)** — Resource ID
- `description` **(text)** — Attachment Description
- `name` **(char)** — Name
- `active` **(boolean)** — Active
- `thumbnail_status` **(selection)** — Thumbnail Status
  > Opções: `present` (Present), `error` (Error), `client_generated` (Client Generated), `restricted` (Inaccessible)
- `url` **(char)** — Link URL
- `url_preview_image` **(char)** — URL Preview Image
- `is_favorited` **(boolean)** — Is Favorited
- `sequence` **(integer)** — Sequence
- `is_access_via_link_hidden` **(boolean)** — Link Access Hidden
  > If "True", only people given direct access to this document will be able to view it. If "False", access with the link also given to all who can access the parent folder.
- `parent_path` **(char)** — Parent Path
- `create_activity_option` **(boolean)** — Create a new activity
- `create_activity_summary` **(char)** — Summary
- `create_activity_date_deadline_range` **(integer)** — Due Date In
- `create_activity_date_deadline_range_type` **(selection)** — Due type
  > Opções: `days` (Days), `weeks` (Weeks), `months` (Months)
- `create_activity_note` **(html)** — Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `ai_sort_prompt` **(html)** — AI Folder Sort Prompt
  > Prompt used to automatically sort files moved in this folder
- `ai_to_sort` **(boolean)** — AI To Sort
  > Flag to mark the files as to be sorted with AI
- `excel_export` **(binary)** — Excel Export
- `handler` **(selection)** — Handler
  > Opções: `spreadsheet` (Spreadsheet), `frozen_folder` (Frozen Folder), `frozen_spreadsheet` (Frozen Spreadsheet)
- `has_embedded_pdf` **(boolean)** — Has Embedded PDF 🔒 readonly

## Relacionamentos

- `spreadsheet_revision_ids` **(one2many)** — Spreadsheet Revision → `spreadsheet.revision`
- `alias_id` **(many2one)** — Alias → `mail.alias`
- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
- `attachment_id` **(many2one)** — Attachment → `ir.attachment`
- `previous_attachment_ids` **(many2many)** — History → `ir.attachment`
- `shortcut_document_id` **(many2one)** — Source Document → `documents.document`
- `shortcut_document_owner_id` **(many2one)** — Source Document Owner 🔒 readonly → `res.users`
- `shortcut_ids` **(one2many)** — Shortcut → `documents.document`
- `favorited_ids` **(many2many)** — Favorite of → `res.users`
- `tag_ids` **(many2many)** — Tags → `documents.tag`
- `partner_id` **(many2one)** — Contact → `res.partner`
- `owner_id` **(many2one)** — Owner → `res.users`
- `lock_uid` **(many2one)** — Locked by → `res.users`
- `request_activity_id` **(many2one)** — Request Activity → `mail.activity`
- `requestee_partner_id` **(many2one)** — Requestee Partner → `res.partner`
- `access_ids` **(one2many)** — Allowed Access → `documents.access`
- `folder_id` **(many2one)** — Folder → `documents.document`
- `children_ids` **(one2many)** — Children → `documents.document`
- `company_id` **(many2one)** — Company → `res.company`
- `create_activity_type_id` **(many2one)** — Activity type → `mail.activity.type`
- `create_activity_user_id` **(many2one)** — Responsible → `res.users`
- `available_embedded_actions_ids` **(many2many)** — Available Embedded Actions 🔒 readonly → `ir.embedded.actions`
- `alias_tag_ids` **(many2many)** — Alias Tags → `documents.tag`
- `product_template_id` **(many2one)** — Product 🔒 readonly → `product.template`
- `product_id` **(many2one)** — Product Variant 🔒 readonly → `product.product`
- `project_ids` **(one2many)** — Projects → `project.project`
- `website_id` **(many2one)** — Website → `website`
- `ai_document_or_env_company_id` **(many2one)** — AI Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `spreadsheet_file_name` **(char)** — Spreadsheet File Name 🔒 readonly
- `current_revision_uuid` **(char)** — Current Revision Uuid 🔒 readonly
- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_defaults` **(text)** — Default Values 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `alias_email` **(char)** — Email Alias 🔒 readonly
- `checksum` **(char)** — Checksum/SHA1 🔒 readonly
- `mimetype` **(char)** — Mime Type 🔒 readonly
- `res_name` **(char)** — Resource Name 🔒 readonly
- `index_content` **(text)** — Indexed Content 🔒 readonly
- `res_model_name` **(char)** — Res Model Name 🔒 readonly
- `access_token` **(char)** — Access Token 🔒 readonly
- `access_url` **(char)** — Access url 🔒 readonly
- `user_permission` **(selection)** — User permission 🔒 readonly
  > Opções: `edit` (Editor), `view` (Viewer), `none` (None)
- `user_can_move` **(boolean)** — Can move it 🔒 readonly
- `user_folder_id` **(char)** — Parent 🔒 readonly
- `deletion_delay` **(integer)** — Deletion delay 🔒 readonly
  > Delay after permanent deletion of the document in the trash (days)
- `mail_alias_domain_count` **(integer)** — Mail Alias Domain Count 🔒 readonly
- `last_access_date_group` **(selection)** — Last Accessed On 🔒 readonly
  > Opções: `0_older` (Older), `1_month` (This Month), `2_week` (This Week), `3_day` (Today)
- `ai_sortable` **(boolean)** — AI Sortable 🔒 readonly
- `spreadsheet_thumbnail_checksum` **(char)** — Spreadsheet Thumbnail Checksum 🔒 readonly
