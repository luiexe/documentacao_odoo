# Page Properties — `website.page.properties`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `website_id` **(many2one)** — Website ⚠️ obrigatório → `website`
- `url` **(char)** — Page URL ⚠️ obrigatório
- `redirect_type` **(selection)** — Redirect Type ⚠️ obrigatório
  > Opções: `301` (301 Moved permanently), `302` (302 Moved temporarily)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `is_in_menu` **(boolean)** — Is In Menu
- `is_homepage` **(boolean)** — Homepage
- `is_published` **(boolean)** — Is Published
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `name` **(char)** — View Name
- `date_publish` **(datetime)** — Publishing Date
- `website_indexed` **(boolean)** — Is Indexed
- `visibility` **(selection)** — Visibility
  > Opções: `` (Public), `connected` (Signed In), `restricted_group` (Restricted Group), `password` (With Password)
- `visibility_password_display` **(char)** — Visibility Password Display
- `is_new_page_template` **(boolean)** — New Page Template
  > Add this page to the "+New" page templates. It will be added to the "Custom" category.
- `old_url` **(char)** — Old Url
- `redirect_old_url` **(boolean)** — Redirect Old Url

## Relacionamentos

- `target_model_id` **(many2one)** — Target Model → `website.page`
- `menu_ids` **(one2many)** — Menu 🔒 readonly → `website.menu`
- `group_ids` **(many2many)** — Groups → `res.groups`
  > If this field is empty, the view applies to all users. Otherwise, the view applies to the users of those groups only.

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
