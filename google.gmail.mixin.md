# Google Gmail Mixin — `google.gmail.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `google_gmail_refresh_token` **(char)** — Refresh Token
- `google_gmail_access_token` **(char)** — Access Token
- `google_gmail_access_token_expiration` **(integer)** — Access Token Expiration Timestamp

## Campos Calculados (readonly)

- `google_gmail_uri` **(char)** — URI 🔒 readonly
  > The URL to generate the authorization code from Google
