# Website Theme Page — `theme.website.page`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `view_id` **(many2one)** — View ⚠️ obrigatório → `theme.ir.ui.view`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `header_visible` **(boolean)** — Header Visible
- `footer_visible` **(boolean)** — Footer Visible
- `header_overlay` **(boolean)** — Header Overlay
- `header_color` **(char)** — Header Color
- `header_text_color` **(char)** — Header Text Color
- `url` **(char)** — Url
- `website_indexed` **(boolean)** — Page Indexed
- `is_published` **(boolean)** — Is Published
- `is_new_page_template` **(boolean)** — New Page Template
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `copy_ids` **(one2many)** — Page using a copy of me 🔒 readonly → `website.page`
