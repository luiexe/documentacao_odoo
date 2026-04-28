# Link Tracker Click — `link.tracker.click`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `link_id` **(many2one)** — Link ⚠️ obrigatório → `link.tracker`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `ip` **(char)** — Internet Protocol
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `campaign_id` **(many2one)** — UTM Campaign 🔒 readonly → `utm.campaign`
  > This is a name that helps you keep track of your different campaign efforts, e.g. Fall_Drive, Christmas_Special
- `country_id` **(many2one)** — Country → `res.country`
- `mailing_trace_id` **(many2one)** — Mail Statistics → `mailing.trace`
- `mass_mailing_id` **(many2one)** — Mass Mailing → `mailing.mailing`
- `whatsapp_message_id` **(many2one)** — Whatsapp Message → `whatsapp.message`
