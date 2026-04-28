# Knowledge Article — `knowledge.article`

**Ordenação padrão:** `favorite_count desc, write_date desc, id desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `html_field_history` **(json)** — History data 🔒 readonly
- `active` **(boolean)** — Active
- `name` **(char)** — Title
- `body` **(html)** — Body
- `icon` **(char)** — Emoji
- `cover_image_position` **(float)** — Cover vertical offset
- `is_locked` **(boolean)** — Locked
  > When locked, users cannot write on the body or change the title, even if they have write access on the article.
- `full_width` **(boolean)** — Full width
  > When set, the article body will take the full width available on the article page. Otherwise, the body will have large horizontal margins.
- `internal_permission` **(selection)** — Internal Permission
  > Default permission for all internal users. (External users can still have access to this article if they are added to its members)
  > Opções: `write` (Can edit), `read` (Can read), `none` (Members only)
- `inherited_permission` **(selection)** — Inherited Permission 🔒 readonly
  > Opções: `write` (Can edit), `read` (Can read), `none` (Members only)
- `parent_path` **(char)** — Parent Path
- `is_desynchronized` **(boolean)** — Desyncronized with parents
  > If set, this article won't inherit access rules from its parents anymore.
- `sequence` **(integer)** — Sequence
  > The sequence is computed only among the articles that have the same parent.
- `is_article_item` **(boolean)** — Is Item?
- `category` **(selection)** — Section 🔒 readonly
  > Used to categorize articles in UI, depending on their main permission definitions.
  > Opções: `workspace` (Workspace), `private` (Private), `shared` (Shared)
- `last_edition_date` **(datetime)** — Last Edited on 🔒 readonly
- `favorite_count` **(integer)** — #Is Favorite 🔒 readonly
- `is_article_visible_by_everyone` **(boolean)** — Can everyone see the Article?
- `to_delete` **(boolean)** — Trashed
  > When sent to trash, articles are flagged to be deleted                 days after last edit. knowledge_article_trash_limit_days config                 parameter can be used to modify the number of days.                  (default is 30)
- `article_properties_definition` **(properties_definition)** — Article Item Properties
- `article_properties` **(properties)** — Properties
- `is_listed_in_templates_gallery` **(boolean)** — Is listed in Templates Gallery?
  > If checked, the article will appear in the templates gallery under the 'Shared Templates' section
- `is_template` **(boolean)** — Is Template
- `template_body` **(text)** — Template Body
- `template_description` **(char)** — Template Description
- `template_name` **(char)** — Template Title
- `template_sequence` **(integer)** — Template Sequence
  > It determines the display order of the template within its category
- `template_child_default_create` **(boolean)** — Auto-Create Child Article
  > If set, this will automatically create this child article when its parent template is used
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `is_audit_report_template` **(boolean)** — Annual Report Template

## Relacionamentos

- `cover_image_id` **(many2one)** — Article cover → `knowledge.cover`
- `inherited_permission_parent_id` **(many2one)** — Inherited Permission Parent Article 🔒 readonly → `knowledge.article`
- `article_member_ids` **(one2many)** — Members Information → `knowledge.article.member`
- `parent_id` **(many2one)** — Parent Article → `knowledge.article`
- `child_ids` **(one2many)** — Child Articles and Items → `knowledge.article`
- `root_article_id` **(many2one)** — Menu Article 🔒 readonly → `knowledge.article`
  > The subject is the title of the highest parent in the article hierarchy.
- `stage_id` **(many2one)** — Item Stage → `knowledge.article.stage`
- `last_edition_uid` **(many2one)** — Last Edited by 🔒 readonly → `res.users`
- `favorite_ids` **(one2many)** — Favorite Articles → `knowledge.article.favorite`
- `template_category_id` **(many2one)** — Template Category → `knowledge.article.template.category`
- `origin_template_id` **(many2one)** — Template used to generate the article → `knowledge.article`
- `inherited_audit_report_id` **(one2many)** — Inherited Audit Report 🔒 readonly → `audit.report`

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `html_field_history_metadata` **(json)** — History metadata 🔒 readonly
- `cover_image_url` **(char)** — Cover url 🔒 readonly
- `article_url` **(char)** — Article URL 🔒 readonly
- `user_has_access` **(boolean)** — Has Access 🔒 readonly
- `user_has_access_parent_path` **(boolean)** — Can the user join? 🔒 readonly
  > Has the user access to each parent from current article until its root?
- `user_has_write_access` **(boolean)** — Has Write Access 🔒 readonly
- `user_can_read` **(boolean)** — Can Read 🔒 readonly
- `user_can_write` **(boolean)** — Can Edit 🔒 readonly
- `user_permission` **(selection)** — User permission 🔒 readonly
  > Opções: `write` (write), `read` (read), `none` (none)
- `has_item_parent` **(boolean)** — Is the parent an Item? 🔒 readonly
- `has_item_children` **(boolean)** — Has article item children? 🔒 readonly
- `has_article_children` **(boolean)** — Has normal article children? 🔒 readonly
- `last_edition_user_avatar` **(binary)** — Last Editor's Avatar 🔒 readonly
- `is_user_favorite` **(boolean)** — Is Favorited 🔒 readonly
- `user_favorite_sequence` **(integer)** — User Favorite Sequence 🔒 readonly
- `is_article_visible` **(boolean)** — Can the user see the article? 🔒 readonly
- `deletion_date` **(date)** — Deletion Date 🔒 readonly
- `template_category_sequence` **(integer)** — Template Category Sequence 🔒 readonly
  > It determines the display order of the category
- `template_preview` **(html)** — Template Preview 🔒 readonly
- `summary` **(text)** — Summary 🔒 readonly

## Campos de Auditoria

- `audit_report_id` **(one2many)** — Audit Report → `audit.report`
