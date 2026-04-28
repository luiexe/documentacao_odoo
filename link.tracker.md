# Link Tracker — `link.tracker`

**Ordenação padrão:** `count DESC`

---

## Campos Obrigatórios

- `url` **(char)** — Target URL ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `title` **(char)** — Page Title
- `label` **(char)** — Button label
- `code` **(char)** — Short URL code
- `count` **(integer)** — Number of Clicks 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `campaign_id` **(many2one)** — Campaign → `utm.campaign`
  > This is a name that helps you keep track of your different campaign efforts, e.g. Fall_Drive, Christmas_Special
- `source_id` **(many2one)** — Source → `utm.source`
  > This is the source of the link, e.g. Search Engine, another domain, or name of email list
- `medium_id` **(many2one)** — Medium → `utm.medium`
  > This is the method of delivery, e.g. Postcard, Email, or Banner Ad
- `link_code_ids` **(one2many)** — Codes → `link.tracker.code`
- `link_click_ids` **(one2many)** — Clicks → `link.tracker.click`
- `mass_mailing_id` **(many2one)** — Mass Mailing → `mailing.mailing`

## Campos Calculados (readonly)

- `absolute_url` **(char)** — Absolute URL 🔒 readonly
- `short_url` **(char)** — Tracked URL 🔒 readonly
- `redirected_url` **(char)** — Redirected URL 🔒 readonly
- `short_url_host` **(char)** — Host of the short URL 🔒 readonly
