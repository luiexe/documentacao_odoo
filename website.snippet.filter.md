# Website Snippet Filter — `website.snippet.filter`

**Ordenação padrão:** `name ASC`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `field_names` **(char)** — Field Names ⚠️ obrigatório
  > A list of comma-separated field names
- `limit` **(integer)** — Limit ⚠️ obrigatório
  > The limit is the maximum number of records retrieved

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `help` **(text)** — Description
  > Optional help text describing the filter usage and/or purpose.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `product_cross_selling` **(boolean)** — About cross selling products
  > True only for product filters that require a product_id because they relate to cross selling

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `action_server_id` **(many2one)** — Server Action → `ir.actions.server`
- `filter_id` **(many2one)** — Filter → `ir.filters`

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `model_name` **(char)** — Model name 🔒 readonly
