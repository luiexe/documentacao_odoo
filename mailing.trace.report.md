# Mass Mailing Statistics — `mailing.trace.report`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mailing_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `mail` (Mail)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Mass Mail 🔒 readonly
- `campaign` **(char)** — Mailing Campaign 🔒 readonly
- `scheduled_date` **(datetime)** — Scheduled Date 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Draft), `test` (Tested), `done` (Sent)
- `email_from` **(char)** — From 🔒 readonly
- `scheduled` **(integer)** — Scheduled 🔒 readonly
- `processing` **(integer)** — Processing 🔒 readonly
- `pending` **(integer)** — Pending 🔒 readonly
- `sent` **(integer)** — Sent 🔒 readonly
- `delivered` **(integer)** — Delivered 🔒 readonly
- `error` **(integer)** — Error 🔒 readonly
- `opened` **(integer)** — Opened 🔒 readonly
- `replied` **(integer)** — Replied 🔒 readonly
- `bounced` **(integer)** — Bounced 🔒 readonly
- `canceled` **(integer)** — Canceled 🔒 readonly
- `clicked` **(integer)** — Clicked 🔒 readonly
