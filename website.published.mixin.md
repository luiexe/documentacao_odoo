# Website Published Mixin — `website.published.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
