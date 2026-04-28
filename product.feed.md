# Product Feed — `product.feed`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `website_id` **(many2one)** — Website ⚠️ obrigatório → `website`
- `lang_id` **(many2one)** — Language ⚠️ obrigatório → `res.lang`
  > Select the language to translate product names, descriptions, and other text in the feed.
- `target` **(selection)** — Target ⚠️ obrigatório
  > Opções: `gmc` (Google Merchant Center)
- `access_token` **(char)** — Access Token ⚠️ obrigatório 🔒 readonly
- `cache_expiry` **(datetime)** — Cache Expiry ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `last_notification_date` **(date)** — Last Notification Date
- `feed_cache` **(binary)** — Feed Cache 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `pricelist_id` **(many2one)** — Pricelist → `product.pricelist`
  > Specify a pricelist to localize the feed with a specific currency. If not set, the default website pricelist will be used. Note that the pricelist must be selectable on the website.
- `website_lang_ids` **(many2many)** — Languages 🔒 readonly → `res.lang`
- `product_category_ids` **(many2many)** — Categories → `product.public.category`

## Campos Calculados (readonly)

- `url` **(char)** — Url 🔒 readonly
