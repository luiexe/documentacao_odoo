# Website Theme Menu — `theme.website.menu`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `url` **(char)** — Url
- `new_window` **(boolean)** — New Window
- `sequence` **(integer)** — Sequence
- `mega_menu_content` **(html)** — Mega Menu Content
- `mega_menu_classes` **(char)** — Mega Menu Classes
- `use_main_menu_as_parent` **(boolean)** — Use Main Menu As Parent
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `page_id` **(many2one)** — Page → `theme.website.page`
- `parent_id` **(many2one)** — Parent → `theme.website.menu`
- `copy_ids` **(one2many)** — Menu using a copy of me 🔒 readonly → `website.menu`
