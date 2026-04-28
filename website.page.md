# Page — `website.page`

**Ordenação padrão:** `website_id`

---

## Campos Obrigatórios

- `url` **(char)** — Page URL ⚠️ obrigatório
- `view_id` **(many2one)** — View ⚠️ obrigatório → `ir.ui.view`
- `name` **(char)** — View Name ⚠️ obrigatório
- `priority` **(integer)** — Sequence ⚠️ obrigatório
- `mode` **(selection)** — View inheritance mode ⚠️ obrigatório
  > Only applies if this view inherits from an other one (inherit_id is not False/Null).  * if extension (default), if this view is requested the closest primary view is looked up (via inherit_id), then all views inheriting from it with this view's model are applied * if primary, the closest primary view is fully resolved (even if it uses a different model than this one), then this view's inheritance specs (<xpath/>) are applied, and the result is used as if it were this view's actual arch. 
  > Opções: `primary` (Base view), `extension` (Extension View)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `header_visible` **(boolean)** — Header Visible
- `footer_visible` **(boolean)** — Footer Visible
- `header_overlay` **(boolean)** — Header Overlay
- `header_color` **(char)** — Header Color
- `header_text_color` **(char)** — Header Text Color
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `website_indexed` **(boolean)** — Is Indexed
- `date_publish` **(datetime)** — Publishing Date
- `is_new_page_template` **(boolean)** — New Page Template
  > Add this page to the "+New" page templates. It will be added to the "Custom" category.
- `arch` **(text)** — View Architecture
  > This field should be used when accessing view arch. It will use translation.                                Note that it will read `arch_db` or `arch_fs` if in dev-xml mode.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `model` **(char)** — Model
- `key` **(char)** — Key
- `type` **(selection)** — View Type
  > Opções: `list` (List), `form` (Form), `graph` (Graph), `pivot` (Pivot), `calendar` (Calendar), `kanban` (Kanban), `search` (Search), `qweb` (QWeb), `cohort` (Cohort), `gantt` (Gantt), `grid` (Grid), `hierarchy` (Hierarchy), `map` (Map), `activity` (Activity)
- `arch_base` **(text)** — Base View Architecture
  > This field is the same as `arch` field without translations
- `arch_db` **(text)** — Arch Blob
  > This field stores the view arch.
- `arch_fs` **(char)** — Arch Filename
  > File from where the view originates.                                                           Useful to (hard) reset broken views or to read arch from file in dev-xml mode.
- `arch_updated` **(boolean)** — Modified Architecture
- `arch_prev` **(text)** — Previous View Architecture
  > This field will save the current `arch_db` before writing on it.                                                                          Useful to (soft) reset a broken view.
- `active` **(boolean)** — Active
  > If this view is inherited, * if True, the view always extends its parent * if False, the view currently does not extend its parent but can be enabled          
- `customize_show` **(boolean)** — Show As Optional Inherit
- `track` **(boolean)** — Track
  > Allow to specify for one page of the website to be trackable or not
- `visibility` **(selection)** — Visibility
  > Opções: `` (Public), `connected` (Signed In), `restricted_group` (Restricted Group), `password` (With Password)
- `visibility_password` **(char)** — Visibility Password
- `visibility_password_display` **(char)** — Visibility Password Display

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `view_write_uid` **(many2one)** — Last Content Update by 🔒 readonly → `res.users`
- `menu_ids` **(one2many)** — Related Menus → `website.menu`
- `theme_template_id` **(many2one)** — Theme Template → `theme.website.page`
- `inherit_id` **(many2one)** — Inherited View → `ir.ui.view`
- `inherit_children_ids` **(one2many)** — Views which inherit from this one → `ir.ui.view`
- `model_data_id` **(many2one)** — Model Data 🔒 readonly → `ir.model.data`
- `group_ids` **(many2many)** — Groups → `res.groups`
  > If this field is empty, the view applies to all users. Otherwise, the view applies to the users of those groups only.
- `model_id` **(many2one)** — Model of the view → `ir.model`
- `page_ids` **(one2many)** — Page → `website.page`
- `controller_page_ids` **(one2many)** — Controller Page → `website.controller.page`
- `first_page_id` **(many2one)** — Website Page 🔒 readonly → `website.page`
  > First page linked to this view

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `view_write_date` **(datetime)** — Last Content Update on 🔒 readonly
- `is_in_menu` **(boolean)** — Is In Menu 🔒 readonly
- `is_homepage` **(boolean)** — Homepage 🔒 readonly
- `is_visible` **(boolean)** — Is Visible 🔒 readonly
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `xml_id` **(char)** — External ID 🔒 readonly
  > ID of the view defined in xml file
- `warning_info` **(html)** — Warning information 🔒 readonly
- `invalid_locators` **(json)** — Invalid Locators 🔒 readonly
