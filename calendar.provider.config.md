# Calendar Provider Configuration Wizard — `calendar.provider.config`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `external_calendar_provider` **(selection)** — Choose an external calendar to configure
  > Opções: `google` (Google), `microsoft` (Outlook)
- `cal_client_id` **(char)** — Google Client_id
- `cal_client_secret` **(char)** — Google Client_key
- `cal_sync_paused` **(boolean)** — Google Synchronization Paused
- `microsoft_outlook_client_identifier` **(char)** — Outlook Client Id
- `microsoft_outlook_client_secret` **(char)** — Outlook Client Secret
- `microsoft_outlook_sync_paused` **(boolean)** — Outlook Synchronization Paused
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
