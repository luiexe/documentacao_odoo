# Website Generator Request — `website_generator.request`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `target_url` **(char)** — URL to scrape ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `additional_urls` **(char)** — Additional URLs
- `page_count` **(integer)** — Number of pages
- `uuid` **(char)** — Output UUID generated from Website Scraper Server
- `status` **(char)** — Status
- `version` **(char)** — Version
- `notified` **(boolean)** — Notified
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`

## Campos Calculados (readonly)

- `status_message` **(char)** — Status Message 🔒 readonly
