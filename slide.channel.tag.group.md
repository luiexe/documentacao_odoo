# Channel/Course Groups — `slide.channel.tag.group`

**Ordenação padrão:** `sequence asc`

---

## Campos Obrigatórios

- `name` **(char)** — Group Name ⚠️ obrigatório
- `sequence` **(integer)** — Sequence ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `tag_ids` **(one2many)** — Tags → `slide.channel.tag`

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
