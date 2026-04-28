# Website rewrite — `website.rewrite`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `url_from` **(char)** — URL from
- `url_to` **(char)** — URL to
- `redirect_type` **(selection)** — Action
  > Type of redirect/Rewrite:          301 Moved permanently: The browser will keep in cache the new url.         302 Moved temporarily: The browser will not keep in cache the new url and ask again the next time the new url.         404 Not Found: If you want remove a specific page/controller (e.g. Ecommerce is installed, but you don't want /shop on a specific website)         308 Redirect / Rewrite: If you want rename a controller with a new url. (Eg: /shop -> /garden - Both url will be accessible but /shop will automatically be redirected to /garden)     
  > Opções: `404` (404 Not Found), `301` (301 Moved permanently), `302` (302 Moved temporarily), `308` (308 Redirect / Rewrite)
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
- `route_id` **(many2one)** — Route → `website.route`
