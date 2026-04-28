# Microsoft Outlook Mixin — `microsoft.outlook.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `microsoft_outlook_refresh_token` **(char)** — Outlook Refresh Token
- `microsoft_outlook_access_token` **(char)** — Outlook Access Token
- `microsoft_outlook_access_token_expiration` **(integer)** — Outlook Access Token Expiration Timestamp

## Campos Calculados (readonly)

- `microsoft_outlook_uri` **(char)** — Authentication URI 🔒 readonly
  > The URL to generate the authorization code from Outlook
