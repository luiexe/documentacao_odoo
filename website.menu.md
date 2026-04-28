# Website Menu — `website.menu`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Menu ⚠️ obrigatório
- `url` **(char)** — Url ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `new_window` **(boolean)** — New Window
- `sequence` **(integer)** — Sequence
- `parent_path` **(char)** — Parent Path
- `is_mega_menu` **(boolean)** — Is Mega Menu
- `mega_menu_content` **(html)** — Mega Menu Content
- `mega_menu_classes` **(char)** — Mega Menu Classes
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `page_id` **(many2one)** — Related Page → `website.page`
- `controller_page_id` **(many2one)** — Related Model Page → `website.controller.page`
- `website_id` **(many2one)** — Website → `website`
- `parent_id` **(many2one)** — Parent Menu → `website.menu`
- `child_id` **(one2many)** — Child Menus → `website.menu`
- `group_ids` **(many2many)** — Visible Groups → `res.groups`
  > User needs to be at least in one of these groups to see the menu
- `theme_template_id` **(many2one)** — Theme Template → `theme.website.menu`

## Campos Calculados (readonly)

- `is_visible` **(boolean)** — Is Visible 🔒 readonly
